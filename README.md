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
