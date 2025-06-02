bulk_card:

Case_number	char	NO	12
PI_ID	char	NO	16
Bulk_PI_ID	char	NO	16
in_date	datetime	NO	NULL


Failed_Trans

case_number	char	YES	12
type	smallint	YES	NULL
command_line	varchar	YES	255
system_type	varchar	YES	50
retry_count	smallint	YES	NULL
date_time	datetime	YES	NULL
cycle	varchar	YES	1
trans_no	numeric	YES	NULL


SELECT
    c.name AS ColumnName,
    c.is_identity AS IsIdentity,
    c.seed_value AS IdentitySeed,
    c.increment_value AS IdentityIncrement
FROM
    sys.columns c
INNER JOIN
    sys.tables t ON c.object_id = t.object_id
WHERE
    t.name = 'YourTableName' AND c.name = 'YourColumnName';

