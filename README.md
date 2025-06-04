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


DELETED_CASES

case_number	char	NO
pi_id	char	YES
customer_id	char	YES
primary_pi_id	char	YES
account	char	YES
last_name	char	YES
first_name	char	YES
hm_phone	char	YES
wk_phone	char	YES
entity_cd	char	YES
role_cd	char	YES
pi_status	char	YES
status	char	YES
active	bit	NO
reason	char	YES
subreason	int	YES
disposition	char	YES
in_hour	int	YES
in_date	datetime	YES
next_date	datetime	YES
out_date	datetime	YES
auto_date	datetime	YES
num_cards	int	YES
final_action_cards_nr	int	YES
delivery_id	int	YES
sys_prin	char	YES
cycle	char	YES
Frst_Updt_Vend_id	char	YES
Contact_cd	char	YES
Contact_Ph_nr	char	YES
Return_Reason_cd	char	YES
Issuance_cd	char	YES
issuance_dt	datetime	YES
WorkStation_name_tx	char	YES
Operator_CD	char	YES
Barcode_Type_CD	char	YES
rec_typ_tx	char	YES
srvc_typ_tx	char	YES
mailer_id	char	YES
AS400_client_id	char	YES
AS400_system_id	char	YES
bsc_spplmntl_id	char	YES
orig_ml_dt	datetime	YES
msg_id	char	YES
ml_mthd	char	YES
source_file	char	YES
cust_id	char	YES
ms_issue_date	char	YES
cust_id2	char	YES
mkt_cd	char	YES
account_tokenid	char	YES
pi_id_tokenid	char	YES
primary_pi_id_tokenid	char	YES

