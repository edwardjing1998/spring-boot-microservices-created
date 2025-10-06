SELECT COALESCE((
        SELECT JSON_ARRAYAGG(
          JSON_OBJECT(
            'client'              VALUE sp.client,
            'sysPrin'             VALUE sp.sys_prin,
            'custType'            VALUE sp.cust_type,
            'undeliverable'       VALUE sp.undeliverable,
            'statA'               VALUE sp.stat_a,
            'statB'               VALUE sp.stat_b,
            'statC'               VALUE sp.stat_c,
            'statD'               VALUE sp.stat_d,
            'statE'               VALUE sp.stat_e,
            'statF'               VALUE sp.stat_f,
            'statI'               VALUE sp.stat_i,
            'statL'               VALUE sp.stat_l,
            'statO'               VALUE sp.stat_o,
            'statU'               VALUE sp.stat_u,
            'statX'               VALUE sp.stat_x,
            'statZ'               VALUE sp.stat_z,
            'poBox'               VALUE sp.po_box,
            'addrFlag'            VALUE sp.addr_flag,
            'tempAway'            VALUE sp.temp_away,
            'rps'                 VALUE sp.rps,
            'session'             VALUE sp.session,
            'badState'            VALUE sp.bad_state,
            'astatRch'            VALUE sp.A_STAT_RCH,
            'nm13'                VALUE sp.NM_13,
            'tempAwayAtts'        VALUE sp.temp_away_atts,
            'reportMethod'        VALUE sp.report_method,
            'active'              VALUE sp.active,
            'notes'               VALUE sp.notes,
            'returnStatus'        VALUE sp.RET_STAT,
            'destroyStatus'       VALUE sp.DES_STAT,
            'nonUS'               VALUE sp.non_us,
            'special'             VALUE sp.special,
            'pinMailer'           VALUE sp.pin,
            'holdDays'            VALUE sp.hold_days,
            'forwardingAddress'   VALUE sp.FORWARDING_ADDR,
            'contact'             VALUE sp.contact,
            'phone'               VALUE sp.phone,
            'entityCode'          VALUE sp.ENTITY_CD,

            /* invalidDelivAreas -> [] when none */
            'invalidDelivAreas'   VALUE COALESCE((
              SELECT JSON_ARRAYAGG(
                JSON_OBJECT(
                  'area'    VALUE ida.area,
                  'sysPrin' VALUE ida.sys_prin
                )
              )
              FROM invalid_deliv_areas ida
              WHERE ida.sys_prin = sp.sys_prin
            ), JSON '[]'),

            /* vendorSentTo: only vendors with IO='I' */
            'vendorSentTo'        VALUE COALESCE((
              SELECT JSON_ARRAYAGG(
                JSON_OBJECT(
                  'sysPrin'    VALUE vst.sys_prin,
                  'vendorId'   VALUE vst.vend_id,
                  'queForMail' VALUE vst.queformail_cd,
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
                      'fileTransferSpecs' VALUE v.vend_filetrans_specs,
                      'fileType'         VALUE v.vend_file_type,
                      'ftpPassive'       VALUE v.ftp_passive,
                      'ftpFileType'      VALUE v.ftp_filetype
                    )
                    FROM vendor v
                    WHERE v.vend_id = vst.vend_id
                      AND v.vend_file_io = 'I'
                  )
                )
              )
              FROM vendor_sent_to vst
              WHERE vst.sys_prin = sp.sys_prin
                AND EXISTS (
                  SELECT 1 FROM vendor vv
                  WHERE vv.vend_id = vst.vend_id AND vv.vend_file_io = 'I'
                )
            ), JSON '[]'),

            /* vendorReceivedFrom: only vendors with IO='O' */
            'vendorReceivedFrom'  VALUE COALESCE((
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
                      'fileTransferSpecs' VALUE v.vend_filetrans_specs,
                      'fileType'         VALUE v.vend_file_type,
                      'ftpPassive'       VALUE v.ftp_passive,
                      'ftpFileType'      VALUE v.ftp_filetype
                    )
                    FROM vendor v
                    WHERE v.vend_id = vrf.vend_id
                      AND v.vend_file_io = 'O'
                  )
                )
              )
              FROM vendor_sent_to vrf
              WHERE vrf.sys_prin = sp.sys_prin
                AND EXISTS (
                  SELECT 1 FROM vendor vv
                  WHERE vv.vend_id = vrf.vend_id AND vv.vend_file_io = 'O'
                )
            ), JSON '[]')
          )
        )
        FROM sys_prins sp
        WHERE sp.client = :client
          AND sp.sys_prin = :sysPrin
      ), JSON '[]') AS full_json;












