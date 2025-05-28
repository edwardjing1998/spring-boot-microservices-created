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


<dependency>
    <groupId>com.ibm.mq</groupId>
    <artifactId>com.ibm.mq.allclient</artifactId>
    <version>9.3.4.0</version> <!-- Or compatible with your MQ version 8.0.0.4 -->
</dependency>
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-jms</artifactId>
</dependency>



<dependency>
    <groupId>com.ibm.mq</groupId>
    <artifactId>com.ibm.mq.allclient</artifactId>
    <version>9.3.4.0</version>
</dependency>



import com.ibm.mq.jms.MQQueueConnectionFactory;
import com.ibm.msg.client.wmq.WMQConstants;
import jakarta.jms.ConnectionFactory;
import jakarta.jms.JMSException;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

@Configuration
public class MqConfig {

    @Bean
    public ConnectionFactory mqConnectionFactory() throws JMSException {
        MQQueueConnectionFactory factory = new MQQueueConnectionFactory();
        factory.setHostName("your-mq-host");
        factory.setPort(1414);
        factory.setQueueManager("QMGR_NAME");
        factory.setChannel("CHANNEL.NAME");
        factory.setTransportType(WMQConstants.WMQ_CM_CLIENT);
        return factory;
    }
}



<dependency>
    <groupId>jakarta.jms</groupId>
    <artifactId>jakarta.jms-api</artifactId>
    <version>3.1.0</version> <!-- Adjust version as needed -->
</dependency>



package admin.config;

import com.ibm.mq.jms.MQQueueConnectionFactory;
import com.ibm.msg.client.wmq.WMQConstants;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.jms.annotation.EnableJms;
import org.springframework.jms.connection.UserCredentialsConnectionFactoryAdapter;
import org.springframework.jms.core.JmsTemplate;

import javax.jms.ConnectionFactory;

@Configuration
@EnableJms
public class MqConfig {

    @Bean
    public ConnectionFactory mqConnectionFactory() throws Exception {
        MQQueueConnectionFactory mqFactory = new MQQueueConnectionFactory();
        mqFactory.setHostName("odsmq-qao-oma.1dc.com"); // Your server
        mqFactory.setPort(1414);                        // Port
        mqFactory.setQueueManager("MI_OQA01");          // Use appropriate Queue Manager
        mqFactory.setChannel("RAPIDODS.SVRCONN");       // Channel
        mqFactory.setTransportType(WMQConstants.WMQ_CM_CLIENT);

        // Optional user credentials (if needed)
        UserCredentialsConnectionFactoryAdapter adapter = new UserCredentialsConnectionFactoryAdapter();
        adapter.setTargetConnectionFactory(mqFactory);
        adapter.setUsername("dsfraud");                // Provided User
        adapter.setPassword("");                      // Password if needed (empty here)
        return adapter;
    }

    @Bean
    public JmsTemplate jmsTemplate() throws Exception {
        JmsTemplate template = new JmsTemplate(mqConnectionFactory());
        template.setDefaultDestinationName("RAPIDODS.RQST.OCYCLE.QUEUE"); // Request Queue
        return template;
    }
}



package admin.config;

import com.ibm.mq.jms.MQQueueConnectionFactory;
import com.ibm.msg.client.wmq.WMQConstants;
import jakarta.jms.ConnectionFactory;
import jakarta.jms.JMSException;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

@Configuration
public class MqConfig {

    @Bean
    public ConnectionFactory mqConnectionFactory() throws JMSException, javax.jms.JMSException {
        MQQueueConnectionFactory factory = new MQQueueConnectionFactory();
        factory.setHostName("odsmq-qao-oma.1dc.com");
        factory.setPort(1414);
        factory.setQueueManager("MI_OQA01");
        factory.setChannel("RAPIDODS.SVRCONN");
        factory.setTransportType(WMQConstants.WMQ_CM_CLIENT);
        return (ConnectionFactory) factory;
    }
}



2025-05-27T17:54:46.647-05:00  INFO 37752 --- [           main] .s.b.a.l.ConditionEvaluationReportLogger : 

Error starting ApplicationContext. To display the condition evaluation report re-run your application with 'debug' enabled.
2025-05-27T17:54:46.670-05:00 ERROR 37752 --- [           main] o.s.boot.SpringApplication               : Application run failed

org.springframework.beans.factory.BeanCreationException: Error creating bean with name 'mqConnectionFactory' defined in class path resource [admin/config/MqConfig.class]: Failed to
 instantiate [jakarta.jms.ConnectionFactory]: Factory method 'mqConnectionFactory' threw exception with message: class com.ibm.mq.jms.MQQueueConnectionFactory cannot be cast to class jakarta.jms.ConnectionFactory (com.ibm.mq.jms.MQQueueConnectionFactory and jakarta.jms.ConnectionFactory are in unnamed module of loader 'app')
        at org.springframework.beans.factory.support.ConstructorResolver.instantiate(ConstructorResolver.java:657) ~[spring-beans-6.2.3.jar:6.2.3]
        at org.springframework.beans.factory.support.ConstructorResolver.instantiateUsingFactoryMethod(ConstructorResolver.java:489) ~[spring-beans-6.2.3.jar:6.2.3]
        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.instantiateUsingFactoryMethod(AbstractAutowireCapableBeanFactory.java:1361) ~[spring-beans-6.2.3.jar:6.2.3]
        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.createBeanInstance(AbstractAutowireCapableBeanFactory.java:1191) ~[spring-beans-6.2.3.jar:6.2.3]
        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.doCreateBean(AbstractAutowireCapableBeanFactory.java:563) ~[spring-beans-6.2.3.jar:6.2.3]   
        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.createBean(AbstractAutowireCapableBeanFactory.java:523) ~[spring-beans-6.2.3.jar:6.2.3]     
        at org.springframework.beans.factory.support.AbstractBeanFactory.lambda$doGetBean$0(AbstractBeanFactory.java:339) ~[spring-beans-6.2.3.jar:6.2.3]
        at org.springframework.beans.factory.support.DefaultSingletonBeanRegistry.getSingleton(DefaultSingletonBeanRegistry.java:346) ~[spring-beans-6.2.3.jar:6.2.3]
        at org.springframework.beans.factory.support.AbstractBeanFactory.doGetBean(AbstractBeanFactory.java:337) ~[spring-beans-6.2.3.jar:6.2.3]
        at org.springframework.beans.factory.support.AbstractBeanFactory.getBean(AbstractBeanFactory.java:202) ~[spring-beans-6.2.3.jar:6.2.3]
        at org.springframework.beans.factory.support.DefaultListableBeanFactory.instantiateSingleton(DefaultListableBeanFactory.java:1155) ~[spring-beans-6.2.3.jar:6.2.3]
        at org.springframework.beans.factory.support.DefaultListableBeanFactory.preInstantiateSingleton(DefaultListableBeanFactory.java:1121) ~[spring-beans-6.2.3.jar:6.2.3]       
        at org.springframework.beans.factory.support.DefaultListableBeanFactory.preInstantiateSingletons(DefaultListableBeanFactory.java:1056) ~[spring-beans-6.2.3.jar:6.2.3]      
        at org.springframework.context.support.AbstractApplicationContext.finishBeanFactoryInitialization(AbstractApplicationContext.java:987) ~[spring-context-6.2.3.jar:6.2.3]    
        at org.springframework.context.support.AbstractApplicationContext.refresh(AbstractApplicationContext.java:627) ~[spring-context-6.2.3.jar:6.2.3]
        at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.refresh(ServletWebServerApplicationContext.java:146) ~[spring-boot-3.4.3.jar:3.4.3]      
        at org.springframework.boot.SpringApplication.refresh(SpringApplication.java:752) ~[spring-boot-3.4.3.jar:3.4.3]
        at org.springframework.boot.SpringApplication.refreshContext(SpringApplication.java:439) ~[spring-boot-3.4.3.jar:3.4.3]
        at org.springframework.boot.SpringApplication.run(SpringApplication.java:318) ~[spring-boot-3.4.3.jar:3.4.3]
        at org.springframework.boot.SpringApplication.run(SpringApplication.java:1361) ~[spring-boot-3.4.3.jar:3.4.3]
        at org.springframework.boot.SpringApplication.run(SpringApplication.java:1350) ~[spring-boot-3.4.3.jar:3.4.3]
        at admin.RapidAdminApplication.main(RapidAdminApplication.java:12) ~[classes/:na]
Caused by: org.springframework.beans.BeanInstantiationException: Failed to instantiate [jakarta.jms.ConnectionFactory]: Factory method 'mqConnectionFactory' threw exception with me
ssage: class com.ibm.mq.jms.MQQueueConnectionFactory cannot be cast to class jakarta.jms.ConnectionFactory (com.ibm.mq.jms.MQQueueConnectionFactory and jakarta.jms.ConnectionFactory are in unnamed module of loader 'app')
        at org.springframework.beans.factory.support.SimpleInstantiationStrategy.lambda$instantiate$0(SimpleInstantiationStrategy.java:199) ~[spring-beans-6.2.3.jar:6.2.3]
        at org.springframework.beans.factory.support.SimpleInstantiationStrategy.instantiateWithFactoryMethod(SimpleInstantiationStrategy.java:88) ~[spring-beans-6.2.3.jar:6.2.3]  
        at org.springframework.beans.factory.support.SimpleInstantiationStrategy.instantiate(SimpleInstantiationStrategy.java:168) ~[spring-beans-6.2.3.jar:6.2.3]
        at org.springframework.beans.factory.support.ConstructorResolver.instantiate(ConstructorResolver.java:653) ~[spring-beans-6.2.3.jar:6.2.3]
        ... 21 common frames omitted
Caused by: java.lang.ClassCastException: class com.ibm.mq.jms.MQQueueConnectionFactory cannot be cast to class jakarta.jms.ConnectionFactory (com.ibm.mq.jms.MQQueueConnectionFactory and jakarta.jms.ConnectionFactory are in unnamed module of loader 'app')
        at admin.config.MqConfig.mqConnectionFactory(MqConfig.java:21) ~[classes/:na]
        at admin.config.MqConfig$$SpringCGLIB$$0.CGLIB$mqConnectionFactory$0(<generated>) ~[classes/:na]
        at admin.config.MqConfig$$SpringCGLIB$$FastClass$$1.invoke(<generated>) ~[classes/:na]
        at org.springframework.cglib.proxy.MethodProxy.invokeSuper(MethodProxy.java:258) ~[spring-core-6.2.3.jar:6.2.3]
        at org.springframework.context.annotation.ConfigurationClassEnhancer$BeanMethodInterceptor.intercept(ConfigurationClassEnhancer.java:372) ~[spring-context-6.2.3.jar:6.2.3] 
        at admin.config.MqConfig$$SpringCGLIB$$0.mqConnectionFactory(<generated>) ~[classes/:na]
        at java.base/jdk.internal.reflect.DirectMethodHandleAccessor.invoke(DirectMethodHandleAccessor.java:104) ~[na:na]
        at java.base/java.lang.reflect.Method.invoke(Method.java:565) ~[na:na]
        at org.springframework.beans.factory.support.SimpleInstantiationStrategy.lambda$instantiate$0(SimpleInstantiationStrategy.java:171) ~[spring-beans-6.2.3.jar:6.2.3]
        ... 24 common frames omitted

[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  26.229 s
[INFO] Finished at: 2025-05-27T17:54:46-05:00
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.springframework.boot:spring-boot-maven-plugin:3.4.3:run (default-cli) on project admin: Process terminated with exit code: 1 -> [Help 1]
[ERROR]
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR]
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/MojoExecutionException
PS C:\Users\F2LIPBX\spring_boot\2025-04-12\RAPIDadmin-microservices-java> 






package admin.controller;

import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

import javax.jms.Connection;
import javax.jms.ConnectionFactory;
import javax.jms.JMSException;
import java.util.HashMap;
import java.util.Map;

@RestController
public class MqTestController {

    private final ConnectionFactory connectionFactory;

    public MqTestController(ConnectionFactory connectionFactory) {
        this.connectionFactory = connectionFactory;
    }

    @GetMapping("/api/test-mq")
    public Map<String, String> testMqConnection() {
        Map<String, String> response = new HashMap<>();
        try (Connection connection = connectionFactory.createConnection()) {
            connection.start();
            response.put("status", "success");
            response.put("message", "✅ Successfully connected to IBM MQ.");
        } catch (JMSException e) {
            response.put("status", "failure");
            response.put("message", "❌ Failed to connect to IBM MQ: " + e.getMessage());
        }
        return response;
    }
}


{
  "message": "❌ Failed to connect to IBM MQ: JMSWMQ0018: Failed to connect to queue manager 'MI_OQA01' with connection mode 'Client' and host name 'odsmq-qao-oma.1dc.com(1414)'.",
  "status": "failure"
}
Resp



import org.springframework.context.annotation.Bean;
import org.springframework.jms.connection.UserCredentialsConnectionFactoryAdapter;
import org.springframework.jms.core.JmsTemplate;

@Bean
public UserCredentialsConnectionFactoryAdapter userCredentialsConnectionFactory(MQQueueConnectionFactory mqFactory) {
    UserCredentialsConnectionFactoryAdapter adapter = new UserCredentialsConnectionFactoryAdapter();
    adapter.setTargetConnectionFactory(mqFactory);
    adapter.setUsername("yourUsername");  // Replace with your MQ username
    adapter.setPassword("yourPassword");  // Replace with your MQ password
    return adapter;
}

@Bean
public JmsTemplate jmsTemplate(UserCredentialsConnectionFactoryAdapter userCredentialsConnectionFactory) {
    return new JmsTemplate(userCredentialsConnectionFactory);
}



package admin.config;

import com.ibm.mq.jms.MQQueueConnectionFactory;
import com.ibm.msg.client.wmq.WMQConstants;
import javax.jms.ConnectionFactory;
import javax.jms.JMSException;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

import org.springframework.jms.connection.UserCredentialsConnectionFactoryAdapter;
import org.springframework.jms.core.JmsTemplate;

@Configuration
public class MqConfig {

    @Bean
    public ConnectionFactory mqConnectionFactory() throws JMSException, javax.jms.JMSException {
        MQQueueConnectionFactory factory = new MQQueueConnectionFactory();
        factory.setHostName("odsmq-qao-oma.1dc.com");
        factory.setPort(1414);
        factory.setQueueManager("MI_OQA02");
        factory.setChannel("RAPIDODS.SVRCONN");
        factory.setTransportType(WMQConstants.WMQ_CM_CLIENT);
        return factory;
    }

    @Bean
    public UserCredentialsConnectionFactoryAdapter userCredentialsConnectionFactory(MQQueueConnectionFactory mqFactory) {
        UserCredentialsConnectionFactoryAdapter adapter = new UserCredentialsConnectionFactoryAdapter();
        adapter.setTargetConnectionFactory(mqFactory);
        adapter.setUsername("yourUsername");  // Replace with your MQ username
        adapter.setPassword("yourPassword");  // Replace with your MQ password
        return adapter;
    }

    @Bean
    public JmsTemplate jmsTemplate(UserCredentialsConnectionFactoryAdapter userCredentialsConnectionFactory) {
        return new JmsTemplate(userCredentialsConnectionFactory);
    }
}





package admin.config;

import com.ibm.mq.jms.MQConnectionFactory;
import com.ibm.msg.client.wmq.WMQConstants;
import javax.jms.ConnectionFactory;
import javax.jms.JMSException;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.jms.connection.UserCredentialsConnectionFactoryAdapter;
import org.springframework.jms.core.JmsTemplate;

@Configuration
public class MqConfig {

    @Bean
    public ConnectionFactory mqConnectionFactory() throws JMSException {
        MQConnectionFactory factory = new MQConnectionFactory();  // Use MQConnectionFactory instead of MQQueueConnectionFactory
        factory.setHostName("odsmq-qao-oma.1dc.com");
        factory.setPort(1414);
        factory.setQueueManager("MI_OQA02");
        factory.setChannel("RAPIDODS.SVRCONN");
        factory.setTransportType(WMQConstants.WMQ_CM_CLIENT);
        return factory;
    }

    @Bean
    public UserCredentialsConnectionFactoryAdapter userCredentialsConnectionFactory(ConnectionFactory mqFactory) {
        UserCredentialsConnectionFactoryAdapter adapter = new UserCredentialsConnectionFactoryAdapter();
        adapter.setTargetConnectionFactory(mqFactory);
        adapter.setUsername("yourUsername");  // Replace with actual MQ username
        adapter.setPassword("yourPassword");  // Replace with actual MQ password
        return adapter;
    }

    @Bean
    public JmsTemplate jmsTemplate(UserCredentialsConnectionFactoryAdapter userCredentialsConnectionFactory) {
        return new JmsTemplate(userCredentialsConnectionFactory);
    }
}




ng 'hibernate.dialect' (remove the property setting and it will be selected by default)
2025-05-27T19:01:28.935-05:00  INFO 26236 --- [           main] org.hibernate.orm.connections.pooling    : HHH10001005: Database info:
        Database JDBC URL [Connecting through datasource 'HikariDataSource (HikariPool-1)']
        Database driver: undefined/unknown
        Database version: 10.0
        Autocommit mode: undefined/unknown
        Isolation level: undefined/unknown
        Minimum pool size: undefined/unknown
        Maximum pool size: undefined/unknown
2025-05-27T19:01:30.734-05:00  INFO 26236 --- [           main] o.h.e.t.j.p.i.JtaPlatformInitiator       : HHH000489: No JTA platform available (set 'hibernate.transaction.jta.platform' to enable JTA platform integration)
2025-05-27T19:01:30.737-05:00  INFO 26236 --- [           main] j.LocalContainerEntityManagerFactoryBean : Initialized JPA EntityManagerFactory for persistence unit 'default'      
2025-05-27T19:01:31.299-05:00  INFO 26236 --- [           main] o.s.d.j.r.query.QueryEnhancerFactory     : Hibernate is in classpath; If applicable, HQL parser will be used.
Hibernate: select c1_0.client,c1_0.name from clients c1_0
Lucene indexing completed. Total indexed: 988
2025-05-27T19:01:35.504-05:00  WARN 26236 --- [           main] ConfigServletWebServerApplicationContext : Exception encountered during context initialization - cancelling refresh 
attempt: org.springframework.beans.factory.UnsatisfiedDependencyException: Error creating bean with name 'userCredentialsConnectionFactory' defined in class path resource [admin/co
nfig/MqConfig.class]: Unsatisfied dependency expressed through method 'userCredentialsConnectionFactory' parameter 0: Error creating bean with name 'userCredentialsConnectionFactory': Requested bean is currently in creation: Is there an unresolvable circular reference or an asynchronous initialization dependency?
2025-05-27T19:01:35.507-05:00  INFO 26236 --- [           main] j.LocalContainerEntityManagerFactoryBean : Closing JPA EntityManagerFactory for persistence unit 'default'
2025-05-27T19:01:35.511-05:00  INFO 26236 --- [           main] com.zaxxer.hikari.HikariDataSource       : HikariPool-1 - Shutdown initiated...
2025-05-27T19:01:36.311-05:00  INFO 26236 --- [           main] com.zaxxer.hikari.HikariDataSource       : HikariPool-1 - Shutdown completed.
2025-05-27T19:01:36.313-05:00  INFO 26236 --- [           main] o.apache.catalina.core.StandardService   : Stopping service [Tomcat]
2025-05-27T19:01:36.327-05:00  INFO 26236 --- [           main] .s.b.a.l.ConditionEvaluationReportLogger : 

Error starting ApplicationContext. To display the condition evaluation report re-run your application with 'debug' enabled.
2025-05-27T19:01:36.345-05:00 ERROR 26236 --- [           main] o.s.b.d.LoggingFailureAnalysisReporter   : 

***************************
APPLICATION FAILED TO START
***************************

Description:

The dependencies of some of the beans in the application context form a cycle:

ΓöîΓöÇΓöÇ->ΓöÇΓöÇΓöÉ
|  userCredentialsConnectionFactory defined in class path resource [admin/config/MqConfig.class]
ΓööΓöÇΓöÇ<-ΓöÇΓöÇΓöÿ


Action:

Relying upon circular references is discouraged and they are prohibited by default. Update your application to remove the dependency cycle between beans. As a last resort, it may be possible to break the cycle automatically by setting spring.main.allow-circular-references to true.

[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  29.501 s
[INFO] Finished at: 2025-05-27T19:01:36-05:00
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.springframework.boot:spring-boot-maven-plugin:3.4.3:run (default-cli) on project admin: Process terminated with exit code: 1 -> [Help 1]
[ERROR]
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR]
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/MojoExecutionException
PS C:\Users\F2LIPBX\spring_boot\2025-04-12\RAPIDadmin-microservices-java> 





package admin.config;

import com.ibm.mq.jms.MQConnectionFactory;
import com.ibm.msg.client.wmq.WMQConstants;
import jakarta.jms.ConnectionFactory; // Use jakarta.jms if using Spring Boot 3.4.x
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.jms.core.JmsTemplate;

@Configuration
public class MqConfig {

    @Bean
    public ConnectionFactory mqConnectionFactory() throws Exception {
        MQConnectionFactory factory = new MQConnectionFactory();
        factory.setHostName("odsmq-qao-oma.1dc.com");
        factory.setPort(1414);
        factory.setQueueManager("MI_OQA02");  // Use the correct QM
        factory.setChannel("RAPIDODS.SVRCONN");
        factory.setTransportType(WMQConstants.WMQ_CM_CLIENT);
        
        // If using user/pass, set them here
        factory.setStringProperty(WMQConstants.USERID, "dsfraud");
        factory.setStringProperty(WMQConstants.PASSWORD, ""); // Add password if required

        return factory;
    }

    @Bean
    public JmsTemplate jmsTemplate(ConnectionFactory connectionFactory) {
        return new JmsTemplate(connectionFactory);
    }
}
















