SELECT
  c.client                                   AS client,
  sp.sys_prin,
  COALESCE(
    (SELECT '[' || COALESCE(LISTAGG('"' || REPLACE(i.area, '"', '\"') || '"', ','), '') || ']'
       FROM invalid_deliv_areas i
      WHERE i.sys_prin = sp.sys_prin),
    '[]'
  ) AS invalid_deliv_areas,
  COALESCE(
    (SELECT '[' || COALESCE(LISTAGG('"' || REPLACE(s.vend_id, '"', '\"') || '"', ','), '') || ']'
       FROM vendor_sent_to s
      WHERE s.sys_prin = sp.sys_prin),
    '[]'
  ) AS vendor_sent_to,
  COALESCE(
    (SELECT '[' || COALESCE(LISTAGG('"' || REPLACE(r.vend_id, '"', '\"') || '"', ','), '') || ']'
       FROM vendor_received_from r
      WHERE r.sys_prin = sp.sys_prin),
    '[]'
  ) AS vendor_received_from
FROM clients c
LEFT JOIN sys_prins sp
  ON sp.client = c.client
WHERE c.client IS NOT NULL
ORDER BY c.client, sp.sys_prin;
