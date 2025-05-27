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
 
