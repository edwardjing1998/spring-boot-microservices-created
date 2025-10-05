2025-10-05T13:26:29.773-05:00 ERROR 7364 --- [client-sysprin-reader] [0.0-8083-exec-4] o.a.c.c.C.[.[.[/].[dispatcherServlet]    : Servlet.service() for servlet [dispatcherServlet] in context with path [] threw exception [Request processing failed: org.springframework.jdbc.UncategorizedSQLException: PreparedStatementCallback; uncategorized SQLException for SQL [SELECT
  JSON_ARRAYAGG(
    JSON_OBJECT(
      'client'              VALUE c.client,
      'name'                VALUE c.name,
      'addr'                VALUE c.addr,
      'city'                VALUE c.city,
      'state'               VALUE c.state,
      'zip'                 VALUE c.zip,
      'contact'             VALUE c.contact,
      'phone'               VALUE c.phone,
      'active'              VALUE c.active,
      'faxNumber'           VALUE c.fax_number,
      'billingSp'           VALUE c.billing_sp,
      'reportBreakFlag'     VALUE c.report_break_flag,
      'chLookUpType'        VALUE c.chlookup_type,
      'excludeFromReport'   VALUE c.exclude_from_report,
      'positiveReports'     VALUE c.positive_reports,
      'subClientInd'        VALUE c.sub_client_ind,
      'subClientXref'       VALUE c.sub_client_xref,
      'amexIssued'          VALUE c.amex_issued,
      'reportOptions' VALUE COALESCE((
        SELECT JSON_ARRAYAGG(
          JSON_OBJECT(
            'clientId'         VALUE ro.client_id,
            'reportId'         VALUE ro.report_id,
            'receiveFlag'      VALUE ro.receive_flag,
            'outputTypeCd'     VALUE ro.output_type_cd,
            'fileTypeCd'       VALUE ro.file_type_cd,
            'emailFlag'        VALUE ro.email_flag,
            'emailBodyTx'      VALUE ro.email_body_tx,
            'reportPasswordTx' VALUE ro.report_password_tx,
            'reportDetails' VALUE (
              SELECT JSON_OBJECT(
                'reportId'             VALUE rd.report_id,
                'queryName'            VALUE rd.query_name,
                'query'                VALUE rd.query,
                'inputDataFields'      VALUE rd.input_data_fields,
                'fileExt'              VALUE rd.file_ext,
                'dbDriverType'         VALUE rd.db_driver_type,
                'fileHeaderInd'        VALUE rd.file_header_ind,
                'defaultFileNm'        VALUE rd.default_file_nm,
                'reportDbServer'       VALUE rd.report_db_server,
                'reportDb'             VALUE rd.report_db,
                'reportDbUserid'       VALUE rd.report_db_userid,
                'reportDbPasswrd'      VALUE rd.report_db_passwrd,
                'fileTransferType'     VALUE rd.file_transfer_type,
                'reportDbIpAndPort'    VALUE rd.report_db_ip_and_port,
                'reportByClientFlag'   VALUE rd.report_by_client_flag,
                'rerunDateRangeStart'  VALUE rd.rerun_date_range_start,
                'rerunDateRangeEnd'    VALUE rd.rerun_date_range_end,
                'rerunClientId'        VALUE rd.rerun_client_id,
                'emailFromAddress'     VALUE rd.email_from_address,
                'emailEventId'         VALUE rd.email_event_id,
                'tabDelimitedFlag'     VALUE rd.tab_delimited_flag,
                'inputFileTx'          VALUE rd.input_file_tx,
                'inputFileKeyStartPos' VALUE rd.input_file_key_start_pos,
                'inputFileKeyLength'   VALUE rd.input_file_key_length,
                'accessLevel'          VALUE rd.access_level,
                'isActive'             VALUE rd.is_active,
                'isVisible'            VALUE rd.is_visible,
                'numSheets'            VALUE rd.num_sheets,
                'c3FileTransfer' VALUE (
                  SELECT JSON_OBJECT(
                    'fileTransId'     VALUE ft.file_trns_id,
                    'sequenceNr'      VALUE ft.sequence_nr,
                    'transferCd'      VALUE ft.transfer_cd,
                    'protocolNm'      VALUE ft.protocol_nm,
                    'transPrgNm'      VALUE ft.trans_prg_nm,
                    'ipPortCd'        VALUE ft.ip_port_cd,
                    'blockSizeNr'     VALUE ft.block_size_nr,
                    'convertFileCd'   VALUE ft.convert_file_cd,
                    'modeNm'          VALUE ft.mode_nm,
                    'securityNm'      VALUE ft.security_nm,
                    'xferFileNm'      VALUE ft.xfer_file_nm,
                    'ddNm'            VALUE ft.dd_nm,
                    'memberCd'        VALUE ft.member_cd,
                    'jobNm'           VALUE ft.job_nm,
                    'remoteFileNm'    VALUE ft.remote_file_nm,
                    'gatewayAccessCd' VALUE ft.gateway_access_cd,
                    'listenerSrvNm'   VALUE ft.listener_srv_nm,
                    'orgTypeCd'       VALUE ft.org_type_cd,
                    'programNm'       VALUE ft.program_nm,
                    'binFileCRLFInf'  VALUE ft.bin_file_CRLF_ind,
                    'controlFileNm'   VALUE ft.control_file_nm,
                    'recordLengthNr'  VALUE ft.record_lgth_nr,
                    'localFileNm'     VALUE ft.local_file_nm
                  )
                  FROM c3_transfer_parameters ft
                  WHERE ft.file_trns_id = rd.report_id
                )
              )
              FROM ADMIN_QUERY_LIST rd
              WHERE rd.report_id = ro.report_id
            )
          )
        )
        FROM CLIENT_REPORT_OPTIONS ro
        WHERE ro.client_id = c.client
      ), JSON '[]'),
      'sysPrinsPrefixes' VALUE COALESCE((
        SELECT JSON_ARRAYAGG(
          JSON_OBJECT(
            'billingSp'   VALUE spp.billing_sp,
            'prefix'      VALUE spp.prefix,
            'atmCashRule' VALUE spp.atm_cash_rule
          )
          ORDER BY spp.prefix
        )
        FROM sys_prins_prefix spp
        WHERE spp.BILLING_SP = c.billing_sp
      ), JSON '[]'),
      'clientEmail' VALUE COALESCE((
        SELECT JSON_ARRAYAGG(
          JSON_OBJECT(
            'clientId'       VALUE ce.client_id,
            'emailAddressTx' VALUE ce.email_address_tx,
            'reportId'       VALUE ce.report_id,
            'emailNameTx'    VALUE ce.email_name_tx,
            'carbonCopyFlag' VALUE ce.carbon_copy_flag,
            'activeFlag'     VALUE ce.active_flag,
            'mailServerId'   VALUE ce.mail_server_id
          )
          ORDER BY ce.report_id, ce.email_address_tx
        )
        FROM CLIENT_EMAIL ce
        WHERE ce.client_id = c.client
      ), JSON '[]'),
      'sysPrins' VALUE COALESCE((
        SELECT JSON_ARRAYAGG(
          JSON_OBJECT(
            'client'            VALUE sp.client,
            'sysPrin'           VALUE sp.sys_prin,
            'custType'          VALUE sp.cust_type,
            'undeliverable'     VALUE sp.undeliverable,
            'statA'             VALUE sp.stat_a,
            'statB'             VALUE sp.stat_b,
            'statC'             VALUE sp.stat_c,
            'statD'             VALUE sp.stat_d,
            'statE'             VALUE sp.stat_e,
            'statF'             VALUE sp.stat_f,
            'statI'             VALUE sp.stat_i,
            'statL'             VALUE sp.stat_l,
            'statO'             VALUE sp.stat_o,
            'statU'             VALUE sp.stat_u,
            'statX'             VALUE sp.stat_x,
            'statZ'             VALUE sp.stat_z,
            'poBox'             VALUE sp.po_box,
            'addrFlag'          VALUE sp.addr_flag,
            'tempAway'          VALUE sp.temp_away,
            'rps'               VALUE sp.rps,
            'session'           VALUE sp.session,
            'badState'          VALUE sp.bad_state,
            'astatRch'          VALUE sp.A_STAT_RCH,
            'nm13'              VALUE sp.NM_13,
            'tempAwayAtts'      VALUE sp.temp_away_atts,
            'reportMethod'      VALUE sp.report_method,
            'active'            VALUE sp.active,
            'notes'             VALUE sp.notes,
            'returnStatus'      VALUE sp.RET_STAT,
            'destroyStatus'     VALUE sp.DES_STAT,
            'nonUS'             VALUE sp.non_us,
            'special'           VALUE sp.special,
            'pinMailer'         VALUE sp.pin,
            'holdDays'          VALUE sp.hold_days,
            'forwardingAddress' VALUE sp.FORWARDING_ADDR,
            'contact'           VALUE sp.contact,
            'phone'             VALUE sp.phone,
            'entityCode'        VALUE sp.ENTITY_CD,
            'invalidDelivAreas' VALUE COALESCE((
              SELECT JSON_ARRAYAGG(
                JSON_OBJECT('area' VALUE ida.area, 'sysPrin' VALUE ida.sys_prin)
              )
              FROM invalid_deliv_areas ida
              WHERE ida.sys_prin = sp.sys_prin
            ), JSON '[]'),
            'vendorSentTo' VALUE COALESCE((
              SELECT JSON_ARRAYAGG(
                JSON_OBJECT(
                  'sysPrin'    VALUE vst.sys_prin,
                  'vendorId'   VALUE vst.vend_id,
                  'queForMail' VALUE vst.queformail_cd,
                  'vendor'     VALUE (
                    SELECT JSON_OBJECT(
                      'id'                 VALUE v.vend_id,
                      'name'               VALUE v.vend_nm,
                      'active'             VALUE v.vend_actv_cd,
                      'receiver'           VALUE v.vend_rcvr_cd,
                      'fileServerName'     VALUE v.vend_fsrv_nm,
                      'fileServerIp'       VALUE v.vend_fsrv_ip,
                      'fileServerUserId'   VALUE v.fsrvr_user_id,
                      'fileServerPassword' VALUE v.fsrvr_usr_pwd_tx,
                      'fileName'           VALUE v.fsrvr_file_name_tx,
                      'uncShare'           VALUE v.fsrvr_unc_share_tx,
                      'path'               VALUE v.fsrvr_path_tx,
                      'archivePath'        VALUE v.fsrvr_file_archive_path_tx,
                      'vendorTypeCode'     VALUE v.vendor_type_cd,
                      'fileIo'             VALUE v.vend_file_io,
                      'clientSpecific'     VALUE v.vend_client_specific,
                      'schedule'           VALUE v.vend_schedule,
                      'dateLastWorked'     VALUE v.vend_date_last_worked,
                      'fileSize'           VALUE v.vend_filesize,
                      'fileTransferSpecs'  VALUE v.vend_filetrans_specs,
                      'fileType'           VALUE v.vend_file_type,
                      'ftpPassive'         VALUE v.ftp_passive,
                      'ftpFileType'        VALUE v.ftp_filetype
                    )
                    FROM VENDOR v
                    WHERE v.vend_id = vst.vend_id
                  )
                )
              )
              FROM vendor_sent_to vst
              WHERE vst.sys_prin = sp.sys_prin
                AND EXISTS (
                  SELECT 1 FROM VENDOR vv
                  WHERE vv.vend_id = vst.vend_id AND vv.vend_file_io = 'I'
                )
            ), JSON '[]'),
            'vendorReceivedFrom' VALUE COALESCE((
              SELECT JSON_ARRAYAGG(
                JSON_OBJECT(
                  'sysPrin'    VALUE vrf.sys_prin,
                  'vendorId'   VALUE vrf.vend_id,
                  'queForMail' VALUE vrf.queformail_cd,
                  'vendor'     VALUE (
                    SELECT JSON_OBJECT(
                      'id'               VALUE v.vend_id,
                      'name'             VALUE v.vend_nm,
                      'active'           VALUE v.vend_actv_cd,
                      'receiver'         VALUE v.vend_rcvr_cd,
                      'fileServerName'   VALUE v.vend_fsrv_nm,
                      'fileServerIp'     VALUE v.vend_fsrv_ip,
                      'fileServerUserId' VALUE v.fsrvr_user_id,
                      'fileServerPassword' VALUE v.fsrvr_usr_pwd_tx,
                      'fileName'         VALUE v.fsrvr_file_name_tx,
                      'uncShare'         VALUE v.fsrvr_unc_share_tx,
                      'path'             VALUE v.fsrvr_path_tx,
                      'archivePath'      VALUE v.fsrvr_file_archive_path_tx,
                      'vendorTypeCode'   VALUE v.vendor_type_cd,
                      'fileIo'           VALUE v.vend_file_io,
                      'clientSpecific'   VALUE v.vend_client_specific,
                      'schedule'         VALUE v.vend_schedule,
                      'dateLastWorked'   VALUE v.vend_date_last_worked,
                      'fileSize'         VALUE v.vend_filesize,
                      'fileTransferSpecs'VALUE v.vend_filetrans_specs,
                      'fileType'         VALUE v.vend_file_type,
                      'ftpPassive'       VALUE v.ftp_passive,
                      'ftpFileType'      VALUE v.ftp_filetype
                    )
                    FROM VENDOR v
                    WHERE v.vend_id = vrf.vend_id AND v.vend_file_io = 'O'
                  )
                )
              )
              FROM vendor_sent_to vrf
              WHERE vrf.sys_prin = sp.sys_prin
                AND EXISTS (
                  SELECT 1 FROM VENDOR vv
                  WHERE vv.vend_id = vrf.vend_id AND vv.vend_file_io = 'O'
                )
            ), JSON '[]')
          )
        )
        FROM sys_prins sp
        WHERE sp.client = c.client
      ), JSON '[]')
    )
  ) AS full_json
  FROM (
    SELECT * FROM clients
    WHERE client IS NOT NULL
    ORDER BY client
    LIMIT ? OFFSET ?
  ) c]; SQL state [S0001]; error code [102]; Incorrect syntax near 'VALUE'.] with root cause

com.microsoft.sqlserver.jdbc.SQLServerException: Incorrect syntax near 'VALUE'.
        at com.microsoft.sqlserver.jdbc.SQLServerException.makeFromDatabaseError(SQLServerException.java:276) ~[mssql-jdbc-12.10.0.jre11.jar:na]
        at com.microsoft.sqlserver.jdbc.SQLServerStatement.getNextResult(SQLServerStatement.java:1787) ~[mssql-jdbc-12.10.0.jre11.jar:na]
        at com.microsoft.sqlserver.jdbc.SQLServerPreparedStatement.doExecutePreparedStatement(SQLServerPreparedStatement.java:688) ~[mssql-jdbc-12.10.0.jre11.jar:na]
        at com.microsoft.sqlserver.jdbc.SQLServerPreparedStatement$PrepStmtExecCmd.doExecute(SQLServerPreparedStatement.java:607) ~[mssql-jdbc-12.10.0.jre11.jar:na]
        at com.microsoft.sqlserver.jdbc.TDSCommand.execute(IOBuffer.java:7745) ~[mssql-jdbc-12.10.0.jre11.jar:na]
        at com.microsoft.sqlserver.jdbc.SQLServerConnection.executeCommand(SQLServerConnection.java:4700) ~[mssql-jdbc-12.10.0.jre11.jar:na]
        at com.microsoft.sqlserver.jdbc.SQLServerStatement.executeCommand(SQLServerStatement.java:321) ~[mssql-jdbc-12.10.0.jre11.jar:na]
        at com.microsoft.sqlserver.jdbc.SQLServerStatement.executeStatement(SQLServerStatement.java:253) ~[mssql-jdbc-12.10.0.jre11.jar:na]
        at com.microsoft.sqlserver.jdbc.SQLServerPreparedStatement.executeQuery(SQLServerPreparedStatement.java:521) ~[mssql-jdbc-12.10.0.jre11.jar:na]
        at com.zaxxer.hikari.pool.ProxyPreparedStatement.executeQuery(ProxyPreparedStatement.java:52) ~[HikariCP-6.3.0.jar:na]
