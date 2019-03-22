# Java Adapter


Java Adapter is a service layer that create artifact jira-tm-report.xml. 

### Installation

Java Adapter requires at least Java 8 to run.

in your pom.xml file define new repository:
```java
<repository>
            <id>adapter-java-v2-core-mvn-repo</id>
            <url>https://raw.github.com//at-lab-development/adapter-java-v2-core/mvn-repo</url>
            <snapshots>
                <enabled>true</enabled>
                <updatePolicy>always</updatePolicy>
            </snapshots>
</repository>
```
then add dependency:
```java
 <dependency>
            <groupId>com.epam.jira</groupId>
            <artifactId>adapter-java-core</artifactId>
            <version>2.0</version>
</dependency>
```


### Usage

To use Java Adapter call com.epam.jira.core.TestResultProcessor class methods:

| Method | Description |
| ------ | ------ |
| void startJiraAnnotatedTest(String jiraKey) | save previous test and/or create new test entry with Jira key. **Required to start** |
| void setStatus(String status) | set status of test (Passed, Failed, Out of scope, Untested) |
| void addException(Throwable throwable) | add Throwable to test description |
| void addToSummary(String toAdd) | add any text to test description |
| void addParameter(String title, String value) | add parameter in test description (a table with title-value pair) |
| void addAttachment(File attachment) | attach a file (max size depends of Jira settings) |
| void setTime(String time) | set duration of test |
| void saveResults() | save last test and create jira-tm-report.xml. **Required to finish** |
