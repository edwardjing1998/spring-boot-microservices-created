UPDATE clients
SET name = 'New Name'
WHERE ROWID = (
  SELECT ROWID
  FROM clients
  WHERE client = '0001'
    AND name   = 'Old Name'
    -- ... other equality predicates ...
  FETCH FIRST 1 ROWS ONLY
);
