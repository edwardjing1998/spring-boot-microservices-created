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





Vend_id,Vend_nm,Vend_Actv_cd,Vend_Rcvr_cd,Vend_fsrv_nm,Vend_fsrv_ip,fsrvr_user_id,fsrvr_usr_pwd_tx,fsrvr_file_name_tx,fsrvr_UNC_share_tx,fsrvr_path_tx,fsrvr_file_archive_path_tx,Vendor_Type_cd,Vend_file_IO,Vend_client_specific,Vend_schedule,Vend_date_last_worked,Vend_filesize,Vend_filetrans_specs,Vend_file_type,ftp_passive,ftp_filetype
v01,"Teleservices                                      ",1,1,"tafmsas2                                ","               ","ndmfrd0   ","0718CF1F9445528370DDFE84CA612E9D                  ","Rapid-Amex.TXT                                    ","Transferdata                                                                                                                                                                                                                                                   ","Rapid                                             ","Rapid\Archive                                     ",A,O,0,10:30:00,2015/09/07,NULL,NULL,3,NULL,NULL
v02,"Letters                                           ",1,1,"tafmsas2                                ","               ","ndmfrd0   ","0718CF1F9445528370DDFE84CA612E9D                  ","AmexLetters.txt                                   ","Transferdata                                                                                                                                                                                                                                                   ","Rapid                                             ","Rapid\Archive                                     ",A,I,0,10:30:00,2015/09/08,NULL,NULL,3,NULL,NULL
v03,"Solutions                                         ",1,1,"tafmsas2                                ","               ","ndmfrd0   ","0718CF1F9445528370DDFE84CA612E9D                  ","Solutions.txt                                     ","Transferdata                                                                                                                                                                                                                                                   ","Temp                                              ","Rapid\Archive                                     ",A,I,0,10:30:00,2015/09/08,NULL,NULL,3,NULL,NULL
v04,"Remail Memo Rejects                               ",1,1,"tafmsas2                                ","               ","ndmfrd0   ","0718CF1F9445528370DDFE84CA612E9D                  ","FWRreject.OUT                                     ","Transferdata                                                                                                                                                                                                                                                   ","Rapid                                             ","Rapid\Archive                                     ",R,I,0,10:30:00,2015/09/08,NULL,NULL,3,NULL,NULL
v05,"Memo Rejects                                      ",1,1,"tafmsas2                                ","               ","ndmfrd0   ","0718CF1F9445528370DDFE84CA612E9D                  ","RETRreject.OUT                                    ","Transferdata                                                                                                                                                                                                                                                   ","Rapid                                             ","Rapid\Archive                                     ",R,I,0,10:30:00,2015/09/08,NULL,NULL,3,NULL,NULL
v08,"Solutions Rec                                     ",1,1,"tafmsas2                                ","               ","ndmfrd0   ","0718CF1F9445528370DDFE84CA612E9D                  ","RFIIRA2I.TXT                                      ","Transferdata                                                                                                                                                                                                                                                   ","RAPID\Solutions\Input\RFIIRA2I                    ",NULL,A,I,0,10:30:00,2015/09/08,NULL,"Sol1                                              ",3,NULL,NULL
v09,"Solutions Send                                    ",1,1,"tafmsas2                                ","               ","ndmfrd0   ","0718CF1F9445528370DDFE84CA612E9D                  ","SOLU.TXT                                          ","Transferdata                                                                                                                                                                                                                                                   ","RAPID\Solutions\Output\RFIIRA2I                   ",NULL,A,O,0,10:30:00,2015/09/07,156,NULL,3,NULL,NULL
v10,"ProvWamu                                          ",1,0,"tafmsas2                                ","               ","ndmfrd0   ","0718CF1F9445528370DDFE84CA612E9D                  ","prowamuad.txt                                     ","TransferData                                                                                                                                                                                                                                                   ","Rapid                                             ","Rapid\Archive                                     ",A,I,0,10:30:00,2015/09/08,NULL,NULL,3,NULL,NULL
