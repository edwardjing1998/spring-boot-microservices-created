Hi Everyone 
 
if any one Idea about those errors can you please help me.
 
I got same errors, I had tried 4 servers.
 
a1qvap1036

a1qvap1038

a3qvap1010

a3qvap1012
 
Caused by: com.ibm.mq.jmqi.JmqiException: CC=2;RC=2009;AMQ9204: Connection to host 'a1qvap1038.1dc.com(1414)' rejected. [1=com.ibm.mq.jmqi.JmqiExcep

tion[CC=2;RC=2009;AMQ9213: A communications error for 'TCP' occurred. [1=java.net.SocketException[Connection reset],4=TCP,5=sockInStream.read]],3=a1qvap1038.1dc.com(1414),4=,5=RemoteTCPConnection.receive]

Caused by: com.ibm.mq.MQException: JMSCMQ0001: IBM MQ call failed with compcode '2' ('MQCC_FAILED') reason '2009' ('MQRC_CONNECTION_BROKEN').       

        at com.ibm.msg.client.jakarta.wmq.common.internal.Reason.createException(Reason.java:203)
 
Caused by: com.ibm.msg.client.jakarta.jms.DetailedJMSException: JMSWMQ0018: Failed to connect to queue manager 'MI_OQA02' with connection mode 'Client' and host name 'a1qvap1038.1dc.com(1414)'.
 
telnet a1qvap1038.1dc.com 1414


Test-NetConnection -ComputerName a1qvap1038.1dc.com -Port 1414

Test-NetConnection -ComputerName a1qvap1038.1dc.com -Port 1414

netstat -an | grep 1414
telnet a1qvap1038.1dc.com 1414

Test-NetConnection -ComputerName a1qvap1038.1dc.com -Port 1414

nc -vz a1qvap1038.1dc.com 1414


unt,account_tokenid,active,as400_client_id,as400_system_id,auto_date,barcode_type_cd,bsc_spplmntl_id,contact_cd,contact_ph_nr,cust_id,cust_id2,customer_id,cycle,delivery_id,disposi
tion,entity_cd,file_sent,final_action_cards_nr,first_name,frst_updt_vend_id,hm_phone,in_date,in_hour,issuance_cd,issuance_dt,issued_by_amex,last_name,mailer_id,mkt_cd,ml_mthd,ms_is
sue_date,msg_id,next_date,num_cards,operator_cd,orig_ml_dt,out_date,pi_id,pi_id_tokenid,pi_status,postage_billed,primary_pi_id,primary_pi_id_tokenid,reason,rec_typ_tx,return_reason
_cd,role_cd,source_file,srvc_typ_tx,status,subreason,sys_prin,wk_phone,workstation_name_tx,case_number) values (?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?)]
        at org.springframework.orm.jpa.vendor.HibernateJpaDialect.convertHibernateAccessException(HibernateJpaDialect.java:293) ~[spring-orm-6.2.3.jar:6.2.3]
        at org.springframework.orm.jpa.vendor.HibernateJpaDialect.translateExceptionIfPossible(HibernateJpaDialect.java:241) ~[spring-orm-6.2.3.jar:6.2.3]
        at org.springframework.orm.jpa.JpaTransactionManager.doCommit(JpaTransactionManager.java:566) ~[spring-orm-6.2.3.jar:6.2.3]
        at org.springframework.transaction.support.AbstractPlatformTransactionManager.processCommit(AbstractPlatformTransactionManager.java:795) ~[spring-tx-6.2.3.jar:6.2.3]       
        at org.springframework.transaction.support.AbstractPlatformTransactionManager.commit(AbstractPlatformTransactionManager.java:758) ~[spring-tx-6.2.3.jar:6.2.3]
        at org.springframework.transaction.interceptor.TransactionAspectSupport.commitTransactionAfterReturning(TransactionAspectSupport.java:698) ~[spring-tx-6.2.3.jar:6.2.3]     
        at org.springframework.transaction.interceptor.TransactionAspectSupport.invokeWithinTransaction(TransactionAspectSupport.java:416) ~[spring-tx-6.2.3.jar:6.2.3]
        at org.springframework.transaction.interceptor.TransactionInterceptor.invoke(TransactionInterceptor.java:119) ~[spring-tx-6.2.3.jar:6.2.3]
        at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:184) ~[spring-aop-6.2.3.jar:6.2.3]
        at org.springframework.dao.support.PersistenceExceptionTranslationInterceptor.invoke(PersistenceExceptionTranslationInterceptor.java:138) ~[spring-tx-6.2.3.jar:6.2.3]      
        at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:184) ~[spring-aop-6.2.3.jar:6.2.3]
        at org.springframework.data.jpa.repository.support.CrudMethodMetadataPostProcessor$CrudMethodMetadataPopulatingMethodInterceptor.invoke(CrudMethodMetadataPostProcessor.java:165) ~[spring-data-jpa-3.4.3.jar:3.4.3]
        at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:184) ~[spring-aop-6.2.3.jar:6.2.3]
        at org.springframework.aop.framework.JdkDynamicAopProxy.invoke(JdkDynamicAopProxy.java:223) ~[spring-aop-6.2.3.jar:6.2.3]
        at jdk.proxy2/jdk.proxy2.$Proxy155.saveAll(Unknown Source) ~[na:na]
        at admin.config.data.CaseDataGenerator.generateCases(CaseDataGenerator.java:142) ~[classes/:na]
        at admin.config.data.DataGenerationOrchestrator.runDataGeneration(DataGenerationOrchestrator.java:32) ~[classes/:na]
        at java.base/jdk.internal.reflect.DirectMethodHandleAccessor.invoke(DirectMethodHandleAccessor.java:104) ~[na:na]
        at java.base/java.lang.reflect.Method.invoke(Method.java:565) ~[na:na]
        at org.springframework.beans.factory.annotation.InitDestroyAnnotationBeanPostProcessor$LifecycleMethod.invoke(InitDestroyAnnotationBeanPostProcessor.java:457) ~[spring-beans-6.2.3.jar:6.2.3]
        at org.springframework.beans.factory.annotation.InitDestroyAnnotationBeanPostProcessor$LifecycleMetadata.invokeInitMethods(InitDestroyAnnotationBeanPostProcessor.java:401) ~[spring-beans-6.2.3.jar:6.2.3]
        at org.springframework.beans.factory.annotation.InitDestroyAnnotationBeanPostProcessor.postProcessBeforeInitialization(InitDestroyAnnotationBeanPostProcessor.java:219) ~[spring-beans-6.2.3.jar:6.2.3]
        ... 20 common frames omitted
Caused by: org.hibernate.exception.DataException: could not execute statement [Value too long for column "SYS_PRIN CHARACTER(8)": "'SP0000000003' (12)"; SQL statement:
insert into cases (account,account_tokenid,active,as400_client_id,as400_system_id,auto_date,barcode_type_cd,bsc_spplmntl_id,contact_cd,contact_ph_nr,cust_id,cust_id2,customer_id,cy
cle,delivery_id,disposition,entity_cd,file_sent,final_action_cards_nr,first_name,frst_updt_vend_id,hm_phone,in_date,in_hour,issuance_cd,issuance_dt,issued_by_amex,last_name,mailer_
id,mkt_cd,ml_mthd,ms_issue_date,msg_id,next_date,num_cards,operator_cd,orig_ml_dt,out_date,pi_id,pi_id_tokenid,pi_status,postage_billed,primary_pi_id,primary_pi_id_tokenid,reason,r
ec_typ_tx,return_reason_cd,role_cd,source_file,srvc_typ_tx,status,subreason,sys_prin,wk_phone,workstation_name_tx,case_number) values (?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?
,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?) [22001-232]] [insert into cases (account,account_tokenid,active,as400_client_id,as400_system_id,auto_date,barcod
e_type_cd,bsc_spplmntl_id,contact_cd,contact_ph_nr,cust_id,cust_id2,customer_id,cycle,delivery_id,disposition,entity_cd,file_sent,final_action_cards_nr,first_name,frst_updt_vend_id
,hm_phone,in_date,in_hour,issuance_cd,issuance_dt,issued_by_amex,last_name,mailer_id,mkt_cd,ml_mthd,ms_issue_date,msg_id,next_date,num_cards,operator_cd,orig_ml_dt,out_date,pi_id,p
i_id_tokenid,pi_status,postage_billed,primary_pi_id,primary_pi_id_tokenid,reason,rec_typ_tx,return_reason_cd,role_cd,source_file,srvc_typ_tx,status,subreason,sys_prin,wk_phone,workstation_name_tx,case_number) values (?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?)]
        at org.hibernate.exception.internal.SQLExceptionTypeDelegate.convert(SQLExceptionTypeDelegate.java:55) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.exception.internal.StandardSQLExceptionConverter.convert(StandardSQLExceptionConverter.java:58) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.engine.jdbc.spi.SqlExceptionHelper.convert(SqlExceptionHelper.java:108) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.engine.jdbc.internal.ResultSetReturnImpl.executeUpdate(ResultSetReturnImpl.java:197) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.engine.jdbc.mutation.internal.AbstractMutationExecutor.performNonBatchedMutation(AbstractMutationExecutor.java:134) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.engine.jdbc.mutation.internal.MutationExecutorSingleNonBatched.performNonBatchedOperations(MutationExecutorSingleNonBatched.java:55) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.engine.jdbc.mutation.internal.AbstractMutationExecutor.execute(AbstractMutationExecutor.java:55) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.persister.entity.mutation.InsertCoordinatorStandard.doStaticInserts(InsertCoordinatorStandard.java:194) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]      
        at org.hibernate.persister.entity.mutation.InsertCoordinatorStandard.coordinateInsert(InsertCoordinatorStandard.java:132) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]     
        at org.hibernate.persister.entity.mutation.InsertCoordinatorStandard.insert(InsertCoordinatorStandard.java:104) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.action.internal.EntityInsertAction.execute(EntityInsertAction.java:110) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.engine.spi.ActionQueue.executeActions(ActionQueue.java:644) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.engine.spi.ActionQueue.executeActions(ActionQueue.java:511) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.event.internal.AbstractFlushingEventListener.performExecutions(AbstractFlushingEventListener.java:414) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]       
        at org.hibernate.event.internal.DefaultFlushEventListener.onFlush(DefaultFlushEventListener.java:41) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.event.service.internal.EventListenerGroupImpl.fireEventOnEachListener(EventListenerGroupImpl.java:127) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]       
        at org.hibernate.internal.SessionImpl.doFlush(SessionImpl.java:1429) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.internal.SessionImpl.managedFlush(SessionImpl.java:491) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.internal.SessionImpl.flushBeforeTransactionCompletion(SessionImpl.java:2354) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.internal.SessionImpl.beforeTransactionCompletion(SessionImpl.java:1978) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.engine.jdbc.internal.JdbcCoordinatorImpl.beforeTransactionCompletion(JdbcCoordinatorImpl.java:439) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.resource.transaction.backend.jdbc.internal.JdbcResourceLocalTransactionCoordinatorImpl.beforeCompletionCallback(JdbcResourceLocalTransactionCoordinatorImpl.java:169) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.resource.transaction.backend.jdbc.internal.JdbcResourceLocalTransactionCoordinatorImpl$TransactionDriverControlImpl.commit(JdbcResourceLocalTransactionCoordinatorImpl.java:267) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.engine.transaction.internal.TransactionImpl.commit(TransactionImpl.java:101) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.springframework.orm.jpa.JpaTransactionManager.doCommit(JpaTransactionManager.java:562) ~[spring-orm-6.2.3.jar:6.2.3]
        ... 39 common frames omitted
Caused by: org.h2.jdbc.JdbcSQLDataException: Value too long for column "SYS_PRIN CHARACTER(8)": "'SP0000000003' (12)"; SQL statement:
insert into cases (account,account_tokenid,active,as400_client_id,as400_system_id,auto_date,barcode_type_cd,bsc_spplmntl_id,contact_cd,contact_ph_nr,cust_id,cust_id2,customer_id,cy
cle,delivery_id,disposition,entity_cd,file_sent,final_action_cards_nr,first_name,frst_updt_vend_id,hm_phone,in_date,in_hour,issuance_cd,issuance_dt,issued_by_amex,last_name,mailer_
id,mkt_cd,ml_mthd,ms_issue_date,msg_id,next_date,num_cards,operator_cd,orig_ml_dt,out_date,pi_id,pi_id_tokenid,pi_status,postage_billed,primary_pi_id,primary_pi_id_tokenid,reason,r
ec_typ_tx,return_reason_cd,role_cd,source_file,srvc_typ_tx,status,subreason,sys_prin,wk_phone,workstation_name_tx,case_number) values (?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?,?) [22001-232]
        at org.h2.message.DbException.getJdbcSQLException(DbException.java:518) ~[h2-2.3.232.jar:2.3.232]
        at org.h2.message.DbException.getJdbcSQLException(DbException.java:489) ~[h2-2.3.232.jar:2.3.232]
        at org.h2.message.DbException.get(DbException.java:223) ~[h2-2.3.232.jar:2.3.232]
        at org.h2.message.DbException.getValueTooLongException(DbException.java:334) ~[h2-2.3.232.jar:2.3.232]
        at org.h2.value.Value.getValueTooLongException(Value.java:2612) ~[h2-2.3.232.jar:2.3.232]
        at org.h2.value.Value.convertToChar(Value.java:1250) ~[h2-2.3.232.jar:2.3.232]
        at org.h2.value.Value.convertTo(Value.java:1141) ~[h2-2.3.232.jar:2.3.232]
        at org.h2.value.Value.convertForAssignTo(Value.java:1118) ~[h2-2.3.232.jar:2.3.232]
        at org.h2.table.Column.validateConvertUpdateSequence(Column.java:406) ~[h2-2.3.232.jar:2.3.232]
        at org.h2.table.Table.convertInsertRow(Table.java:963) ~[h2-2.3.232.jar:2.3.232]
        at org.h2.command.dml.Insert.insertRows(Insert.java:167) ~[h2-2.3.232.jar:2.3.232]
        at org.h2.command.dml.Insert.update(Insert.java:135) ~[h2-2.3.232.jar:2.3.232]
        at org.h2.command.dml.DataChangeStatement.update(DataChangeStatement.java:74) ~[h2-2.3.232.jar:2.3.232]
        at org.h2.command.CommandContainer.update(CommandContainer.java:139) ~[h2-2.3.232.jar:2.3.232]
        at org.h2.command.Command.executeUpdate(Command.java:304) ~[h2-2.3.232.jar:2.3.232]
        at org.h2.command.Command.executeUpdate(Command.java:248) ~[h2-2.3.232.jar:2.3.232]
        at org.h2.jdbc.JdbcPreparedStatement.executeUpdateInternal(JdbcPreparedStatement.java:213) ~[h2-2.3.232.jar:2.3.232]
        at org.h2.jdbc.JdbcPreparedStatement.executeUpdate(JdbcPreparedStatement.java:172) ~[h2-2.3.232.jar:2.3.232]
        at com.zaxxer.hikari.pool.ProxyPreparedStatement.executeUpdate(ProxyPreparedStatement.java:61) ~[HikariCP-5.1.0.jar:na]
        at com.zaxxer.hikari.pool.HikariProxyPreparedStatement.executeUpdate(HikariProxyPreparedStatement.java) ~[HikariCP-5.1.0.jar:na]
        at org.hibernate.engine.jdbc.internal.ResultSetReturnImpl.executeUpdate(ResultSetReturnImpl.java:194) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        ... 60 common frames omitted

[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  17.743 s
[INFO] Finished at: 2025-05-27T10:44:00-05:00
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.springframework.boot:spring-boot-maven-plugin:3.4.3:run (default-cli) on project admin: Process terminated with exit code: 1 -> [Help 1]
[ERROR]
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR]
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/MojoExecutionException
PS C:\Users\F2LIPBX\spring_boot\2025-04-12\RAPIDadmin-microservices-java> 





