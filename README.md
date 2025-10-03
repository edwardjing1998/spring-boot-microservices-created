-- Standard SQL, should run on all major RDBMS with minimal/no changes
SELECT c.client,
       sp.sys_prin,
       'invalid_deliv_areas' AS list_name,
       i.area AS item
FROM   clients c
LEFT JOIN sys_prins sp
       ON sp.client = c.client
LEFT JOIN invalid_deliv_areas i
       ON i.sys_prin = sp.sys_prin

UNION ALL

SELECT c.client,
       sp.sys_prin,
       'vendor_sent_to' AS list_name,
       s.vend_id AS item
FROM   clients c
LEFT JOIN sys_prins sp
       ON sp.client = c.client
LEFT JOIN vendor_sent_to s
       ON s.sys_prin = sp.sys_prin

UNION ALL

SELECT c.client,
       sp.sys_prin,
       'vendor_received_from' AS list_name,
       r.vend_id AS item
FROM   clients c
LEFT JOIN sys_prins sp
       ON sp.client = c.client
LEFT JOIN vendor_received_from r
       ON r.sys_prin = sp.sys_prin

ORDER BY client, sys_prin, list_name, item;
