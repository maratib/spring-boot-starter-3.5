# Spring Boot Starter

## Version: 3.5.5, Lombok, Multi Profiles.

<details>
<summary>Watch out for VSCode specific settings in `.vscode` folder</summary>
**launch.json**

```json
// 
{
    "configurations": [
        {
            "type": "java",
            "name": "Spring Boot-Application<spring>",
            "request": "launch",
            "cwd": "${workspaceFolder}",
            "mainClass": "com.mak.Application",
            "projectName": "spring",
            "args": "--spring.profiles.active=dev",
            "envFile": "${workspaceFolder}/.env",
            "console": "internalConsole",
            "internalConsoleOptions": "openOnSessionStart"
        },
    ]
}
```
**settings.json**
```json
{
    "java.compile.nullAnalysis.mode": "disabled",
    "java.configuration.updateBuildConfiguration": "automatic",
    "testing.automaticallyOpenTestResults": "neverOpen"
}
```
### Move the `resources` director out of spring boot project, for deploy time changes
```xml
<!-- add the following to pom.xml within <build> -->
<resources>
    <resource>
        <directory>config</directory>
        <filtering>true</filtering>
    </resource>
</resources>
```
</details>

## Profiles

```json
// Change profile in launch.json for SpringBoot Extension
"args": "--spring.profiles.active=dev",

//Or
//For Maven change the profile in spring-boot-maven-plugin
//And run the app with maven
mvn spring-boot:run
```
  