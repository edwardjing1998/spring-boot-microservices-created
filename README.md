SELECT
  c.client_code              AS client,
  sp.sys_prin                AS sys_prin,
  COALESCE(ida.areas, ARRAY[]::text[]) AS invalid_deliv_areas,
  COALESCE(vst.vendors, ARRAY[]::text[]) AS vendor_sent_to,
  COALESCE(vrf.vendors, ARRAY[]::text[]) AS vendor_received_from
FROM clients c
LEFT JOIN sys_prins sp
  ON sp.client_id = c.client_id
LEFT JOIN (
  SELECT sys_prin, ARRAY_AGG(area ORDER BY area) AS areas
  FROM invalid_deliv_areas
  GROUP BY sys_prin
) ida ON ida.sys_prin = sp.sys_prin
LEFT JOIN (
  SELECT sys_prin, ARRAY_AGG(vendor ORDER BY vendor) AS vendors
  FROM vendor_sent_to
  GROUP BY sys_prin
) vst ON vst.sys_prin = sp.sys_prin
LEFT JOIN (
  SELECT sys_prin, ARRAY_AGG(vendor ORDER BY vendor) AS vendors
  FROM vendor_received_from
  GROUP BY sys_prin
) vrf ON vrf.sys_prin = sp.sys_prin
ORDER BY c.client_code, sp.sys_prin;

