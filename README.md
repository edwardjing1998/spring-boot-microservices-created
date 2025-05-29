COLUMN_NAME	DATA_TYPE	IS_NULLABLE	CHARACTER_MAXIMUM_LENGTH
Vend_id	char	NO	3
Vend_nm	char	NO	50
Vend_Actv_cd	bit	NO	NULL
Vend_Rcvr_cd	bit	NO	NULL
Vend_fsrv_nm	char	YES	40
Vend_fsrv_ip	char	YES	15
fsrvr_user_id	char	YES	10
fsrvr_usr_pwd_tx	char	YES	50
fsrvr_file_name_tx	char	YES	50
fsrvr_UNC_share_tx	char	YES	255
fsrvr_path_tx	char	YES	50
fsrvr_file_archive_path_tx	char	YES	50
Vendor_Type_cd	char	YES	1
Vend_file_IO	char	YES	1
Vend_client_specific	bit	YES	NULL
Vend_schedule	char	YES	8
Vend_date_last_worked	char	YES	10
Vend_filesize	int	YES	NULL
Vend_filetrans_specs	char	YES	50
Vend_file_type	int	YES	NULL
ftp_passive	char	YES	5
ftp_filetype	char	YES	1




"sSQL = "SELECT Vend_id, Vend_nm, Vend_rcvr_cd, Vend_fsrv_nm, Vend_fsrv_ip" _ & " FROM VENDOR WHERE VEND_ACTV_CD = 1 and Vend_file_IO ='" & Trim$(sFile) & "'" " is for FilesentTo or FileSentFrom ?

vendor_sent_to

sys_prin	char	NO	8
vend_id	char	NO	3
queformail_cd	bit	NO	NULL







