# API documentation

The API contains two main endpoints. One is for generation of new data called ```origin``` and ``` api/v1 ```

#### Parameters
<table>
    <tr>
        <td><strong>Name</strong></td>
        <td><strong>Type</strong></td>
        <td><strong>Description</strong></td>
    </tr>
    <tr>
        <td><code>api_key</code></td>
        <td>string</td>
        <td>Your own API public key</td>
    </tr>
    <tr>
        <td><code>timestamp</code></td>
        <td>integer</td>
        <td>Current unix timestamp (GMT+0) in <a href="http://www.epochconverter.com/">seconds</a></td>
    </tr>
    <tr>
        <td><code>dev_hash</code></td>
        <td>string</td>
        <td>
            Calculate with <code>timestamp</code> and <code>api_secret</code>
            <br>
            Formula: <code>md5(concatenate(&lt;timestamp&gt;, &lt;api_secret&gt;))</code>
        </td>
    </tr>
</table>

# Installation and docker packaging

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

### Testing locally
This will launch the enrichment API on the local machine and should be accessible through the localhost.
```text
./gradlew tomcatRunWar
```

### Stoping gradle process
Processes need to be stopped manually if timcatRunWar has previously been executed.
```text
./gradlew stop
```

### Docker-compose
Getting started with docker-compose

```bash
gradle war
docker-compose build
docker-compose up
```
