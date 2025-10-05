Error starting ApplicationContext. To display the condition evaluation report re-run your application with 'debug' enabled.
2025-10-05T12:32:02.736-05:00 ERROR 23896 --- [client-sysprin-writer] [           main] o.s.boot.SpringApplication               : Application run failed

org.springframework.beans.factory.BeanCreationException: Error creating bean with name 'clientDetailDaoWithNativeSql': Injection of autowired dependencies failed
        at org.springframework.beans.factory.annotation.AutowiredAnnotationBeanPostProcessor.postProcessProperties(AutowiredAnnotationBeanPostProcessor.java:515) ~[spring-beans-6.2.7.jar:6.2.7]
        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.populateBean(AbstractAutowireCapableBeanFactory.java:1459) ~[spring-beans-6.2.7.jar:6.2.7]
        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.doCreateBean(AbstractAutowireCapableBeanFactory.java:606) ~[spring-beans-6.2.7.jar:6.2.7]
        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.createBean(AbstractAutowireCapableBeanFactory.java:529) ~[spring-beans-6.2.7.jar:6.2.7]
        at org.springframework.beans.factory.support.AbstractBeanFactory.lambda$doGetBean$0(AbstractBeanFactory.java:339) ~[spring-beans-6.2.7.jar:6.2.7]
        at org.springframework.beans.factory.support.DefaultSingletonBeanRegistry.getSingleton(DefaultSingletonBeanRegistry.java:373) ~[spring-beans-6.2.7.jar:6.2.7]
        at org.springframework.beans.factory.support.AbstractBeanFactory.doGetBean(AbstractBeanFactory.java:337) ~[spring-beans-6.2.7.jar:6.2.7]
        at org.springframework.beans.factory.support.AbstractBeanFactory.getBean(AbstractBeanFactory.java:202) ~[spring-beans-6.2.7.jar:6.2.7]
        at org.springframework.beans.factory.support.DefaultListableBeanFactory.instantiateSingleton(DefaultListableBeanFactory.java:1222) ~[spring-beans-6.2.7.jar:6.2.7]
        at org.springframework.beans.factory.support.DefaultListableBeanFactory.preInstantiateSingleton(DefaultListableBeanFactory.java:1188) 



@SpringBootApplication(scanBasePackages = {
        "rapid"
})
@EntityScan("rapid.model")
@EnableJpaRepositories(
        basePackages = "rapid.repository",
        excludeFilters = {
        // Exclude by concrete type(s)
        @ComponentScan.Filter(type = FilterType.ASSIGNABLE_TYPE, classes = {
                rapid.repository.client.ClientDetailDaoWithNativeSql.class
        }),
})
public class ClientSysPrinWriterApplication {

    public static void main(String[] args) {
        SpringApplication sa = new SpringApplication(ClientSysPrinWriterApplication.class);
        sa.run(args);
    }
}
