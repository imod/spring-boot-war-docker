# spring-boot-war-docker

an example showing problem when building a docker image with the spring boot maven plugin for a WAR project

```
$> mvn spring-boot:build-image 
[INFO] Scanning for projects...
[INFO] 
[INFO] --------------------------< com.example:demo >--------------------------
[INFO] Building demo 0.0.1-SNAPSHOT
[INFO] --------------------------------[ war ]---------------------------------
[INFO] 
[INFO] >>> spring-boot-maven-plugin:2.4.0:build-image (default-cli) > package @ demo >>>
[INFO] 
[INFO] --- maven-resources-plugin:3.2.0:resources (default-resources) @ demo ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Using 'UTF-8' encoding to copy filtered properties files.
...
...
[INFO]  > Pulled builder image 'paketobuildpacks/builder@sha256:2416307af708a80b7bee5eb79869f40e4afbeb3a27041a4a3408f171cd5a75e1'
[INFO]  > Pulling run image 'docker.io/paketobuildpacks/run:base-cnb' 100%
[INFO]  > Pulled run image 'paketobuildpacks/run@sha256:d7049d9f995e45753d22bff537f49cf4eff94747e5ad6c58894b87a197c3e825'
[INFO]  > Executing lifecycle version v0.9.3
[INFO]  > Using build cache volume 'pack-cache-5cbe5692dbc4.build'
[INFO] 
[INFO]  > Running creator
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  11.326 s
[INFO] Finished at: 2020-12-10T13:50:49+01:00
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.springframework.boot:spring-boot-maven-plugin:2.4.0:build-image (default-cli) on project demo: Execution default-cli of goal org.springframework.boot:spring-boot-maven-plugin:2.4.0:build-image failed: Source must refer to an existing file, got /Users/domi/work/bugs/demo/target/demo-0.0.1-SNAPSHOT.jar -> [Help 1]
[ERROR] 
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR] 
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/PluginExecutionException
$>
```
