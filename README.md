FROM fmk.nexus-ci.onefiserv.net/org/is/com.fiserv.issuer/fs-container-springboot-x86:3.0.8

USER root

ARG JAR_NAME
COPY target/${JAR_NAME} /app/apprapid.jar

RUN chgrp -R 0 /app && chmod -R g+rwX /app

VOLUME ["/app"]
WORKDIR /app

USER 1001

ENTRYPOINT ["java", "-Xmx1G",
            "-Dreactor.netty.http.server.accessLogEnabled=true",
            "-Djava.security.egd=file:/dev/./urandom",
            "-Duser.timezone=America/Toronto",
            "-jar", "/app/apprapid.jar"]


WARNING: Failed to pull image with policy "": image pull failed: failed to pull and unpack image "docker.io/library/eclipse-temurin-21-jre:latest": failed to resolve reference "docker.io/library/eclipse-temurin-21-jre:latest": failed to do request: Head "https://registry-1.docker.io/v2/library/eclipse-temurin-21-jre/manifests/latest": net/http: TLS handshake timeout
ERROR: Job failed: prepare environment: waiting for pod running: pulling image "eclipse-temurin-21-jre": image pull failed: failed to pull and unpack image "docker.io/library/eclipse-temurin-21-jre:latest": failed to resolve reference "docker.io/library/eclipse-temurin-21-jre:latest": failed to do request: Head "https://registry-1.docker.io/v2/library/eclipse-temurin-21-jre/manifests/latest": net/http: TLS handshake timeout. Check https://docs.gitlab.com/runner/shells/index.html#shell-profile-loading for more information
