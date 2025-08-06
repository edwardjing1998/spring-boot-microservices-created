FROM fmk.nexus-ci.onefiserv.net/org/is/com.fiserv.issuer/fs-container-springboot-x86:3.0.8

USER root

# Copy the jar from the local build context (target folder)
COPY target/admin-0.0.1-SNAPSHOT.jar /app/apprapid.jar

RUN chgrp -R 0 /app && chmod -R g+rwX /app

VOLUME ["/app"]
WORKDIR /app

USER 1001

ENTRYPOINT ["java", "-Xmx1G",
            "-Dreactor.netty.http.server.accessLogEnabled=true",
            "-Djava.security.egd=file:/dev/./urandom",
            "-Duser.timezone=America/Toronto",
            "-jar", "/app/apprapid.jar"]




            CVSS score: 8, CVSS exploitability score: 1.3
            Fixed version: 2.43.7-1.el8_10
        CVE-2025-48385, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:11534
            CVSS score: 8.6
            Fixed version: 2.43.7-1.el8_10
        CVE-2018-1000021, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2018-1000021
            CVSS score: 5, CVSS exploitability score: 1.6
        CVE-2024-52005, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:8414
            CVSS score: 7.5
            Fixed version: 2.43.5-3.el8_10
        CVE-2025-27613, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:11534
            CVSS score: 3.6, CVSS exploitability score: 1.8
            Fixed version: 2.43.7-1.el8_10
        CVE-2025-27614, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:11534
            CVSS score: 8.6, CVSS exploitability score: 1.8
            Fixed version: 2.43.7-1.el8_10
        CVE-2025-48386, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-48386
            CVSS score: 6.3, CVSS exploitability score: 1.8
        CVE-2024-50349, Severity: LOW, Source: https://access.redhat.com/errata/RHSA-2025:11534
            CVSS score: 2.1
            Fixed version: 2.43.7-1.el8_10
        CVE-2024-52006, Severity: LOW, Source: https://access.redhat.com/errata/RHSA-2025:11534
            CVSS score: 2.1
            Fixed version: 2.43.7-1.el8_10
        CVE-2025-46835, Severity: LOW, Source: https://access.redhat.com/errata/RHSA-2025:11534
            CVSS score: 8.5, CVSS exploitability score: 1.8
            Fixed version: 2.43.7-1.el8_10
    Name: glib-networking, Version: 2.56.1
        CVE-2020-13645, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2020-13645
            CVSS score: 6.5, CVSS exploitability score: 3.9
    Name: glib2, Version: 2.56.4
        CVE-2024-34397, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:11327
            CVSS score: 5.2, CVSS exploitability score: 0.9
            Fixed version: 2.56.4-166.el8_10
        CVE-2024-52533, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:11327
            CVSS score: 9.8, CVSS exploitability score: 3.9
            Fixed version: 2.56.4-166.el8_10
        CVE-2025-4373, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:11327
            CVSS score: 4.8, CVSS exploitability score: 2.2
            Fixed version: 2.56.4-166.el8_10
        CVE-2023-29499, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-29499
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2023-32611, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-32611
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2023-32636, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-32636
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2023-32665, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-32665
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2025-3360, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2025-3360
            CVSS score: 3.7, CVSS exploitability score: 2.2
    Name: glibc, Version: 2.28
        CVE-2025-0395, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:3828
            CVSS score: 7.5, CVSS exploitability score: 3.9
            Fixed version: 2.28-251.el8_10.16
        CVE-2025-4802, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:8686
            CVSS score: 7.8, CVSS exploitability score: 1.8
            Fixed version: 2.28-251.el8_10.22
        CVE-2025-8058, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:12980
            CVSS score: 5.9
            Fixed version: 2.28-251.el8_10.25
    Name: glibc-common, Version: 2.28
        CVE-2025-0395, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:3828
            CVSS score: 7.5, CVSS exploitability score: 3.9
            Fixed version: 2.28-251.el8_10.16
        CVE-2025-4802, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:8686
            CVSS score: 7.8, CVSS exploitability score: 1.8
            Fixed version: 2.28-251.el8_10.22
        CVE-2025-8058, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:12980
            CVSS score: 5.9
            Fixed version: 2.28-251.el8_10.25
    Name: glibc-minimal-langpack, Version: 2.28
        CVE-2025-0395, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:3828
            CVSS score: 7.5, CVSS exploitability score: 3.9
            Fixed version: 2.28-251.el8_10.16
        CVE-2025-4802, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:8686
            CVSS score: 7.8, CVSS exploitability score: 1.8
            Fixed version: 2.28-251.el8_10.22
        CVE-2025-8058, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:12980
            CVSS score: 5.9
            Fixed version: 2.28-251.el8_10.25
    Name: gnupg2, Version: 2.2.20
        CVE-2022-3219, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-3219
            CVSS score: 3.3, CVSS exploitability score: 1.8
        CVE-2025-30258, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2025-30258
            CVSS score: 2.7, CVSS exploitability score: 1
    Name: gnutls, Version: 3.6.16
        CVE-2024-12243, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:4051
            CVSS score: 5.3, CVSS exploitability score: 3.9
            Fixed version: 3.6.16-8.el8_10.3
        CVE-2025-32988, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-32988
            CVSS score: 6.5, CVSS exploitability score: 2.2
        CVE-2025-32989, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-32989
            CVSS score: 5.3, CVSS exploitability score: 3.9
        CVE-2025-32990, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-32990
            CVSS score: 6.5, CVSS exploitability score: 3.9
        CVE-2025-6395, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-6395
            CVSS score: 6.5, CVSS exploitability score: 2.2
        CVE-2021-4209, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2021-4209
            CVSS score: 6.5, CVSS exploitability score: 2.8
    Name: jasper-libs, Version: 2.0.14
        CVE-2017-5503, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2017-5503
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2017-5504, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2017-5504
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2017-5505, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2017-5505
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2018-9055, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2018-9055
            CVSS score: 5.5, CVSS exploitability score: 1.8
            Has public exploit
        CVE-2018-9252, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2018-9252
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2021-3443, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2021-3443
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2021-3467, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2021-3467
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2022-2963, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2022-2963
            CVSS score: 7.5, CVSS exploitability score: 3.9
            Has public exploit
        CVE-2017-13745, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2017-13745
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2017-5499, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2017-5499
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2017-9782, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2017-9782
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2018-18873, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-18873
            CVSS score: 5.5, CVSS exploitability score: 1.8
            Has public exploit
        CVE-2018-19139, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-19139
            CVSS score: 5.5, CVSS exploitability score: 1.8
            Has public exploit
        CVE-2018-19539, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-19539
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2018-19540, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-19540
            CVSS score: 8.8, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2018-19541, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-19541
            CVSS score: 8.8, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2018-19542, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-19542
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2018-19543, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-19543
            CVSS score: 7.8, CVSS exploitability score: 1.8
            Has public exploit
        CVE-2018-20570, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-20570
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2018-20622, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-20622
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2022-40755, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-40755
            CVSS score: 5.5, CVSS exploitability score: 1.8
            Has public exploit
        CVE-2023-51257, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-51257
            CVSS score: 7.8, CVSS exploitability score: 1.8
    Name: java-11-openjdk, Version: 11.0.25.0.9
        CVE-2025-21502, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-21502
            CVSS score: 4.8, CVSS exploitability score: 2.2
        CVE-2025-21587, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-21587
            CVSS score: 7.4, CVSS exploitability score: 2.2
        CVE-2025-30691, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-30691
            CVSS score: 4.8, CVSS exploitability score: 2.2
        CVE-2025-30698, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-30698
            CVSS score: 5.6, CVSS exploitability score: 2.2
    Name: java-11-openjdk-devel, Version: 11.0.25.0.9
        CVE-2025-21502, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-21502
            CVSS score: 4.8, CVSS exploitability score: 2.2
        CVE-2025-21587, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-21587
            CVSS score: 7.4, CVSS exploitability score: 2.2
        CVE-2025-30691, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-30691
            CVSS score: 4.8, CVSS exploitability score: 2.2
        CVE-2025-30698, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-30698
            CVSS score: 5.6, CVSS exploitability score: 2.2
    Name: java-11-openjdk-headless, Version: 11.0.25.0.9
        CVE-2025-21502, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-21502
            CVSS score: 4.8, CVSS exploitability score: 2.2
        CVE-2025-21587, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-21587
            CVSS score: 7.4, CVSS exploitability score: 2.2
        CVE-2025-30691, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-30691
            CVSS score: 4.8, CVSS exploitability score: 2.2
        CVE-2025-30698, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-30698
            CVSS score: 5.6, CVSS exploitability score: 2.2
    Name: jq, Version: 1.6
        CVE-2024-23337, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:10618
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Fixed version: 1.6-11.el8_10
        CVE-2025-48060, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:10618
            CVSS score: 7.7, CVSS exploitability score: 3.9
            Fixed version: 1.6-11.el8_10
        CVE-2016-4074, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2016-4074
            CVSS score: 7.5, CVSS exploitability score: 3.9
    Name: krb5-libs, Version: 1.18.2
        CVE-2025-24528, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:2722
            Fixed version: 1.18.2-31.el8_10
        CVE-2025-3576, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:8411
            CVSS score: 5.9, CVSS exploitability score: 2.2
            Fixed version: 1.18.2-32.el8_10
    Name: lcms2, Version: 2.9
        CVE-2018-16435, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2018-16435
            CVSS score: 5.5, CVSS exploitability score: 1.8
    Name: libarchive, Version: 3.3.3
        CVE-2020-21674, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2020-21674
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2024-57970, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2024-57970
            CVSS score: 4, CVSS exploitability score: 2.5
        CVE-2025-25724, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-25724
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2018-1000879, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-1000879
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2018-1000880, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-1000880
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2025-1632, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2025-1632
            CVSS score: 4.8, CVSS exploitability score: 1.8
            Has public exploit
        CVE-2025-5914, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2025-5914
            CVSS score: 9.8, CVSS exploitability score: 3.9
        CVE-2025-5915, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2025-5915
            CVSS score: 3.9, CVSS exploitability score: 1.3
        CVE-2025-5916, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2025-5916
            CVSS score: 3.9, CVSS exploitability score: 1.3
        CVE-2025-5917, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2025-5917
            CVSS score: 2.8, CVSS exploitability score: 1.3
        CVE-2025-5918, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2025-5918
            CVSS score: 3.9, CVSS exploitability score: 1.3
    Name: libcurl, Version: 7.61.1
        CVE-2023-27534, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-27534
            CVSS score: 8.8, CVSS exploitability score: 2.8
        CVE-2024-11053, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-11053
            CVSS score: 3.4, CVSS exploitability score: 1.6
        CVE-2024-7264, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-7264
            CVSS score: 6.5, CVSS exploitability score: 2.8
    Name: libgcc, Version: 8.5.0
        CVE-2020-11023, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:1301
            CVSS score: 6.1, CVSS exploitability score: 2.8
            Fixed version: 8.5.0-23.el8_10
            Has public exploit, Has CISA KEV exploit
        CVE-2018-20657, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-20657
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2019-14250, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2019-14250
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2022-27943, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-27943
            CVSS score: 5.5, CVSS exploitability score: 1.8
    Name: libgcrypt, Version: 1.8.5
        CVE-2019-12904, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2019-12904
            CVSS score: 5.9, CVSS exploitability score: 2.2
        CVE-2024-2236, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2024-2236
            CVSS score: 5.9, CVSS exploitability score: 2.2
    Name: libjpeg-turbo, Version: 1.5.3
        CVE-2019-2201, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2019-2201
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2020-13790, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:7540
            CVSS score: 8.1, CVSS exploitability score: 2.8
            Fixed version: 1.5.3-14.el8_10
            Has public exploit
        CVE-2020-35538, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-35538
            CVSS score: 5.5, CVSS exploitability score: 1.8
    Name: libpkgconf, Version: 1.4.2
        CVE-2023-24056, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-24056
            CVSS score: 5.5, CVSS exploitability score: 1.8
    Name: libpng, Version: 1.6.34
        CVE-2019-7317, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2019-7317
            CVSS score: 5.3, CVSS exploitability score: 1.6
            Has public exploit
    Name: libproxy, Version: 0.4.15
        CVE-2020-25219, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2020-25219
            CVSS score: 7.5, CVSS exploitability score: 3.9
            Has public exploit
    Name: libsoup, Version: 2.62.3
        Failed policy: issuer-solution-ci-scan-policy
        CVE-2024-52531, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:0838
            CVSS score: 6.5, CVSS exploitability score: 2.2
            Fixed version: 2.62.3-7.el8_10
        CVE-2025-32906, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:4560
            CVSS score: 7.5, CVSS exploitability score: 3.9
            Fixed version: 2.62.3-8.el8_10
        CVE-2025-32908, Severity: HIGH, Source: https://access.redhat.com/security/cve/CVE-2025-32908
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2025-32911, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:4560
            CVSS score: 9, CVSS exploitability score: 2.2
            Fixed version: 2.62.3-8.el8_10
        CVE-2025-32913, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:4560
            CVSS score: 7.5, CVSS exploitability score: 3.9
            Fixed version: 2.62.3-8.el8_10
        CVE-2025-4948, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:8132
            CVSS score: 7.5, CVSS exploitability score: 3.9
            Fixed version: 2.62.3-9.el8_10
        CVE-2025-2784, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:8132
            CVSS score: 6.5, CVSS exploitability score: 3.9
            Fixed version: 2.62.3-9.el8_10
        CVE-2025-32049, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:8132
            CVSS score: 7.5, CVSS exploitability score: 3.9
            Fixed version: 2.62.3-9.el8_10
        CVE-2025-32050, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:4560
            CVSS score: 5.9, CVSS exploitability score: 2.2
            Fixed version: 2.62.3-8.el8_10
        CVE-2025-32052, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:4560
            CVSS score: 6.5, CVSS exploitability score: 3.9
            Fixed version: 2.62.3-8.el8_10
        CVE-2025-32053, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:4560
            CVSS score: 6.5, CVSS exploitability score: 3.9
            Fixed version: 2.62.3-8.el8_10
        CVE-2025-32909, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-32909
            CVSS score: 5.3, CVSS exploitability score: 3.9
        CVE-2025-32910, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-32910
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2025-32912, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-32912
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2025-32914, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:8132
            CVSS score: 7.4, CVSS exploitability score: 2.2
            Fixed version: 2.62.3-9.el8_10
        CVE-2025-4035, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-4035
            CVSS score: 4.3, CVSS exploitability score: 2.8
        CVE-2025-46420, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:4560
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Fixed version: 2.62.3-8.el8_10
        CVE-2025-46421, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:4560
            CVSS score: 6.8, CVSS exploitability score: 1.6
            Fixed version: 2.62.3-8.el8_10
        CVE-2025-4969, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-4969
            CVSS score: 6.5, CVSS exploitability score: 3.9
        CVE-2025-8197, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-8197
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2025-4476, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2025-4476
            CVSS score: 4.3, CVSS exploitability score: 2.8
        CVE-2025-4945, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2025-4945
            CVSS score: 3.7, CVSS exploitability score: 2.2
    Name: libssh, Version: 0.9.6
        CVE-2025-5318, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-5318
            CVSS score: 5.4, CVSS exploitability score: 2.8
        CVE-2025-5351, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-5351
            CVSS score: 4.2, CVSS exploitability score: 1.6
        CVE-2025-5372, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-5372
            CVSS score: 5, CVSS exploitability score: 1.6
        CVE-2025-5987, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-5987
            CVSS score: 5, CVSS exploitability score: 1.6
        CVE-2025-8114, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-8114
            CVSS score: 4.7, CVSS exploitability score: 1
        CVE-2025-4878, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2025-4878
            CVSS score: 3.6, CVSS exploitability score: 1
    Name: libssh-config, Version: 0.9.6
        CVE-2025-5318, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-5318
            CVSS score: 5.4, CVSS exploitability score: 2.8
        CVE-2025-5351, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-5351
            CVSS score: 4.2, CVSS exploitability score: 1.6
        CVE-2025-5372, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-5372
            CVSS score: 5, CVSS exploitability score: 1.6
        CVE-2025-5987, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-5987
            CVSS score: 5, CVSS exploitability score: 1.6
        CVE-2025-8114, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-8114
            CVSS score: 4.7, CVSS exploitability score: 1
        CVE-2025-4878, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2025-4878
            CVSS score: 3.6, CVSS exploitability score: 1
    Name: libstdc++, Version: 8.5.0
        CVE-2020-11023, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:1301
            CVSS score: 6.1, CVSS exploitability score: 2.8
            Fixed version: 8.5.0-23.el8_10
            Has public exploit, Has CISA KEV exploit
        CVE-2018-20657, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-20657
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2019-14250, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2019-14250
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2022-27943, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-27943
            CVSS score: 5.5, CVSS exploitability score: 1.8
    Name: libtasn1, Version: 4.13
        CVE-2024-12133, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:4049
            CVSS score: 5.3, CVSS exploitability score: 3.9
            Fixed version: 4.13-5.el8_10
        CVE-2018-1000654, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-1000654
            CVSS score: 5.5, CVSS exploitability score: 1.8
    Name: libtiff, Version: 4.0.9
        CVE-2017-17095, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:4658
            CVSS score: 8.8, CVSS exploitability score: 2.8
            Fixed version: 4.0.9-34.el8_10
            Has public exploit
        CVE-2018-10801, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2018-10801
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2018-16335, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2018-16335
            CVSS score: 8.8, CVSS exploitability score: 2.8
        CVE-2019-6128, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2019-6128
            CVSS score: 8.8, CVSS exploitability score: 2.8
        CVE-2022-3570, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2022-3570
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2022-3598, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2022-3598
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2022-3599, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2022-3599
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2022-40090, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2022-40090
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2023-0795, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-0795
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2023-0796, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-0796
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2023-0797, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-0797
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2023-0798, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-0798
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2023-0799, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-0799
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2023-25434, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-25434
            CVSS score: 8.8, CVSS exploitability score: 2.8
        CVE-2023-25435, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-25435
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2023-26965, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-26965
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2023-26966, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-26966
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2023-30086, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-30086
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2023-30774, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-30774
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2023-30775, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-30775
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2023-3164, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-3164
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2023-3316, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-3316
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2023-3576, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-3576
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2023-3618, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-3618
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2023-40745, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-40745
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2023-41175, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-41175
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2023-52355, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-52355
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2023-6277, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-6277
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2025-8176, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-8176
            CVSS score: 4.8, CVSS exploitability score: 1.8
        CVE-2025-8177, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-8177
            CVSS score: 4.8, CVSS exploitability score: 1.8
        CVE-2018-10779, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-10779
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2018-17101, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-17101
            CVSS score: 8.8, CVSS exploitability score: 2.8
        CVE-2018-19210, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-19210
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2018-5360, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-5360
            CVSS score: 8.8, CVSS exploitability score: 2.8
        CVE-2020-18768, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-18768
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2022-1056, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-1056
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2022-1354, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-1354
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2023-1916, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-1916
            CVSS score: 6.1, CVSS exploitability score: 1.8
        CVE-2024-13978, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-13978
            CVSS score: 2, CVSS exploitability score: 1
    Name: libxml2, Version: 2.9.7
        Failed policy: issuer-solution-ci-scan-policy
        CVE-2024-56171, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:2686
            CVSS score: 7.8, CVSS exploitability score: 1.4
            Fixed version: 2.9.7-19.el8_10
        CVE-2025-24928, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:2686
            CVSS score: 7.8, CVSS exploitability score: 1.4
            Fixed version: 2.9.7-19.el8_10
        CVE-2025-49794, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:10698
            CVSS score: 9.1, CVSS exploitability score: 3.9
            Fixed version: 2.9.7-21.el8_10.1
        CVE-2025-49795, Severity: HIGH, Source: https://access.redhat.com/security/cve/CVE-2025-49795
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2025-49796, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:10698
            CVSS score: 9.1, CVSS exploitability score: 3.9
            Fixed version: 2.9.7-21.el8_10.1
        CVE-2025-7425, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:12450
            CVSS score: 7.8, CVSS exploitability score: 1.4
            Fixed version: 2.9.7-21.el8_10.2
        CVE-2022-49043, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:1517
            CVSS score: 8.1, CVSS exploitability score: 1.4
            Fixed version: 2.9.7-18.el8_10.2
        CVE-2025-32414, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:8958
            CVSS score: 7.5, CVSS exploitability score: 3.9
            Fixed version: 2.9.7-20.el8_10
        CVE-2025-32415, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-32415
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2025-6021, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:10698
            CVSS score: 7.5, CVSS exploitability score: 3.9
            Fixed version: 2.9.7-21.el8_10.1
        CVE-2023-45322, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-45322
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2024-34459, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-34459
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2025-27113, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2025-27113
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2025-6170, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2025-6170
            CVSS score: 2.5, CVSS exploitability score: 1
    Name: libzstd, Version: 1.4.4
        CVE-2022-4899, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2022-4899
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2021-24032, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2021-24032
            CVSS score: 4.7, CVSS exploitability score: 1
    Name: lz4-libs, Version: 1.8.3
        CVE-2019-17543, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:11035
            CVSS score: 8.1, CVSS exploitability score: 2.2
            Fixed version: 1.8.3-5.el8_10
    Name: ncurses, Version: 6.1
        CVE-2018-19217, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2018-19217
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2018-19211, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-19211
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2020-19185, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-19185
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2020-19186, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-19186
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2020-19187, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-19187
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2020-19188, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-19188
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2020-19189, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-19189
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2020-19190, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-19190
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2021-39537, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2021-39537
            CVSS score: 8.8, CVSS exploitability score: 2.8
        CVE-2023-50495, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-50495
            CVSS score: 6.5, CVSS exploitability score: 2.8
    Name: ncurses-base, Version: 6.1
        CVE-2018-19217, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2018-19217
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2018-19211, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-19211
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2020-19185, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-19185
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2020-19186, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-19186
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2020-19187, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-19187
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2020-19188, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-19188
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2020-19189, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-19189
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2020-19190, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-19190
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2021-39537, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2021-39537
            CVSS score: 8.8, CVSS exploitability score: 2.8
        CVE-2023-50495, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-50495
            CVSS score: 6.5, CVSS exploitability score: 2.8
    Name: ncurses-libs, Version: 6.1
        CVE-2018-19217, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2018-19217
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2018-19211, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-19211
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2020-19185, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-19185
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2020-19186, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-19186
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2020-19187, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-19187
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2020-19188, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-19188
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2020-19189, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-19189
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2020-19190, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-19190
            CVSS score: 6.5, CVSS exploitability score: 2.8
            Has public exploit
        CVE-2021-39537, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2021-39537
            CVSS score: 8.8, CVSS exploitability score: 2.8
        CVE-2023-50495, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-50495
            CVSS score: 6.5, CVSS exploitability score: 2.8
    Name: nss, Version: 3.101.0
        CVE-2020-12413, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-12413
            CVSS score: 5.9, CVSS exploitability score: 2.2
        CVE-2024-7531, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-7531
            CVSS score: 6.5, CVSS exploitability score: 2.8
    Name: nss-softokn, Version: 3.101.0
        CVE-2020-12413, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-12413
            CVSS score: 5.9, CVSS exploitability score: 2.2
        CVE-2024-7531, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-7531
            CVSS score: 6.5, CVSS exploitability score: 2.8
    Name: nss-softokn-freebl, Version: 3.101.0
        CVE-2020-12413, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-12413
            CVSS score: 5.9, CVSS exploitability score: 2.2
        CVE-2024-7531, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-7531
            CVSS score: 6.5, CVSS exploitability score: 2.8
    Name: nss-sysinit, Version: 3.101.0
        CVE-2020-12413, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-12413
            CVSS score: 5.9, CVSS exploitability score: 2.2
        CVE-2024-7531, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-7531
            CVSS score: 6.5, CVSS exploitability score: 2.8
    Name: nss-util, Version: 3.101.0
        CVE-2020-12413, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-12413
            CVSS score: 5.9, CVSS exploitability score: 2.2
        CVE-2024-7531, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-7531
            CVSS score: 6.5, CVSS exploitability score: 2.8
    Name: oniguruma, Version: 6.8.2
        CVE-2019-19246, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2019-19246
            CVSS score: 7.5, CVSS exploitability score: 3.9
    Name: openssh, Version: 8.0p1
        CVE-2018-15919, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2018-15919
            CVSS score: 5.3, CVSS exploitability score: 3.9
        CVE-2019-6110, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2019-6110
            CVSS score: 6.8, CVSS exploitability score: 1.6
            Has public exploit
        CVE-2023-51767, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-51767
            CVSS score: 7, CVSS exploitability score: 1
        CVE-2025-26465, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-26465
            CVSS score: 6.8, CVSS exploitability score: 1.6
        CVE-2025-32728, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-32728
            CVSS score: 3.8, CVSS exploitability score: 2
        CVE-2016-20012, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2016-20012
            CVSS score: 5.3, CVSS exploitability score: 3.9
            Has public exploit
    Name: openssh-clients, Version: 8.0p1
        CVE-2018-15919, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2018-15919
            CVSS score: 5.3, CVSS exploitability score: 3.9
        CVE-2019-6110, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2019-6110
            CVSS score: 6.8, CVSS exploitability score: 1.6
            Has public exploit
        CVE-2023-51767, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-51767
            CVSS score: 7, CVSS exploitability score: 1
        CVE-2025-26465, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-26465
            CVSS score: 6.8, CVSS exploitability score: 1.6
        CVE-2025-32728, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-32728
            CVSS score: 3.8, CVSS exploitability score: 2
        CVE-2016-20012, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2016-20012
            CVSS score: 5.3, CVSS exploitability score: 3.9
            Has public exploit
    Name: openssl, Version: 1.1.1k
        CVE-2023-0466, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-0466
            CVSS score: 5.3, CVSS exploitability score: 3.9
        CVE-2023-2650, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-2650
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2023-0464, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-0464
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2023-0465, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-0465
            CVSS score: 5.3, CVSS exploitability score: 3.9
        CVE-2024-0727, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-0727
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2024-13176, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-13176
            CVSS score: 4.1, CVSS exploitability score: 0.7
        CVE-2024-2511, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-2511
            CVSS score: 5.9, CVSS exploitability score: 2.2
        CVE-2024-41996, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-41996
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2024-4741, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-4741
            CVSS score: 7.5, CVSS exploitability score: 3.9
    Name: openssl-libs, Version: 1.1.1k
        CVE-2023-0466, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-0466
            CVSS score: 5.3, CVSS exploitability score: 3.9
        CVE-2023-2650, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2023-2650
            CVSS score: 6.5, CVSS exploitability score: 2.8
        CVE-2023-0464, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-0464
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2023-0465, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-0465
            CVSS score: 5.3, CVSS exploitability score: 3.9
        CVE-2024-0727, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-0727
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2024-13176, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-13176
            CVSS score: 4.1, CVSS exploitability score: 0.7
        CVE-2024-2511, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-2511
            CVSS score: 5.9, CVSS exploitability score: 2.2
        CVE-2024-41996, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-41996
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2024-4741, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-4741
            CVSS score: 7.5, CVSS exploitability score: 3.9
    Name: pam, Version: 1.3.1
        Failed policy: issuer-solution-ci-scan-policy
        CVE-2025-6020, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:10027
            CVSS score: 7.8, CVSS exploitability score: 1.8
            Fixed version: 1.3.1-37.el8_10
    Name: pcre2, Version: 10.32
        CVE-2022-41409, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-41409
            CVSS score: 7.5, CVSS exploitability score: 3.9
            Has public exploit
    Name: perl-Errno, Version: 1.28
        CVE-2025-40909, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:11805
            CVSS score: 5.9, CVSS exploitability score: 2.5
            Fixed version: 1.28-423.el8_10
    Name: perl-Git, Version: 2.43.5
        Failed policy: issuer-solution-ci-scan-policy
        CVE-2025-48384, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:11534
            CVSS score: 8, CVSS exploitability score: 1.3
            Fixed version: 2.43.7-1.el8_10
        CVE-2025-48385, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:11534
            CVSS score: 8.6
            Fixed version: 2.43.7-1.el8_10
        CVE-2018-1000021, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2018-1000021
            CVSS score: 5, CVSS exploitability score: 1.6
        CVE-2024-52005, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:8414
            CVSS score: 7.5
            Fixed version: 2.43.5-3.el8_10
        CVE-2025-27613, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:11534
            CVSS score: 3.6, CVSS exploitability score: 1.8
            Fixed version: 2.43.7-1.el8_10
        CVE-2025-27614, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:11534
            CVSS score: 8.6, CVSS exploitability score: 1.8
            Fixed version: 2.43.7-1.el8_10
        CVE-2025-48386, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-48386
            CVSS score: 6.3, CVSS exploitability score: 1.8
        CVE-2024-50349, Severity: LOW, Source: https://access.redhat.com/errata/RHSA-2025:11534
            CVSS score: 2.1
            Fixed version: 2.43.7-1.el8_10
        CVE-2024-52006, Severity: LOW, Source: https://access.redhat.com/errata/RHSA-2025:11534
            CVSS score: 2.1
            Fixed version: 2.43.7-1.el8_10
        CVE-2025-46835, Severity: LOW, Source: https://access.redhat.com/errata/RHSA-2025:11534
            CVSS score: 8.5, CVSS exploitability score: 1.8
            Fixed version: 2.43.7-1.el8_10
    Name: perl-IO, Version: 1.38
        CVE-2025-40909, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:11805
            CVSS score: 5.9, CVSS exploitability score: 2.5
            Fixed version: 1.38-423.el8_10
    Name: perl-interpreter, Version: 5.26.3
        CVE-2025-40909, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:11805
            CVSS score: 5.9, CVSS exploitability score: 2.5
            Fixed version: 4:5.26.3-423.el8_10
    Name: perl-libs, Version: 5.26.3
        CVE-2025-40909, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:11805
            CVSS score: 5.9, CVSS exploitability score: 2.5
            Fixed version: 4:5.26.3-423.el8_10
    Name: perl-macros, Version: 5.26.3
        CVE-2025-40909, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:11805
            CVSS score: 5.9, CVSS exploitability score: 2.5
            Fixed version: 4:5.26.3-423.el8_10
    Name: pkgconf, Version: 1.4.2
        CVE-2023-24056, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-24056
            CVSS score: 5.5, CVSS exploitability score: 1.8
    Name: pkgconf-m4, Version: 1.4.2
        CVE-2023-24056, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-24056
            CVSS score: 5.5, CVSS exploitability score: 1.8
    Name: pkgconf-pkg-config, Version: 1.4.2
        CVE-2023-24056, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-24056
            CVSS score: 5.5, CVSS exploitability score: 1.8
    Name: platform-python, Version: 3.6.8
        Failed policy: issuer-solution-ci-scan-policy
        CVE-2024-12718, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:10128
            CVSS score: 5.3, CVSS exploitability score: 3.9
            Fixed version: 3.6.8-70.el8_10
        CVE-2025-4138, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:10128
            CVSS score: 7.5, CVSS exploitability score: 3.9
            Fixed version: 3.6.8-70.el8_10
        CVE-2025-4517, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:10128
            CVSS score: 9.4, CVSS exploitability score: 3.9
            Fixed version: 3.6.8-70.el8_10
        CVE-2025-0938, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-0938
            CVSS score: 6.3
        CVE-2025-4330, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:10128
            CVSS score: 7.5, CVSS exploitability score: 3.9
            Fixed version: 3.6.8-70.el8_10
        CVE-2025-4435, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:10128
            CVSS score: 7.5, CVSS exploitability score: 3.9
            Fixed version: 3.6.8-70.el8_10
        CVE-2025-4516, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-4516
            CVSS score: 5.9
        CVE-2025-6069, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-6069
            CVSS score: 4.3, CVSS exploitability score: 2.8
        CVE-2025-8194, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-8194
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2019-9674, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2019-9674
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2024-0397, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-0397
            CVSS score: 7.4, CVSS exploitability score: 2.2
        CVE-2024-7592, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-7592
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2025-1795, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2025-1795
            CVSS score: 2.3
    Name: platform-python-pip, Version: 9.0.3
        CVE-2025-50181, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-50181
            CVSS score: 5.3, CVSS exploitability score: 1.6
        CVE-2025-50182, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-50182
            CVSS score: 5.3, CVSS exploitability score: 1.6
        CVE-2018-20225, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-20225
            CVSS score: 7.8, CVSS exploitability score: 1.8
    Name: platform-python-setuptools, Version: 39.2.0
        CVE-2025-47273, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:11036
            CVSS score: 7.7, CVSS exploitability score: 2.8
            Fixed version: 39.2.0-9.el8_10
    Name: python3-cloud-what, Version: 1.28.42
        CVE-2022-0235, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2022-0235
            CVSS score: 6.1, CVSS exploitability score: 2.8
    Name: python3-libs, Version: 3.6.8
        Failed policy: issuer-solution-ci-scan-policy
        CVE-2024-12718, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:10128
            CVSS score: 5.3, CVSS exploitability score: 3.9
            Fixed version: 3.6.8-70.el8_10
        CVE-2025-4138, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:10128
            CVSS score: 7.5, CVSS exploitability score: 3.9
            Fixed version: 3.6.8-70.el8_10
        CVE-2025-4517, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:10128
            CVSS score: 9.4, CVSS exploitability score: 3.9
            Fixed version: 3.6.8-70.el8_10
        CVE-2025-0938, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-0938
            CVSS score: 6.3
        CVE-2025-4330, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:10128
            CVSS score: 7.5, CVSS exploitability score: 3.9
            Fixed version: 3.6.8-70.el8_10
        CVE-2025-4435, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:10128
            CVSS score: 7.5, CVSS exploitability score: 3.9
            Fixed version: 3.6.8-70.el8_10
        CVE-2025-4516, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-4516
            CVSS score: 5.9
        CVE-2025-6069, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-6069
            CVSS score: 4.3, CVSS exploitability score: 2.8
        CVE-2025-8194, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-8194
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2019-9674, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2019-9674
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2024-0397, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-0397
            CVSS score: 7.4, CVSS exploitability score: 2.2
        CVE-2024-7592, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-7592
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2025-1795, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2025-1795
            CVSS score: 2.3
    Name: python3-pip-wheel, Version: 9.0.3
        CVE-2025-50181, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-50181
            CVSS score: 5.3, CVSS exploitability score: 1.6
        CVE-2025-50182, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-50182
            CVSS score: 5.3, CVSS exploitability score: 1.6
        CVE-2018-20225, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-20225
            CVSS score: 7.8, CVSS exploitability score: 1.8
    Name: python3-requests, Version: 2.20.0
        CVE-2024-47081, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2024-47081
            CVSS score: 5.3, CVSS exploitability score: 1.6
    Name: python3-setuptools-wheel, Version: 39.2.0
        CVE-2025-47273, Severity: MEDIUM, Source: https://access.redhat.com/errata/RHSA-2025:11036
            CVSS score: 7.7, CVSS exploitability score: 2.8
            Fixed version: 39.2.0-9.el8_10
    Name: python3-subscription-manager-rhsm, Version: 1.28.42
        CVE-2022-0235, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2022-0235
            CVSS score: 6.1, CVSS exploitability score: 2.8
    Name: python3-syspurpose, Version: 1.28.42
        CVE-2022-0235, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2022-0235
            CVSS score: 6.1, CVSS exploitability score: 2.8
    Name: shadow-utils, Version: 4.6
        CVE-2024-56433, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-56433
            CVSS score: 3.6, CVSS exploitability score: 1
    Name: sqlite-libs, Version: 3.26.0
        Failed policy: issuer-solution-ci-scan-policy
        CVE-2025-6965, Severity: HIGH, Source: https://access.redhat.com/errata/RHSA-2025:12010
            CVSS score: 7.2, CVSS exploitability score: 3.9
            Fixed version: 3.26.0-20.el8_10
        CVE-2025-7458, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-7458
            CVSS score: 6.9
        CVE-2019-19244, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2019-19244
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2019-9936, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2019-9936
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2019-9937, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2019-9937
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2024-0232, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-0232
            CVSS score: 5.5, CVSS exploitability score: 1.8
    Name: subscription-manager, Version: 1.28.42
        CVE-2022-0235, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2022-0235
            CVSS score: 6.1, CVSS exploitability score: 2.8
    Name: subscription-manager-rhsm-certificates, Version: 20220623
        CVE-2022-0235, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2022-0235
            CVSS score: 6.1, CVSS exploitability score: 2.8
    Name: systemd, Version: 239
        CVE-2018-20839, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2018-20839
            CVSS score: 4.3, CVSS exploitability score: 0.7
        CVE-2021-3997, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2021-3997
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2025-4598, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-4598
            CVSS score: 4.7, CVSS exploitability score: 1
    Name: systemd-libs, Version: 239
        CVE-2018-20839, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2018-20839
            CVSS score: 4.3, CVSS exploitability score: 0.7
        CVE-2021-3997, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2021-3997
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2025-4598, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-4598
            CVSS score: 4.7, CVSS exploitability score: 1
    Name: systemd-pam, Version: 239
        CVE-2018-20839, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2018-20839
            CVSS score: 4.3, CVSS exploitability score: 0.7
        CVE-2021-3997, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2021-3997
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2025-4598, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-4598
            CVSS score: 4.7, CVSS exploitability score: 1
    Name: tar, Version: 1.30
        CVE-2005-2541, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2005-2541
            CVSS score: 10, CVSS exploitability score: 10
        CVE-2021-20193, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2021-20193
            CVSS score: 3.3, CVSS exploitability score: 1.8
        CVE-2025-45582, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-45582
            CVSS score: 4.1, CVSS exploitability score: 1
        CVE-2019-9923, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2019-9923
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2023-39804, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-39804
            CVSS score: 6.2, CVSS exploitability score: 2.5
    Name: unzip, Version: 6.0
        CVE-2021-4217, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2021-4217
            CVSS score: 3.3, CVSS exploitability score: 1.8
        CVE-2022-0529, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-0529
            CVSS score: 5.5, CVSS exploitability score: 1.8
            Has public exploit
        CVE-2022-0530, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-0530
            CVSS score: 5.5, CVSS exploitability score: 1.8
            Has public exploit
    Name: vim-minimal, Version: 8.0.1763
        CVE-2025-29768, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-29768
            CVSS score: 4.4, CVSS exploitability score: 1.8
        CVE-2025-53905, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-53905
            CVSS score: 4.1, CVSS exploitability score: 1
        CVE-2025-53906, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2025-53906
            CVSS score: 4.1, CVSS exploitability score: 1
        CVE-2018-20786, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2018-20786
            CVSS score: 7.5, CVSS exploitability score: 3.9
            Has public exploit
        CVE-2020-20703, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2020-20703
            CVSS score: 9.8, CVSS exploitability score: 3.9
        CVE-2021-3236, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2021-3236
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2021-3927, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2021-3927
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2021-3974, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2021-3974
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2021-4166, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2021-4166
            CVSS score: 7.1, CVSS exploitability score: 1.8
        CVE-2022-0351, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-0351
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-1619, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-1619
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-1720, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-1720
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2124, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2124
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2125, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2125
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2126, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2126
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2129, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2129
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2175, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2175
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2182, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2182
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2183, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2183
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2206, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2206
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2207, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2207
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2208, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2208
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2022-2210, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2210
            CVSS score: 7.8, CVSS exploitability score: 1.8
            Has public exploit
        CVE-2022-2284, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2284
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2285, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2285
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2286, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2286
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2287, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2287
            CVSS score: 7.1, CVSS exploitability score: 1.8
        CVE-2022-2343, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2343
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2344, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2344
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2345, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2345
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2522, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2522
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2819, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2819
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2845, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2845
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2849, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2849
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2923, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2923
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2022-2946, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2946
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-2980, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-2980
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2022-3037, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-3037
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-3153, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-3153
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2022-3234, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-3234
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-3235, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-3235
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-3256, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-3256
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-3296, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-3296
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-3352, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-3352
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-3705, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-3705
            CVSS score: 7.5, CVSS exploitability score: 1.6
        CVE-2022-4292, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-4292
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2022-4293, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2022-4293
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2023-0049, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-0049
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2023-0054, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-0054
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2023-0288, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-0288
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2023-0433, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-0433
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2023-0512, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-0512
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2023-1127, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-1127
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2023-1170, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-1170
            CVSS score: 6.6, CVSS exploitability score: 1.8
        CVE-2023-1175, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-1175
            CVSS score: 6.6, CVSS exploitability score: 1.8
        CVE-2023-1264, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-1264
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2023-2609, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-2609
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2023-2610, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-2610
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2023-46246, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-46246
            CVSS score: 5.5, CVSS exploitability score: 1.8
            Has public exploit
        CVE-2023-4733, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-4733
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2023-4734, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-4734
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2023-4735, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-4735
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2023-4738, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-4738
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2023-4750, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-4750
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2023-4751, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-4751
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2023-4752, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-4752
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2023-4781, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-4781
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2023-48231, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-48231
            CVSS score: 4.3, CVSS exploitability score: 2.8
        CVE-2023-48232, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-48232
            CVSS score: 4.3, CVSS exploitability score: 2.8
        CVE-2023-48233, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-48233
            CVSS score: 4.3, CVSS exploitability score: 2.8
        CVE-2023-48234, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-48234
            CVSS score: 4.3, CVSS exploitability score: 2.8
        CVE-2023-48235, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-48235
            CVSS score: 4.3, CVSS exploitability score: 2.8
        CVE-2023-48236, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-48236
            CVSS score: 4.3, CVSS exploitability score: 2.8
        CVE-2023-48237, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-48237
            CVSS score: 4.3, CVSS exploitability score: 2.8
        CVE-2023-48706, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-48706
            CVSS score: 4.7, CVSS exploitability score: 1
            Has public exploit
        CVE-2023-5344, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-5344
            CVSS score: 7.5, CVSS exploitability score: 3.9
        CVE-2023-5441, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-5441
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2023-5535, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2023-5535
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2024-22667, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-22667
            CVSS score: 7.8, CVSS exploitability score: 1.8
        CVE-2024-41965, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-41965
            CVSS score: 4.2, CVSS exploitability score: 0.8
        CVE-2024-43374, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-43374
            CVSS score: 4.5, CVSS exploitability score: 1
        CVE-2024-43802, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-43802
            CVSS score: 4.5, CVSS exploitability score: 1
        CVE-2024-45306, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-45306
            CVSS score: 5.5, CVSS exploitability score: 1.8
        CVE-2024-47814, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2024-47814
            CVSS score: 3.9, CVSS exploitability score: 1.3
        CVE-2025-1215, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2025-1215
            CVSS score: 2.4, CVSS exploitability score: 1.3
        CVE-2025-22134, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2025-22134
            CVSS score: 4.2, CVSS exploitability score: 0.8
        CVE-2025-24014, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2025-24014
            CVSS score: 4.2, CVSS exploitability score: 0.8
        CVE-2025-26603, Severity: LOW, Source: https://access.redhat.com/security/cve/CVE-2025-26603
            CVSS score: 4.2, CVSS exploitability score: 0.8
    Name: wget, Version: 1.19.5
        CVE-2021-31879, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2021-31879
            CVSS score: 6.1, CVSS exploitability score: 2.8
        CVE-2024-10524, Severity: MEDIUM, Source: https://access.redhat.com/security/cve/CVE-2024-10524
            CVSS score: 6.5, CVSS exploitability score: 2.2
    Name: zlib, Version: 1.2.11
        Failed policy: issuer-solution-ci-scan-policy
        CVE-2025-4638, Severity: HIGH, Source: https://access.redhat.com/security/cve/CVE-2025-4638
            CVSS score: 9.2

CPE vulnerabilities:
    Name: cpe:2.3:a:oracle:jdk, Version: 11.0.25, Path: /usr/lib/jvm/java-11-openjdk-11.0.25.0.9-2.el8.x86_64/bin/javac
        CVE-2025-21502, Severity: MEDIUM, Source: https://nvd.nist.gov/vuln/detail/CVE-2025-21502
            CVSS score: 4.8, CVSS exploitability score: 2.2
            Fixed version: 11.0.25.9

Secrets:
    Secret description: Private Key
        Secret type: Private key
        Path: /etc/pki/consumer/key.pem, Line 1
        Severity: HIGH
        Additional data: Algorithm: PKIAlgorithmTypeRSA, Bits: 4096
    Secret description: Private Key
        Secret type: Private key
        Path: /etc/pki/entitlement/5726207519676597253-key.pem, Line 1
        Severity: HIGH
        Additional data: Algorithm: PKIAlgorithmTypeRSA, Bits: 4096

Evaluated policy:
    Name: issuer-solution-ci-scan-policy
    Type: VULNERABILITIES
    Action: BLOCK
Failed policy: issuer-solution-ci-scan-policy
Vulnerable packages: CRITICAL: 0, HIGH: 13, MEDIUM: 70, LOW: 22, INFORMATIONAL: 0
    Total: 105
Vulnerabilities: CRITICAL: 0, HIGH: 31, MEDIUM: 224, LOW: 265, INFORMATIONAL: 0
    Total: 520, out of which 101 are fixable
Secrets: Private key: 2
Directories scanned: 2687, Files scanned: 21227
Scan results: FAILED. Container image does not meet policy requirements
Scan report: https://app.wiz.io/findings/cicd-scans#~%2528cicd_scan~%25278001546a-6606-414c-a78a-0c5608b16940%252A2c2025-08-06T21%2525%25252A3a54%2525%25252A3a47.160290436Z%2527%2529
Using mount/mountWithLayers drivers is recommended to decrease image scan time. For more information - https://docs.wiz.io/wiz-docs/docs/use-wiz-cli#scan-drivers
FAILED: Scan failed - policy failure
[Pipeline] }
[Pipeline] // withCredentials
[Pipeline] }
ERROR: script returned exit code 4
[Pipeline] // catchError
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Release container image)
[Pipeline] tool
[Pipeline] envVarsForTool
[Pipeline] tool
[Pipeline] envVarsForTool
[Pipeline] withEnv
[Pipeline] {
[Pipeline] echo
gfsContainerImageNexusPush - push container image to nexus
[Pipeline] withCredentials
Masking supported pattern matches of $pass
[Pipeline] {
[Pipeline] sh
Warning: A secret was passed to "sh" using Groovy String interpolation, which is insecure.
		 Affected argument(s) used the following variable(s): [pass]
		 See https://jenkins.io/redirect/groovy-string-interpolation for details.
+ podman login -u svc-newarch-cicd -p **** fmk.nexus-ci.onefiserv.net
Login Succeeded!
[Pipeline] }
[Pipeline] // withCredentials
[Pipeline] sh
+ podman push fmk.nexus-ci.onefiserv.net/org/is/admin:0.0.3
Getting image source signatures
Copying blob sha256:5d089121e343d27000dd461a5e0327a11f6afa60d25385f3085e60317fda36d5
Copying blob sha256:07a2ea1c9b75dd32baca7b6346e64ae297dbc58484b79815818cfdc7c164ff2b
Copying blob sha256:5f70bf18a086007016e948b04aed3b82103a36bea41755b6cddfaf10ace3c6ef
Copying blob sha256:ba17fbf47947c7921d7a9fa885d7d7a386c60a11b819dca5cdd147ab5a0ea30c
Copying blob sha256:c58a4c0d0ec7a555deb268e975e336b9b18932224992cfd292fc2fd7649289b5
Copying blob sha256:29e4c80a812dbe2dc195a71bc867beb7258154b45e07d43f97af96c974ad969e
Copying blob sha256:256f6f540c227aebb15ff15c26da1c027afb681be6dbba24a143d01de7fcc960
Copying blob sha256:5f70bf18a086007016e948b04aed3b82103a36bea41755b6cddfaf10ace3c6ef
Copying config sha256:94b6f7d3c4ed84087273158b7217c3a7d21ad06abb9b03f8646ff639fb8c14ae
Writing manifest to image destination
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy to DEMO)
[Pipeline] tool
[Pipeline] envVarsForTool
[Pipeline] tool
[Pipeline] envVarsForTool
[Pipeline] withEnv
[Pipeline] {
[Pipeline] tool
[Pipeline] tool
[Pipeline] withEnv
[Pipeline] {
[Pipeline] script
[Pipeline] {
Did you forget the `def` keyword? gfsCloudPipelineV2 seems to be setting a field named failedStage (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] tool
[Pipeline] tool
[Pipeline] withEnv
[Pipeline] {
[Pipeline] sh
+ head -n1 /newarch/apps/fortify/version.txt
Did you forget the `def` keyword? gfsPOMPropertyValue seems to be setting a field named command (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] sh
+ mvn help:evaluate -Dexpression=rundeck.url -Dfortify.version=25.2.0 -q -DforceStdout
Did you forget the `def` keyword? gfsPOMPropertyValue seems to be setting a field named propertyValue (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] echo
pom property value = https://rundeck.1dc.com
[Pipeline] }
[Pipeline] // withEnv
Did you forget the `def` keyword? gfsCloudPipelineV2 seems to be setting a field named rundeckUrl (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] tool
[Pipeline] tool
[Pipeline] withEnv
[Pipeline] {
[Pipeline] sh
+ head -n1 /newarch/apps/fortify/version.txt
Did you forget the `def` keyword? gfsPOMPropertyValue seems to be setting a field named command (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] sh
+ mvn help:evaluate -Dexpression=rundeck.token -Dfortify.version=25.2.0 -q -DforceStdout
Did you forget the `def` keyword? gfsPOMPropertyValue seems to be setting a field named propertyValue (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] echo
pom property value = AbWbrusvtE5DwpX9fWqnXtx9MHqYKs1G
[Pipeline] }
[Pipeline] // withEnv
Did you forget the `def` keyword? gfsCloudPipelineV2 seems to be setting a field named rundeckToken (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] sh
+ mvn help:evaluate -Dexpression=rundeck.job -q -DforceStdout
Did you forget the `def` keyword? gfsCloudPipelineV2 seems to be setting a field named rundeckJob (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] sh
+ mvn help:evaluate -Dexpression=rundeck.job.option.name -q -DforceStdout
Did you forget the `def` keyword? gfsCloudPipelineV2 seems to be setting a field named rundeckOptionName (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] sh
+ mvn help:evaluate -Dexpression=rundeck.job.option.value -q -DforceStdout
Did you forget the `def` keyword? gfsCloudPipelineV2 seems to be setting a field named rundeckOptionValue (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] sh
+ mvn help:evaluate -Dexpression=rundeck.job.params -q -DforceStdout
Did you forget the `def` keyword? gfsCloudPipelineV2 seems to be setting a field named rundeckJobParams (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] echo
Service admin
[Pipeline] echo
SERVICE_NAME=admin,VERSION=0.0.3,NAMESPACE=trace-dev-comm-app,CONFIG_NAME=trace-dev-comm-app-1,TYPE=springboot,CLUSTER=https://api.syosxfftsm0001.fiserv.one:6443/
Did you forget the `def` keyword? gfsCloudPipelineV2 seems to be setting a field named rundeckOptions (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] echo
rundeck params for dev: -Service admin -SERVICE_NAME 'admin' -VERSION '0.0.3' -NAMESPACE 'trace-dev-comm-app' -CONFIG_NAME 'trace-dev-comm-app-1' -TYPE 'springboot' -CLUSTER 'https://api.syosxfftsm0001.fiserv.one:6443/'
[Pipeline] }
[Pipeline] // script
[Pipeline] echo
{"argString": " -Service admin -SERVICE_NAME 'admin' -VERSION '0.0.3' -NAMESPACE 'trace-dev-comm-app' -CONFIG_NAME 'trace-dev-comm-app-1' -TYPE 'springboot' -CLUSTER 'https://api.syosxfftsm0001.fiserv.one:6443/'"}
[Pipeline] httpRequest
HttpMethod: POST
URL: https://rundeck.1dc.com/api/15/job/8ba40041-e885-4e6d-a69a-004dce3b48cf/executions
Accept: application/json
Content-Type: application/json
X-Rundeck-Auth-Token: AbWbrusvtE5DwpX9fWqnXtx9MHqYKs1G
Sending request to url: https://rundeck.1dc.com/api/15/job/8ba40041-e885-4e6d-a69a-004dce3b48cf/executions
Response Code: HTTP/1.1 200 OK
Success: Status code 200 is in the accepted range: 200
[Pipeline] readJSON
[Pipeline] sh
+ echo id api url = https://rundeck.1dc.com/api/34/execution/204935
id api url = https://rundeck.1dc.com/api/34/execution/204935
[Pipeline] sleep
Sleeping for 5 sec
[Pipeline] httpRequest
HttpMethod: GET
URL: https://rundeck.1dc.com/api/34/execution/204935
Accept: application/json
Content-Type: application/json
X-Rundeck-Auth-Token: AbWbrusvtE5DwpX9fWqnXtx9MHqYKs1G
Sending request to url: https://rundeck.1dc.com/api/34/execution/204935
Response Code: HTTP/1.1 200 OK
Success: Status code 200 is in the accepted range: 100:399
[Pipeline] readJSON
[Pipeline] echo
status: running
[Pipeline] echo
retry: 1
[Pipeline] sleep
Sleeping for 5 sec
[Pipeline] httpRequest
HttpMethod: GET
URL: https://rundeck.1dc.com/api/34/execution/204935
Accept: application/json
Content-Type: application/json
X-Rundeck-Auth-Token: AbWbrusvtE5DwpX9fWqnXtx9MHqYKs1G
Sending request to url: https://rundeck.1dc.com/api/34/execution/204935
Response Code: HTTP/1.1 200 OK
Success: Status code 200 is in the accepted range: 100:399
[Pipeline] readJSON
[Pipeline] echo
status: running
[Pipeline] echo
retry: 2
[Pipeline] sleep
Sleeping for 5 sec
[Pipeline] httpRequest
HttpMethod: GET
URL: https://rundeck.1dc.com/api/34/execution/204935
Accept: application/json
Content-Type: application/json
X-Rundeck-Auth-Token: AbWbrusvtE5DwpX9fWqnXtx9MHqYKs1G
Sending request to url: https://rundeck.1dc.com/api/34/execution/204935
Response Code: HTTP/1.1 200 OK
Success: Status code 200 is in the accepted range: 100:399
[Pipeline] readJSON
[Pipeline] echo
status: running
[Pipeline] echo
retry: 3
[Pipeline] sleep
Sleeping for 5 sec
[Pipeline] httpRequest
HttpMethod: GET
URL: https://rundeck.1dc.com/api/34/execution/204935
Accept: application/json
Content-Type: application/json
X-Rundeck-Auth-Token: AbWbrusvtE5DwpX9fWqnXtx9MHqYKs1G
Sending request to url: https://rundeck.1dc.com/api/34/execution/204935
Response Code: HTTP/1.1 200 OK
Success: Status code 200 is in the accepted range: 100:399
[Pipeline] readJSON
[Pipeline] echo
status: running
[Pipeline] echo
retry: 4
[Pipeline] sleep
Sleeping for 5 sec
[Pipeline] httpRequest
HttpMethod: GET
URL: https://rundeck.1dc.com/api/34/execution/204935
Accept: application/json
Content-Type: application/json
X-Rundeck-Auth-Token: AbWbrusvtE5DwpX9fWqnXtx9MHqYKs1G
Sending request to url: https://rundeck.1dc.com/api/34/execution/204935
Response Code: HTTP/1.1 200 OK
Success: Status code 200 is in the accepted range: 100:399
[Pipeline] readJSON
[Pipeline] echo
status: running
[Pipeline] echo
retry: 5
[Pipeline] sleep
Sleeping for 5 sec
[Pipeline] httpRequest
HttpMethod: GET
URL: https://rundeck.1dc.com/api/34/execution/204935
Accept: application/json
Content-Type: application/json
X-Rundeck-Auth-Token: AbWbrusvtE5DwpX9fWqnXtx9MHqYKs1G
Sending request to url: https://rundeck.1dc.com/api/34/execution/204935
Response Code: HTTP/1.1 200 OK
Success: Status code 200 is in the accepted range: 100:399
[Pipeline] readJSON
[Pipeline] echo
status: running
[Pipeline] echo
retry: 6
[Pipeline] sleep
Sleeping for 5 sec
[Pipeline] httpRequest
HttpMethod: GET
URL: https://rundeck.1dc.com/api/34/execution/204935
Accept: application/json
Content-Type: application/json
X-Rundeck-Auth-Token: AbWbrusvtE5DwpX9fWqnXtx9MHqYKs1G
Sending request to url: https://rundeck.1dc.com/api/34/execution/204935
Response Code: HTTP/1.1 200 OK
Success: Status code 200 is in the accepted range: 100:399
[Pipeline] readJSON
[Pipeline] echo
status: running
[Pipeline] echo
retry: 7
[Pipeline] sleep
Sleeping for 5 sec
[Pipeline] httpRequest
HttpMethod: GET
URL: https://rundeck.1dc.com/api/34/execution/204935
Accept: application/json
Content-Type: application/json
X-Rundeck-Auth-Token: AbWbrusvtE5DwpX9fWqnXtx9MHqYKs1G
Sending request to url: https://rundeck.1dc.com/api/34/execution/204935
Response Code: HTTP/1.1 200 OK
Success: Status code 200 is in the accepted range: 100:399
[Pipeline] readJSON
[Pipeline] echo
status: running
[Pipeline] echo
retry: 8
[Pipeline] sleep
Sleeping for 5 sec
[Pipeline] httpRequest
HttpMethod: GET
URL: https://rundeck.1dc.com/api/34/execution/204935
Accept: application/json
Content-Type: application/json
X-Rundeck-Auth-Token: AbWbrusvtE5DwpX9fWqnXtx9MHqYKs1G
Sending request to url: https://rundeck.1dc.com/api/34/execution/204935
Response Code: HTTP/1.1 200 OK
Success: Status code 200 is in the accepted range: 100:399
[Pipeline] readJSON
[Pipeline] echo
status: failed
[Pipeline] echo
https://rundeck.1dc.com/project/fs-azure-openshift-lowers/execution/show/204935
[Pipeline] echo
Rundeck job failed
[Pipeline] error
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (DEMO regression test)
Stage "DEMO regression test" skipped due to earlier failure(s)
[Pipeline] getContext
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy to QA)
Stage "Deploy to QA" skipped due to earlier failure(s)
[Pipeline] getContext
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (QA regression test)
Stage "QA regression test" skipped due to earlier failure(s)
[Pipeline] getContext
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Dynamic Scan)
Stage "Dynamic Scan" skipped due to earlier failure(s)
[Pipeline] getContext
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Declarative: Post Actions)
[Pipeline] script
[Pipeline] {
[Pipeline] echo
notify gitlab
[Pipeline] withCredentials
Masking supported pattern matches of $token
[Pipeline] {
Did you forget the `def` keyword? gfsNotifyGitlab seems to be setting a field named state (to a value of type String) which could lead to memory leaks or other issues.
Did you forget the `def` keyword? gfsNotifyGitlab seems to be setting a field named state (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] echo
project id = issuers%2Ffos-modernization%2Fplastic%2Frapid%2FRAPID-Rapid-microservices-Java
[Pipeline] echo
api url = "https://gitlab.onefiserv.net/api/v4/projects/issuers%2Ffos-modernization%2Fplastic%2Frapid%2FRAPID-Rapid-microservices-Java/statuses/beb607e21779838012885329ece8f9ea1055ea49"
[Pipeline] echo
{"state": "failed", "target_url": "https://nsajenkins.fiserv.one/job/RAPID-Rapid-microservices-Java/job/release%252Frapid-microservices-Java/3/", "description": "built by Jenkins @ https://nsajenkins.fiserv.one"}
[Pipeline] httpRequest
HttpMethod: POST
URL: https://gitlab.onefiserv.net/api/v4/projects/issuers%2Ffos-modernization%2Fplastic%2Frapid%2FRAPID-Rapid-microservices-Java/statuses/beb607e21779838012885329ece8f9ea1055ea49
Content-Type: application/json
Authorization: *****
Sending request to url: https://gitlab.onefiserv.net/api/v4/projects/issuers%2Ffos-modernization%2Fplastic%2Frapid%2FRAPID-Rapid-microservices-Java/statuses/beb607e21779838012885329ece8f9ea1055ea49
Response Code: HTTP/1.1 201 Created
Success: Status code 201 is in the accepted range: 200:204,400:403
[Pipeline] }
[Pipeline] // withCredentials
[Pipeline] tool
[Pipeline] tool
[Pipeline] withEnv
[Pipeline] {
[Pipeline] tool
[Pipeline] tool
[Pipeline] withEnv
[Pipeline] {
[Pipeline] sh
+ head -n1 /newarch/apps/fortify/version.txt
Did you forget the `def` keyword? gfsPOMPropertyValue seems to be setting a field named command (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] sh
+ mvn help:evaluate -Dexpression=project.version -Dfortify.version=25.2.0 -q -DforceStdout
Did you forget the `def` keyword? gfsPOMPropertyValue seems to be setting a field named propertyValue (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] echo
pom property value = 0.0.3
[Pipeline] }
[Pipeline] // withEnv
Did you forget the `def` keyword? gfsCloudPipelineV2 seems to be setting a field named projectVersion (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] sh
+ echo clean up workspace
clean up workspace
[Pipeline] sh
+ podman rmi fmk.nexus-ci.onefiserv.net/org/is/admin:0.0.3
Untagged: fmk.nexus-ci.onefiserv.net/org/is/admin:0.0.3
Deleted: 94b6f7d3c4ed84087273158b7217c3a7d21ad06abb9b03f8646ff639fb8c14ae
Deleted: 3e910138a504228aa16237da1a6d289b8322167f1bb5c5b15d7116ecb94d6e9c
Deleted: 7b2308da7d62d5d616a4e852918df5e5a2c7a290159c877e36e93739815c192e
Deleted: 4908276bcf6898e53c00bdd112dfd01c155e979c38858307abe1855205fe7f27
Deleted: 5a856334bf657326759cdaf98eaec4c1196dd20fee278c96dc79d58eabe9a95e
Deleted: 156cdff055f10051d731c148ca186dacb34f3d72997704a0e6e171429d3113cd
Deleted: c9aa4100f12b344899da1e6d54bb0d6d483728587d024a3800abacc48c8c3c44
Deleted: b7643b5074f8418d27f9a4e90cf5c1d6e64e23f1ca2bba50fd5bbdda196d7e6a
[Pipeline] deleteDir
[Pipeline] }
[Pipeline] // script
[Pipeline] script
[Pipeline] {
Did you forget the `def` keyword? gfsCloudPipelineV2 seems to be setting a field named buildUrl (to a value of type String) which could lead to memory leaks or other issues.
Did you forget the `def` keyword? gfsCloudPipelineV2 seems to be setting a field named buildUrl (to a value of type String) which could lead to memory leaks or other issues.
[Pipeline] mail
[Pipeline] }
[Pipeline] // script
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // timeout
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
ERROR: Rundeck job failed. https://rundeck.1dc.com/project/fs-azure-openshift-lowers/execution/show/204935
Finished: FAILURE
