SELECT
c.client                                   AS client,
sp.sys_prin,
COALESCE(ida.areas_json, '[]')                  AS invalid_deliv_areas,
COALESCE(vst.vendors_json, '[]')                AS vendor_sent_to,
COALESCE(vrf.vendors_json, '[]')                AS vendor_received_from
FROM dbo.clients      AS c
LEFT JOIN dbo.sys_prins AS sp
ON sp.client = c.client
OUTER APPLY (
SELECT '[' + STRING_AGG(QUOTENAME(i.area, '"'), ',') + ']'
FROM dbo.invalid_deliv_areas AS i
WHERE i.sys_prin = sp.sys_prin
) AS ida(areas_json)
OUTER APPLY (
SELECT '[' + STRING_AGG(QUOTENAME(s.vend_id, '"'), ',') + ']'
FROM dbo.vendor_sent_to AS s
WHERE s.sys_prin = sp.sys_prin
) AS vst(vendors_json)
OUTER APPLY (
SELECT '[' + STRING_AGG(QUOTENAME(r.vend_id, '"'), ',') + ']'
FROM dbo.vendor_sent_to AS r
WHERE r.sys_prin = sp.sys_prin
) AS vrf(vendors_json)
WHERE c.client IS NOT NULL  -- optional guard
ORDER BY c.client, sp.sys_prin;
