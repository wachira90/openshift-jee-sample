openshift-jee-sample
====================

A sample app to be deployed on openshift environments

Note: to build this repository with maven you must specify "-Popenshift", eg "mvn clean package -Popenshift"

## pom.xml build with profile openshift

```xml
<profiles>
    <profile>
     <!-- When built in OpenShift the 'openshift' profile will be used when invoking mvn. -->
     <!-- Use this profile for any OpenShift specific customization your app will need. -->
     <!-- By default that is to put the resulting archive into the 'deployments' folder. -->
     <!-- http://maven.apache.org/guides/mini/guide-building-for-different-environments.html -->
     <id>openshift</id>
     <build>
        <finalName>SampleApp</finalName>
        <plugins>
          <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-war-plugin</artifactId>
                <version>3.3.2</version>
                <configuration>
                    <failOnMissingWebXml>false</failOnMissingWebXml>
                    <outputDirectory>target</outputDirectory>
              		  <warName>ROOT</warName>
                </configuration>
            </plugin>
        </plugins>
      </build>
    </profile>
  </profiles>
```
