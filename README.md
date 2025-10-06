2025-10-06T12:56:19.468-05:00 ERROR 33912 --- [client-sysprin-reader] [0.0-8083-exec-6] o.a.c.c.C.[.[.[/].[dispatcherServlet]    : Servlet.service() for servlet [dispatcherServlet] in context with path [] threw exception [Request processing failed: org.springframework.dao.EmptyResultDataAccessException: Incorrect result size: expected 1, actual 0] with root cause

org.springframework.dao.EmptyResultDataAccessException: Incorrect result size: expected 1, actual 0
        at org.springframework.dao.support.DataAccessUtils.nullableSingleResult(DataAccessUtils.java:194) ~[spring-tx-6.2.7.jar:6.2.7]
        at org.springframework.jdbc.core.namedparam.NamedParameterJdbcTemplate.queryForObject(NamedParameterJdbcTemplate.java:253) ~[spring-jdbc-6.2.7.jar:6.2.7]
        at org.springframework.jdbc.core.namedparam.NamedParameterJdbcTemplate.queryForObject(NamedParameterJdbcTemplate.java:269) ~[spring-jdbc-6.2.7.jar:6.2.7]
        at rapid.repository.client.SysPrinDetailDaoWithNativeSql.fetchSysPrinDetailFullJsonPage(SysPrinDetailDaoWithNativeSql.java:24) ~[common-model-0.0.1-SNAPSHOT.jar:na]
        at java.base/jdk.internal.reflect.DirectMethodHandleAccessor.invoke(DirectMethodHandleAccessor.java:104) ~[na:na]
        at java.base/java.lang.reflect.Method.invoke(Method.java:565) ~[na:na]
