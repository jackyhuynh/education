# Java, Spring and SpringBoot
## Introduction:
- Package management: Gradle Setup
- Spring Boot: Annotation
- Development IDE: IntelliJ

## Spring Boot module that supports Refactoring
- https://spring.io/guides/gs/multi-module
- https://docs.spring.io/spring-modulith/reference/index.html

## Gradle Setup for Spring Boot

Start with a basic `build.gradle` setup for a Spring Boot project:

```groovy
plugins {
    id 'org.springframework.boot' version '2.7.2'
    id 'io.spring.dependency-management' version '1.0.11.RELEASE'
    id 'java'
}

group = 'com.example'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = '11'

repositories {
    mavenCentral()
}

dependencies {
    implementation 'org.springframework.boot:spring-boot-starter-web'
    implementation 'org.springframework.boot:spring-boot-starter-data-jpa'
    implementation 'org.springframework.boot:spring-boot-starter-security'
    implementation 'org.springframework.boot:spring-boot-starter-thymeleaf'
    implementation 'mysql:mysql-connector-java'
    testImplementation 'org.springframework.boot:spring-boot-starter-test'
}

test {
    useJUnitPlatform()
}
```

## Common Spring Boot Annotations

### 1. `org.springframework.boot`

- **`@SpringBootApplication`**: Marks the main class of a Spring Boot application. It combines `@Configuration`, `@EnableAutoConfiguration`, and `@ComponentScan`.

### 2. `org.springframework.context.annotation`

- **`@Configuration`**: Indicates that a class declares one or more `@Bean` methods and may be processed by the Spring container to generate bean definitions and service requests at runtime.
- **`@Bean`**: Indicates that a method produces a bean to be managed by the Spring container.

### 3. `org.springframework.stereotype`

- **`@Component`**: Indicates that an annotated class is a "component". Such classes are considered as candidates for auto-detection when using annotation-based configuration and classpath scanning.
- **`@Service`**: Specialization of `@Component`, indicating that an annotated class is a service.
- **`@Repository`**: Specialization of `@Component`, indicating that an annotated class is a repository.
- **`@Controller`**: Specialization of `@Component`, indicating that an annotated class is a controller.

### 4. `org.springframework.web.bind.annotation`

- **`@RequestMapping`**: Annotation for mapping web requests onto specific handler classes and/or handler methods.
- **`@GetMapping`**: Shortcut for `@RequestMapping(method = RequestMethod.GET)`.
- **`@PostMapping`**: Shortcut for `@RequestMapping(method = RequestMethod.POST)`.
- **`@PutMapping`**: Shortcut for `@RequestMapping(method = RequestMethod.PUT)`.
- **`@DeleteMapping`**: Shortcut for `@RequestMapping(method = RequestMethod.DELETE)`.
- **`@PatchMapping`**: Shortcut for `@RequestMapping(method = RequestMethod.PATCH)`.

### 5. `org.springframework.web.bind.annotation`

- **`@RequestParam`**: Annotation which indicates that a method parameter should be bound to a web request parameter.
- **`@PathVariable`**: Annotation which indicates that a method parameter should be bound to a URI template variable.
- **`@RequestBody`**: Annotation indicating a method parameter should be bound to the body of the web request.

### 6. `org.springframework.security.config.annotation.web.configuration`

- **`@EnableWebSecurity`**: Add this annotation to an `@Configuration` class to have the Spring Security configuration defined in that class take effect.

### 7. `org.springframework.data.jpa.repository`

- **`@EnableJpaRepositories`**: Used to enable JPA repositories. Will scan the package of the annotated configuration class for Spring Data repositories by default.

### 8. `org.springframework.transaction.annotation`

- **`@Transactional`**: Describes a transaction attribute on an individual method or on a class.

### 9. `org.springframework.cache.annotation`

- **`@EnableCaching`**: Enables Spring's annotation-driven cache management capability.
- **`@Cacheable`**: Indicates that the result of invoking a method (or all methods in a class) can be cached.

### Summary

1. **Spring Boot Application Setup**: `@SpringBootApplication`
2. **Configuration and Bean Definition**: `@Configuration`, `@Bean`
3. **Component Scanning and Stereotypes**: `@Component`, `@Service`, `@Repository`, `@Controller`
4. **Web Request Handling**: `@RequestMapping`, `@GetMapping`, `@PostMapping`, `@PutMapping`, `@DeleteMapping`, `@PatchMapping`, `@RequestParam`, `@PathVariable`, `@RequestBody`
5. **Security**: `@EnableWebSecurity`
6. **Data Access**: `@EnableJpaRepositories`
7. **Transaction Management**: `@Transactional`
8. **Caching**: `@EnableCaching`, `@Cacheable`

## IntelliJ IDE Shortcut

1. **General Shortcuts:**
   - `Cmd + Shift + A`: Find Action
   - `Cmd + O`: Navigate to Class
   - `Cmd + Shift + O`: Navigate to File
   - `Cmd + E`: Recently opened files
   - `Cmd + F12`: Show file structure
   - `Cmd + 1`: Project view
   - `Cmd + Alt + L`: Reformat code
   - `Cmd + /`: Comment/uncomment lines
   - `Cmd + D`: Duplicate current line or selection
   - `Ctrl + Shift + R`: Run the current program
   - `Ctrl + R`: Run the last run configuration

2. **Gradle Specific Shortcuts:**
   - `Cmd + Shift + L`: Toggle Gradle tool window
   - `Cmd + Alt + Shift + /`: Gradle tasks
   - `Cmd + Shift + F12`: Toggle maximize editor
   - `Cmd + Shift + F7`: Highlight usages in file
   - `Cmd + Alt + Left/Right`: Navigate backward/forward
   - `Ctrl + Shift + I`: Open quick definition lookup

3. **Spring Boot Specific Shortcuts:**
   - `Cmd + Shift + A` and type "spring boot": Show Spring Boot actions
   - `Ctrl + Shift + R`: Run Spring Boot Application
   - `Ctrl + Shift + D`: Debug Spring Boot Application
   - `Ctrl + Shift + F8`: View breakpoints
   - `Cmd + F8`: Toggle breakpoint
   - `Ctrl + Alt + Shift + T`: Generate Test

4. **Java Specific Shortcuts:**
   - `Cmd + N`: Generate code
   - `Cmd + B`: Go to declaration
   - `Cmd + Alt + B`: Go to implementation
   - `Ctrl + Space`: Code completion
   - `Ctrl + Shift + Space`: Smart code completion
   - `Cmd + P`: Parameter info
   - `Cmd + Shift + Enter`: Complete statement
   - `Ctrl + Shift + Space`: Type completion

5. **Mac OS Shortcut:**
   - Mission Control: This shows all open windows, desktop spaces, and full-screen apps. Press the Control key and the Up Arrow key (Ctrl + ↑).
   - 
These shortcuts should help you work efficiently on a Mac with IntelliJ IDEA and Spring Boot projects.
