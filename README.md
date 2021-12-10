# How to load external jar in Spring Boot
1. Add dependency
> Don't depend on mysql-connector-java
```
    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>

        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
        </dependency>

        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-jdbc</artifactId>
        </dependency>

<!--        <dependency>-->
<!--            <groupId>mysql</groupId>-->
<!--            <artifactId>mysql-connector-java</artifactId>-->
<!--&lt;!&ndash;            <scope>test</scope>&ndash;&gt;-->
<!--        </dependency>-->
    </dependencies>
```
2. Modify spring-boot-maven-plugin `layout` to `zip`
```
<build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
                <configuration>
                    <layout>ZIP</layout>
                </configuration>
            </plugin>
        </plugins>
    </build>
```
3. Start application
```
java -Dloader.path=/Users/kuanghaochuan/Projects/java-test/as/spring-boot-maven-dd/test/mysql-connector-java-8.0.27.jar -jar spring-boot-maven-dd-0.0.1-SNAPSHOT.jar
```