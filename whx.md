//下载数据库脚本文件：
wget https://github.com/ucarGroup/DataLink/blob/master/dl-biz/src/main/resources/biz/sql/ucar_datalink.sql
//导入数据库脚本：
source ucar_datalink.sql

---
dl-biz:


Missing artifact com.microsoft.sqlserver:sqljdbc4:jar:4.0

<!-- https://mvnrepository.com/artifact/com.microsoft.sqlserver/mssql-jdbc -->
<dependency>
    <groupId>com.microsoft.sqlserver</groupId>
    <artifactId>mssql-jdbc</artifactId>
    <version>6.1.0.jre8</version>
</dependency>





Due to Oracle license restriction, there are no public repositories that provide ojdbc jar.


http://www.oracle.com/technetwork/database/features/jdbc/jdbc-drivers-12c-download-1958347.html


You need to download it and install in your local repository. Get jar from Oracle and install it in your local maven repository using


mvn install:install-file -Dfile=./ojdbc6.jar -DgroupId=com.oracle -DartifactId=ojdbc6 -Dversion=12.1.0.1 -Dpackaging=jar
If you are using ojdbc7, here is the link



---

dl-worker-writer-kudu :

Failed to execute goal on project dl-worker-writer-kudu: Could not resolve dependencies for project com.ucar.datalink:dl-worker-writer-kudu:jar:1.0.2-beta: Could not find artifact Impala:ImpalaJDBC41:jar:2.6.4 in central (https://repo.maven.apache.org/maven2) -> [Help 1]

        <!-- https://mvnrepository.com/artifact/com.cloudera/ImpalaJDBC41 -->
        <dependency>
            <groupId>com.cloudera</groupId>
            <artifactId>ImpalaJDBC41</artifactId>
            <version>2.6.3</version>
        </dependency>



---

T_DL_INTERCEPTOR
T_DL_TASK
这两个表需要改成小些
dl-biz/src/main/resources/biz/sqlmap:
mapper-interceptor.xml
mapper-task.xml



---
wget https://repo.clojars.org/com/microsoft/sqlserver/sqljdbc4/4.0/sqljdbc4-4.0.jar

mvn install:install-file -Dfile=./sqljdbc4-4.0.jar -DgroupId=com.microsoft.sqlserver -DartifactId=sqljdbc4 -Dversion=4.0 -Dpackaging=jar -DpomFile=./sqljdbc4-4.0.pom


wget http://repo.odysseusinc.com/artifactory/community-libs-release-local/com/cloudera/ImpalaJDBC41/2.6.3/ImpalaJDBC41-2.6.3.jar -DpomFile=

mvn install:install-file -Dfile=./ImpalaJDBC41-2.6.3.jar -DgroupId=com.cloudera -DartifactId=ImpalaJDBC41 -Dversion=2.6.3 -Dpackaging=jar -DpomFile=./ImpalaJDBC41-2.6.3.pom




---
Could not lock System prefs. Unix error code 32629

mkdir -p ~/.java/.systemPrefs
chmod -R 755 ~/.java
export JAVA_OPTS="-Djava.util.prefs.systemRoot=/home/vagrant/.java -Djava.util.prefs.userRoot=/home/vagrant/.java/.userPrefs"


