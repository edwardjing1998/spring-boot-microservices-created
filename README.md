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



    configure/orm/jpa/HibernateJpaConfiguration.class]: Embeddable class 'admin.model.DeliveryTypeId' may not have a property annotated '@Id' since it is used by 'admin.model.DeliveryType.id' as an '@EmbeddedId'
2025-06-02T15:50:59.152-05:00  INFO 24768 --- [           main] o.apache.catalina.core.StandardService   : Stopping service [Tomcat]
2025-06-02T15:50:59.173-05:00  INFO 24768 --- [           main] .s.b.a.l.ConditionEvaluationReportLogger : 

Error starting ApplicationContext. To display the condition evaluation report re-run your application with 'debug' enabled.
2025-06-02T15:50:59.205-05:00 ERROR 24768 --- [           main] o.s.boot.SpringApplication               : Application run failed

org.springframework.beans.factory.BeanCreationException: Error creating bean with name 'entityManagerFactory' defined in class path resource [org/springframework/boot/autoconfigure
/orm/jpa/HibernateJpaConfiguration.class]: Embeddable class 'admin.model.DeliveryTypeId' may not have a property annotated '@Id' since it is used by 'admin.model.DeliveryType.id' as an '@EmbeddedId'
        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.initializeBean(AbstractAutowireCapableBeanFactory.java:1812) ~[spring-beans-6.2.3.jar:6.2.3]
        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.doCreateBean(AbstractAutowireCapableBeanFactory.java:601) ~[spring-beans-6.2.3.jar:6.2.3]   
        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.createBean(AbstractAutowireCapableBeanFactory.java:523) ~[spring-beans-6.2.3.jar:6.2.3]     
        at org.springframework.beans.factory.support.AbstractBeanFactory.lambda$doGetBean$0(AbstractBeanFactory.java:339) ~[spring-beans-6.2.3.jar:6.2.3]
        at org.springframework.beans.factory.support.DefaultSingletonBeanRegistry.getSingleton(DefaultSingletonBeanRegistry.java:346) ~[spring-beans-6.2.3.jar:6.2.3]
        at org.springframework.beans.factory.support.AbstractBeanFactory.doGetBean(AbstractBeanFactory.java:337) ~[spring-beans-6.2.3.jar:6.2.3]
        at org.springframework.beans.factory.support.AbstractBeanFactory.getBean(AbstractBeanFactory.java:207) ~[spring-beans-6.2.3.jar:6.2.3]
        at org.springframework.context.support.AbstractApplicationContext.finishBeanFactoryInitialization(AbstractApplicationContext.java:970) ~[spring-context-6.2.3.jar:6.2.3]    
        at org.springframework.context.support.AbstractApplicationContext.refresh(AbstractApplicationContext.java:627) ~[spring-context-6.2.3.jar:6.2.3]
        at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.refresh(ServletWebServerApplicationContext.java:146) ~[spring-boot-3.4.3.jar:3.4.3]      
        at org.springframework.boot.SpringApplication.refresh(SpringApplication.java:752) ~[spring-boot-3.4.3.jar:3.4.3]
        at org.springframework.boot.SpringApplication.refreshContext(SpringApplication.java:439) ~[spring-boot-3.4.3.jar:3.4.3]
        at org.springframework.boot.SpringApplication.run(SpringApplication.java:318) ~[spring-boot-3.4.3.jar:3.4.3]
        at org.springframework.boot.SpringApplication.run(SpringApplication.java:1361) ~[spring-boot-3.4.3.jar:3.4.3]
        at org.springframework.boot.SpringApplication.run(SpringApplication.java:1350) ~[spring-boot-3.4.3.jar:3.4.3]
        at admin.RapidAdminApplication.main(RapidAdminApplication.java:12) ~[classes/:na]
Caused by: org.hibernate.AnnotationException: Embeddable class 'admin.model.DeliveryTypeId' may not have a property annotated '@Id' since it is used by 'admin.model.DeliveryType.id' as an '@EmbeddedId'
        at org.hibernate.boot.model.internal.EmbeddableBinder.checkEmbeddedId(EmbeddableBinder.java:269) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.boot.model.internal.EmbeddableBinder.bindEmbeddable(EmbeddableBinder.java:216) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.boot.model.internal.EmbeddableBinder.createCompositeBinder(EmbeddableBinder.java:137) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.boot.model.internal.PropertyBinder.bindBasic(PropertyBinder.java:1098) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.boot.model.internal.PropertyBinder.bindProperty(PropertyBinder.java:913) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.boot.model.internal.PropertyBinder.buildProperty(PropertyBinder.java:811) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.boot.model.internal.PropertyBinder.processElementAnnotations(PropertyBinder.java:732) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.boot.model.internal.EntityBinder.processIdPropertiesIfNotAlready(EntityBinder.java:1088) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.boot.model.internal.EntityBinder.handleIdentifier(EntityBinder.java:419) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.boot.model.internal.EntityBinder.bindEntityClass(EntityBinder.java:251) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.boot.model.internal.AnnotationBinder.bindClass(AnnotationBinder.java:401) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.boot.model.source.internal.annotations.AnnotationMetadataSourceProcessorImpl.processEntityHierarchies(AnnotationMetadataSourceProcessorImpl.java:257) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.boot.model.process.spi.MetadataBuildingProcess$1.processEntityHierarchies(MetadataBuildingProcess.java:281) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]  
        at org.hibernate.boot.model.process.spi.MetadataBuildingProcess.complete(MetadataBuildingProcess.java:324) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.hibernate.jpa.boot.internal.EntityManagerFactoryBuilderImpl.metadata(EntityManagerFactoryBuilderImpl.java:1442) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]        
        at org.hibernate.jpa.boot.internal.EntityManagerFactoryBuilderImpl.build(EntityManagerFactoryBuilderImpl.java:1513) ~[hibernate-core-6.6.8.Final.jar:6.6.8.Final]
        at org.springframework.orm.jpa.vendor.SpringHibernateJpaPersistenceProvider.createContainerEntityManagerFactory(SpringHibernateJpaPersistenceProvider.java:66) ~[spring-orm-6.2.3.jar:6.2.3]
        at org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean.createNativeEntityManagerFactory(LocalContainerEntityManagerFactoryBean.java:390) ~[spring-orm-6.2.3.jar:6.2.3]
        at org.springframework.orm.jpa.AbstractEntityManagerFactoryBean.buildNativeEntityManagerFactory(AbstractEntityManagerFactoryBean.java:419) ~[spring-orm-6.2.3.jar:6.2.3]    
        at org.springframework.orm.jpa.AbstractEntityManagerFactoryBean.afterPropertiesSet(AbstractEntityManagerFactoryBean.java:400) ~[spring-orm-6.2.3.jar:6.2.3]
        at org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean.afterPropertiesSet(LocalContainerEntityManagerFactoryBean.java:366) ~[spring-orm-6.2.3.jar:6.2.3]     
        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.invokeInitMethods(AbstractAutowireCapableBeanFactory.java:1859) ~[spring-beans-6.2.3.jar:6.2.3]
        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.initializeBean(AbstractAutowireCapableBeanFactory.java:1808) ~[spring-beans-6.2.3.jar:6.2.3]
        ... 15 common frames omitted

[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  24.745 s
[INFO] Finished at: 2025-06-02T15:50:59-05:00
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.springframework.boot:spring-boot-maven-plugin:3.4.3:run (default-cli) on project admin: Process terminated with exit code: 1 -> [Help 1]
[ERROR]
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR]
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/MojoExecutionException
PS C:\Users\F2LIPBX\sprin

