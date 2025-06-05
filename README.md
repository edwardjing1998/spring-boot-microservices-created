  # ------------- 新增调试 Job -------------
  debug-effective-pom:
    name: Dump effective POM
    needs: ci-workflow          # 先跑完主流水线，再跑调试；如想并行可去掉
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - name: Set up JDK 21
        uses: actions/setup-java@v4
        with:
          distribution: temurin
          java-version: '21'
          cache: maven

      - name: Dump effective POM
        run: mvn -q help:effective-pom -Doutput=effective.xml

      - name: Grep tomcat version
        run: grep -n "<tomcat-embed-core" -A1 effective.xml || true

      #（可选）把 effective.xml 作为工件下载到本机查看
      - name: Upload effective POM
        uses: actions/upload-artifact@v4
        with:
          name: effective-pom
          path: effective.xml
