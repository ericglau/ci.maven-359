# ci.maven-359
Recreate for WASdev/ci.maven [issue 359](https://github.com/WASdev/ci.maven/issues/359)

## Simple way to recreate NPE

1. Run
```bash
cd 2.4.2
mvn package
cd ..
cd 2.5
mvn package
cd ..
diff -ru 2.4.2/target/liberty/wlp 2.5/target/liberty/wlp > diff.txt
```

Result in diff.txt:
```
Only in 2.4.2/target/liberty/wlp/bin: batchManager
Only in 2.4.2/target/liberty/wlp/bin: batchManager.bat
Only in 2.4.2/target/liberty/wlp/bin: ddlGen
Only in 2.4.2/target/liberty/wlp/bin: ddlGen.bat
Only in 2.4.2/target/liberty/wlp/bin: jaxb
Only in 2.4.2/target/liberty/wlp/bin: pluginUtility
Only in 2.4.2/target/liberty/wlp/bin: pluginUtility.bat
Only in 2.4.2/target/liberty/wlp/bin/tools: ws-generateddlutil.jar
Only in 2.4.2/target/liberty/wlp/bin/tools: ws-jbatchutil.jar
Only in 2.4.2/target/liberty/wlp/bin/tools: ws-webserverPluginutil.jar
Only in 2.4.2/target/liberty/wlp/dev/api/ibm/javadoc: com.ibm.websphere.appserver.api.basics_1.3-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/api/ibm/javadoc: com.ibm.websphere.appserver.api.distributedMap_2.0-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/api/ibm/javadoc: com.ibm.websphere.appserver.api.endpoint_1.0-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/api/ibm/javadoc: com.ibm.websphere.appserver.api.json_1.0-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/api/ibm/javadoc: com.ibm.websphere.appserver.api.persistence_1.0-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/api/ibm/javadoc: com.ibm.websphere.appserver.api.security.spnego_1.0-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/api/ibm/javadoc: com.ibm.websphere.appserver.api.security_1.2-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/api/ibm/javadoc: com.ibm.websphere.appserver.api.servlet_1.1-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/api/ibm/javadoc: com.ibm.websphere.appserver.api.ssl_1.1-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/api/ibm/javadoc: com.ibm.websphere.appserver.api.transaction_1.1-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/api/ibm: schema
Only in 2.4.2/target/liberty/wlp/dev/spi/ibm/javadoc: com.ibm.websphere.appserver.spi.anno_1.1-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/spi/ibm/javadoc: com.ibm.websphere.appserver.spi.application_1.1-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/spi/ibm/javadoc: com.ibm.websphere.appserver.spi.artifact_1.2-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/spi/ibm/javadoc: com.ibm.websphere.appserver.spi.classloading_1.4-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/spi/ibm/javadoc: com.ibm.websphere.appserver.spi.collectivePlugins_2.0-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/spi/ibm/javadoc: com.ibm.websphere.appserver.spi.containerServices_3.0-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/spi/ibm/javadoc: com.ibm.websphere.appserver.spi.httptransport_4.1-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/spi/ibm/javadoc: com.ibm.websphere.appserver.spi.javaeedd_1.3-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/spi/ibm/javadoc: com.ibm.websphere.appserver.spi.restAPIDiscovery_2.0-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/spi/ibm/javadoc: com.ibm.websphere.appserver.spi.restHandler_2.0-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/spi/ibm/javadoc: com.ibm.websphere.appserver.spi.servlet_2.2-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/spi/ibm/javadoc: com.ibm.websphere.appserver.spi.ssl_1.2-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/spi/ibm/javadoc: com.ibm.websphere.appserver.spi.transaction_1.1-javadoc.zip
Only in 2.4.2/target/liberty/wlp/dev/spi/ibm/javadoc: com.ibm.websphere.appserver.spi.wab.configure_1.0-javadoc.zip
```
and the checksums are missing those references as well.



