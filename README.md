Steps to reproduce:

- import project in eclipse
- run dolphin:installDist task using Buildship plugin

project dolphin uses java application plugin's *executableDir* that was introduced in Gradle 4.5: it fails with the following log:


`Working Directory: C:\dev\flat\dolphin
Gradle User Home: C:\Users\****\.gradle
Gradle Distribution: Gradle wrapper from target build
Gradle Version: 4.3
Java Home: C:\Program Files (x86)\Java\jdk1.8.0_162
JVM Arguments: None
Program Arguments: None
Build Scans Enabled: false
Offline Mode Enabled: false
Gradle Tasks: installDist


FAILURE: Build failed with an exception.

* Where:
Build file 'C:\dev\flat\dolphin\build.gradle' line: 5

* What went wrong:
A problem occurred evaluating project ':dolphin'.
> Could not set unknown property 'executableDir' for project ':dolphin' of type org.gradle.api.Project.

* Try:
Run with --stacktrace option to get the stack trace. Run with --info or --debug option to get more log output.

* Get more help at https://help.gradle.org

BUILD FAILED in 0s` 

Running `gradlew installDist` this from the command line works as expected.