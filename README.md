STEP 1/9: FROM fmk-prod.nexus-ci.onefiserv.net/org/is/com.fiserv.issuer/fs-container-springboot-x86:1.1.31
STEP 2/9: ARG SERVICE_NAME
time="2025-08-07T18:57:40Z" level=warning msg="HEALTHCHECK is not supported for OCI image format and will be ignored. Must use `docker` format"
--> 950ec1b09ebf
STEP 3/9: ARG SERVICE_VERSION
time="2025-08-07T18:57:40Z" level=warning msg="HEALTHCHECK is not supported for OCI image format and will be ignored. Must use `docker` format"
--> 33153b670c0f
STEP 4/9: ARG UAID
time="2025-08-07T18:57:41Z" level=warning msg="HEALTHCHECK is not supported for OCI image format and will be ignored. Must use `docker` format"
--> 0a630960e331
STEP 5/9: ENV SERVICE_NAME=${SERVICE_NAME}
time="2025-08-07T18:57:41Z" level=warning msg="HEALTHCHECK is not supported for OCI image format and will be ignored. Must use `docker` format"
--> 61041dcddc0f
STEP 6/9: ENV SERVICE_VERSION=${SERVICE_VERSION}
time="2025-08-07T18:57:41Z" level=warning msg="HEALTHCHECK is not supported for OCI image format and will be ignored. Must use `docker` format"
--> e212c69ddff7
STEP 7/9: ENV JVM_ARGS="-Dfs.app.name=${SERVICE_NAME} -Dfs.app.version=${SERVICE_VERSION} -Dfs.app.uaid=${UAID} -Dlog4j.configurationFile=log4j2.xml"
time="2025-08-07T18:57:41Z" level=warning msg="HEALTHCHECK is not supported for OCI image format and will be ignored. Must use `docker` format"
--> c771655a0d15
STEP 8/9: COPY --chown=${RUNUSER}:0 app /app
time="2025-08-07T18:57:42Z" level=warning msg="HEALTHCHECK is not supported for OCI image format and will be ignored. Must use `docker` format"
--> 13f08b569e6d
STEP 9/9: ENTRYPOINT ["java","-Xmx1G","-Dserver.port=${PORT}","-Dfs.app.name=${SERVICE_NAME}","-Dfs.app.version=${SERVICE_VERSION}","-Dfs.app.uaid=${UAID}","-Dlog4j.configurationFile=log4j2.xml","-Djava.security.egd=file:/dev/./urandom","-cp","/app:/app/voltage/lib/vibesimplejava.jar:/app/BOOT-INF/classes:/app/BOOT-INF/lib/*","org.springframework.boot.loader.launch.JarLauncher"]
COMMIT fmk.nexus-ci.onefiserv.net/org/is/trace-client-sysprin-service:0.0.2
time="2025-08-07T18:57:42Z" level=warning msg="HEALTHCHECK is not supported for OCI image format and will be ignored. Must use `docker` format"
--> 9b33468057b8
Successfully tagged fmk.nexus-ci.onefiserv.net/org/is/trace-client-sysprin-service:0.0.2
9b33468057b8c7a7340cbe23f72334e953bd0f45a30c88a06603bce1a9a06a59
