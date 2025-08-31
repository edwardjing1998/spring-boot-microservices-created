15:52:00.559 [main] INFO org.springframework.test.web.servlet.TestDispatcherServlet -- Completed initialization in 1 ms
[INFO] Tests run: 9, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 1.099 s -- in rapid.cases.web.TransactionControllerTest
[INFO] 
[INFO] Results:
[INFO]
[ERROR] Failures: 
[ERROR]   ReviewCaseControllerTest.getCaseByTransNo_notFound_returns404:91->lambda$getCaseByTransNo_notFound_returns404$0:93 
Expecting actual throwable to be an instance of:                                                                                                                                    
  rapid.cases.exception.CaseNotFoundException                                                                                                                                       
but was:                                                                                                                                                                            
  org.springframework.web.servlet.NoHandlerFoundException: No endpoint GET /cases/by-transno.                                                                                       
        at org.springframework.web.servlet.DispatcherServlet.noHandlerFound(DispatcherServlet.java:1305)                                                                            
        at org.springframework.web.servlet.DispatcherServlet.doDispatch(DispatcherServlet.java:1067)                                                                                
        at org.springframework.web.servlet.DispatcherServlet.doService(DispatcherServlet.java:979)                                                                                  
        ...(84 remaining lines not displayed - this can be changed with Assertions.setMaxStackTraceElementsDisplayed)                                                               
[ERROR]   ReviewCaseControllerTest.getCaseByTransNo_success:78 Status expected:<200> but was:<404>
[INFO]
[ERROR] Tests run: 35, Failures: 2, Errors: 0, Skipped: 0
