<dependency>
    <groupId>com.ibm.mq</groupId>
    <artifactId>com.ibm.mq.allclient</artifactId>
    <version>9.3.3.0</version> <!-- adjust version -->
</dependency>
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-jms</artifactId>
</dependency>




ibm.mq.queue-manager=QMGR
ibm.mq.channel=DEV.APP.SVRCONN
ibm.mq.conn-name=hostname(1414)
ibm.mq.user=     # optional: leave blank if MQ allows unauthenticated
ibm.mq.password= # optional: leave blank



@Configuration
public class MqConfig {
    @Bean
    public ConnectionFactory connectionFactory() {
        MQConnectionFactory mqFactory = new MQConnectionFactory();
        try {
            mqFactory.setHostName("hostname");
            mqFactory.setPort(1414);
            mqFactory.setQueueManager("QMGR");
            mqFactory.setChannel("DEV.APP.SVRCONN");
            mqFactory.setTransportType(JMSC.MQJMS_TP_CLIENT_MQ_TCPIP);

            // Uncomment if credentials are required
            // mqFactory.setUserID("username");
            // mqFactory.setPassword("password");

        } catch (JMSException e) {
            e.printStackTrace();
        }
        return mqFactory;
    }

    @Bean
    public JmsTemplate jmsTemplate(ConnectionFactory connectionFactory) {
        return new JmsTemplate(connectionFactory);
    }
}




a1qvap1036
a1qvap1038
a3qvap1010
a3qvap1012
 
Caused by: com.ibm.mq.jmqi.JmqiException: CC=2;RC=2009;AMQ9204: Connection to host 'a1qvap1038.1dc.com(1414)' rejected. [1=com.ibm.mq.jmqi.JmqiExcep
tion[CC=2;RC=2009;AMQ9213: A communications error for 'TCP' occurred. [1=java.net.SocketException[Connection reset],4=TCP,5=sockInStream.read]],3=a1qvap1038.1dc.com(1414),4=,5=RemoteTCPConnection.receive]

Caused by: com.ibm.mq.MQException: JMSCMQ0001: IBM MQ call failed with compcode '2' ('MQCC_FAILED') reason '2009' ('MQRC_CONNECTION_BROKEN').       
        at com.ibm.msg.client.jakarta.wmq.common.internal.Reason.createException(Reason.java:203)
 
Caused by: com.ibm.msg.client.jakarta.jms.DetailedJMSException: JMSWMQ0018: Failed to connect to queue manager 'MI_OQA02' with connection mode 'Client' and host name 'a1qvap1038.1dc.com(1414)'.



SELECT TABLE_SCHEMA, TABLE_NAME, COLUMN_NAME
FROM INFORMATION_SCHEMA.COLUMNS
WHERE COLUMN_NAME = 'sys_prin'
ORDER BY TABLE_SCHEMA, TABLE_NAME;





Product	Category	CYCLE	Servers	IP 	PORT	QM Name	Cluster Name	Environment	Access	MQ Server
 
IBM MQ	Cluster	O-CYCLE	a1qvap1036	10.180.150.162	1414	MI_OQA01	ODSO	Dev	TPAM	8.0.0.4
IBM MQ	Cluster	O-CYCLE	a1qvap1038	10.180.150.152	1414	MI_OQA02 	ODSO	Dev	TPAM	8.0.0.4
IBM MQ	Cluster	O-CYCLE	a3qvap1010	10.174.148.189	1414	MI_CQA01	ODSO	Dev	TPAM	8.0.0.4
IBM MQ	Cluster	O-CYCLE	a3qvap1012	10.174.148.192	1414	MI_CQA02	ODSO	Dev	TPAM	8.0.0.4

QueueManager=;Server=odsmq-qao-oma.1dc.com(1414);Channel=RAPIDODS.SVRCONN;RequestQueue=RAPIDODS.RQST.OCYCLE.QUEUE;ReplyQueue=RAPIDODS.REPLY.MQAJ.QUEUE;User=dsfraud;Password=;


Test-NetConnection -ComputerName odsmq-qao-oma.1dc.com -Port 1414

AAA.



