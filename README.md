UPDATE clients
SET addr = 'New address'
WHERE ROWID = (
  SELECT ROWID
  FROM clients
  WHERE client = '0001'
  FETCH FIRST 1 ROWS ONLY
);


Msg 156, Level 15, State 1, Line 29
Incorrect syntax near the keyword 'FETCH'.
Msg 153, Level 15, State 2, Line 29
Invalid usage of the option FIRST in the FETCH statement.
