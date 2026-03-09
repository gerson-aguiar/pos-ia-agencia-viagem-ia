# Guia de Migração para Spring Boot 3.5.x + Java 25

Este guia contém as dependências e configurações necessárias para migrar o projeto de Quarkus para Spring Boot.

## build.gradle (Spring Boot)

```gradle
plugins {
    id 'java'
    id 'org.springframework.boot' version '3.5.0'
    id 'io.spring.dependency-management' version '1.1.7'
}

group = 'dev.ia'
version = '1.0.0-SNAPSHOT'

java {
    sourceCompatibility = JavaVersion.VERSION_25
    targetCompatibility = JavaVersion.VERSION_25
}

repositories {
    mavenCentral()
    mavenLocal()
}

dependencies {
    // Spring Boot Starters
    implementation 'org.springframework.boot:spring-boot-starter-web'
    
    // LangChain4j para Spring Boot
    implementation 'dev.langchain4j:langchain4j-spring-boot-starter:0.36.2'
    implementation 'dev.langchain4j:langchain4j-ollama:0.36.2'
    implementation 'dev.langchain4j:langchain4j-easy-rag:0.36.2'
    implementation 'dev.langchain4j:langchain4j-embeddings:0.36.2'
    
    // Testes
    testImplementation 'org.springframework.boot:spring-boot-starter-test'
    testImplementation 'io.rest-assured:rest-assured'
}

tasks.named('test') {
    useJUnitPlatform()
}
```

## pom.xml (alternativa Maven)

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 
         https://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    
    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>3.5.0</version>
        <relativePath/>
    </parent>
    
    <groupId>dev.ia</groupId>
    <artifactId>agencia-viagem-ai</artifactId>
    <version>1.0.0-SNAPSHOT</version>
    <name>agencia-viagem-ai</name>
    
    <properties>
        <java.version>25</java.version>
        <langchain4j.version>0.36.2</langchain4j.version>
    </properties>
    
    <dependencies>
        <!-- Spring Boot Starters -->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
        
        <!-- LangChain4j -->
        <dependency>
            <groupId>dev.langchain4j</groupId>
            <artifactId>langchain4j-spring-boot-starter</artifactId>
            <version>${langchain4j.version}</version>
        </dependency>
        
        <dependency>
            <groupId>dev.langchain4j</groupId>
            <artifactId>langchain4j-ollama</artifactId>
            <version>${langchain4j.version}</version>
        </dependency>
        
        <dependency>
            <groupId>dev.langchain4j</groupId>
            <artifactId>langchain4j-easy-rag</artifactId>
            <version>${langchain4j.version}</version>
        </dependency>
        
        <dependency>
            <groupId>dev.langchain4j</groupId>
            <artifactId>langchain4j-embeddings</artifactId>
            <version>${langchain4j.version}</version>
        </dependency>
        
        <!-- Testes -->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
        </dependency>
        
        <dependency>
            <groupId>io.rest-assured</groupId>
            <artifactId>rest-assured</artifactId>
            <scope>test</scope>
        </dependency>
    </dependencies>
    
    <build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
            </plugin>
        </plugins>
    </build>
</project>
```

## application.properties (Spring Boot)

```properties
# Configuração do Ollama
langchain4j.ollama.base-url=http://localhost:11434
langchain4j.ollama.chat-model.model-name=mistral:7b-instruct-q4_0
langchain4j.ollama.timeout=600s

# Configuração do RAG
langchain4j.easy-rag.path=src/main/resources/rag
```

## Mapeamento de Dependências

| Quarkus | Spring Boot |
|---------|-------------|
| `quarkus-rest` | `spring-boot-starter-web` |
| `quarkus-arc` (CDI) | Spring DI (nativo) |
| `quarkus-langchain4j-ollama` | `langchain4j-spring-boot-starter` + `langchain4j-ollama` |
| `quarkus-langchain4j-easy-rag` | `langchain4j-easy-rag` |

## Mudanças no Código Java

### Anotações

| Quarkus | Spring Boot |
|---------|-------------|
| `@Path("/travel")` | `@RestController` + `@RequestMapping("/travel")` |
| `@POST` | `@PostMapping` |
| `@Inject` | `@Autowired` ou injeção por construtor |
| `@RegisterAiService` | `@Component` + configuração Spring |
| `@Consumes(MediaType.TEXT_PLAIN)` | `consumes = MediaType.TEXT_PLAIN_VALUE` |
| `@Produces(MediaType.TEXT_PLAIN)` | `produces = MediaType.TEXT_PLAIN_VALUE` |

### Exemplo: TravelAgentResource

**Quarkus:**
```java
@Path("/travel")
public class TravelAgentResource {
    @Inject
    TravelAgentAssistant assistant;

    @POST
    @Consumes(MediaType.TEXT_PLAIN)
    @Produces(MediaType.TEXT_PLAIN)
    public String ask(String question) {
        return assistant.chat(question);
    }
}
```

**Spring Boot:**
```java
@RestController
@RequestMapping("/travel")
public class TravelAgentResource {
    private final TravelAgentAssistant assistant;

    public TravelAgentResource(TravelAgentAssistant assistant) {
        this.assistant = assistant;
    }

    @PostMapping(consumes = MediaType.TEXT_PLAIN_VALUE, 
                 produces = MediaType.TEXT_PLAIN_VALUE)
    public String ask(@RequestBody String question) {
        return assistant.chat(question);
    }
}
```

### Exemplo: TravelAgentAssistant

**Quarkus:**
```java
@RegisterAiService
public interface TravelAgentAssistant {
    String chat(String userMessage);
}
```

**Spring Boot:**
```java
@Component
public interface TravelAgentAssistant {
    String chat(String userMessage);
}
```

## Classe Principal (Application)

```java
package dev.ia;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class AgenciaViagemAiApplication {
    public static void main(String[] args) {
        SpringApplication.run(AgenciaViagemAiApplication.class, args);
    }
}
```

## Comandos de Execução

### Desenvolvimento
```bash
# Gradle
./gradlew bootRun

# Maven
./mvnw spring-boot:run
```

### Build
```bash
# Gradle
./gradlew build

# Maven
./mvnw clean package
```

### Executar JAR
```bash
java -jar build/libs/agencia-viagem-ai-1.0.0-SNAPSHOT.jar
```

## Estrutura do Projeto Spring Boot

```
agencia-viagem-ai/
├── src/main/java/dev/ia/
│   ├── AgenciaViagemAiApplication.java  # Classe principal
│   ├── TravelAgentResource.java         # Controller REST
│   └── TravelAgentAssistant.java        # Interface do assistente IA
├── src/main/resources/
│   ├── application.properties           # Configurações
│   └── rag/
│       └── pacotes-viagem.md           # Base de conhecimento
├── build.gradle (ou pom.xml)
└── README.md
```

## Notas Importantes

1. **Java 25**: Certifique-se de ter o JDK 25 instalado
2. **Spring Boot 3.5.x**: Requer Java 17+ (Java 25 é compatível)
3. **LangChain4j**: A versão 0.36.2 é compatível com Spring Boot 3.x
4. **Ollama**: Continua sendo usado da mesma forma, sem mudanças
5. **RAG**: O Easy RAG funciona de forma similar no Spring Boot

## Recursos Adicionais

- [Spring Boot Documentation](https://docs.spring.io/spring-boot/docs/current/reference/html/)
- [LangChain4j Spring Boot Integration](https://docs.langchain4j.dev/integrations/spring-boot)
- [Spring Initializr](https://start.spring.io/) - Para gerar projeto base
