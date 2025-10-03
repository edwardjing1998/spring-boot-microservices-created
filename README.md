SELECT
  c.client_code                                   AS client,
  sp.sys_prin,
  COALESCE(ida.areas_json, '[]')                  AS invalid_deliv_areas,
  COALESCE(vst.vendors_json, '[]')                AS vendor_sent_to,
  COALESCE(vrf.vendors_json, '[]')                AS vendor_received_from
FROM dbo.clients      AS c
LEFT JOIN dbo.sys_prins AS sp
  ON sp.client_id = c.client_id
OUTER APPLY (
  SELECT '[' + STRING_AGG(QUOTENAME(i.area, '"'), ',') + ']'
  FROM dbo.invalid_deliv_areas AS i
  WHERE i.sys_prin = sp.sys_prin
) AS ida(areas_json)
OUTER APPLY (
  SELECT '[' + STRING_AGG(QUOTENAME(s.vendor, '"'), ',') + ']'
  FROM dbo.vendor_sent_to AS s
  WHERE s.sys_prin = sp.sys_prin
) AS vst(vendors_json)
OUTER APPLY (
  SELECT '[' + STRING_AGG(QUOTENAME(r.vendor, '"'), ',') + ']'
  FROM dbo.vendor_received_from AS r
  WHERE r.sys_prin = sp.sys_prin
) AS vrf(vendors_json)
WHERE c.client_code IS NOT NULL  -- optional guard
ORDER BY c.client_code, sp.sys_prin;
