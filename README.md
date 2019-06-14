## Build with Gradle
### Important tasks

<table>
    <tr>
        <th>Task Name</th>
        <th>Description</th>
    </tr>
    <tr>
        <td>war</td>
        <td>Assembles the application WAR file and saves it in the <i>/docker</i> directory</td>
    </tr>
    <tr>
        <td>tomcatRunWar</td>
        <td>Starts a Tomcat instance and deploys the WAR to it</td>
    </tr>
    <tr>
        <td>clean</td>
        <td>Deletes the project build directory and files generated by tasks</td>
    </tr>
    <tr>
        <td>test</td>
        <td>Runs the unit tests using JUnit or TestNG</td>
    </tr>
    <tr>
        <td>check</td>
        <td>Aggregate task that performs verification tasks, such as running the tests</td>
    </tr>
    <tr>
        <td>compileJava</td>
        <td>Compiles production Java source files using the JDK compiler</td>
    </tr>
</table>

### Running tasks

To run gradle task, enter
```text
./gradlew {task_name}
```

### Documentation

<a href="https://docs.gradle.org/current/userguide/java_plugin.html">The Java Plugin documentation</a><br>
<a href="https://docs.gradle.org/current/userguide/war_plugin.html">The War Plugin documentation</a><br>
<a href="https://github.com/bmuschko/gradle-tomcat-plugin">The Tomcat Plugin documentation</a>

### Docker-compose
Getting started with docker-compose

```bash
gradle war
docker-compose build
docker-compose up
```
