<img width="1900" height="781" alt="Captura de tela 2026-03-05 235256" src="https://github.com/user-attachments/assets/290bcc6f-e643-486c-b90c-57bf5ca6fd7d" />


<img width="1905" height="787" alt="Captura de tela 2026-03-05 235247" src="https://github.com/user-attachments/assets/3e448a2f-a5da-4596-8b24-7c4b20544ffe" />


<img width="914" height="535" alt="Captura de tela 2026-03-05 235335" src="https://github.com/user-attachments/assets/64f7cfc1-0b45-484b-9d8b-61db780ddc99" />

```bash
➜ curl -X POST -H "Content-Type: text/plain" -d "Tem viagem para Amazonas? Me de detalhes." http://localhost:8080/travel
### Pacote Aventura Amazônia
O pacote Aventura Amazônia é uma viagem de 7 dias e 6 noites com foco em atividades na selva como a focagem noturna de jacarés, caminhada na selva, e visita a comunidades ribeirinhas. O preço deste pacote é R$ 4.500,00 por pessoa. Em caso de cancelamento, você terá reembolso de 80% dentro de 30 dias de antecedência.

### Pacote Tesouros do Egito
O pacote Tesouros do Egito é uma viagem de 10 dias e 9 noites com atividades como visita às pirâmides de Gizé, cruzeiro no Nilo, e tour pelo Museu do Cairo. O preço deste pacote é R$ 12.800,00 por pessoa. Em caso de cancelamento, você terá reembolso de 50% dentro de 30 dias de antecedência.%                                                                                                       
~ took 1m 3.4s …
➜ curl -X POST -H "Content-Type: text/plain" -d "Tem viagem para Amazonas? Me de detalhes." http://localhost:8080/travel
O Pacote Aventura Amazônia é um pacote turístico de sete dias e seis noites, que inclui atividades como focagem noturna de jacarés, caminhada na selva e visita a comunidades ribeirinhas. O preço do pacote é R$ 4.500,00 por pessoa e a política de cancelação permite um reembolso de 80% com trinta dias de antecedência.

Já o Pacote Tesouros do Egito é um pacote turístico de dez dias e nove noites, que inclui atividades como visita às pirâmides de Gizé, cruzeiro no Nilo e tour pelo Museu do Cairo. O preço do pacote é R$ 12.800,00 por pessoa e a política de cancelação permite um reembolso de 50% com trinta dias de antecedência.%                                                                                 
~ took 47.5s …
➜ curl -X POST -H "Content-Type: text/plain" -d "Tem viagem para Amazonas? Me de detalhes." http://localhost:8080/travel
### Pacote Aventura Amazônia
* Duração: 7 dias e 6 noites.
* Atividades: Focagem noturna de jacarés, caminhada na selva, visita a comunidades ribeirinhas.
* Política de cancelação: Reembolso de 80% com 30 dias de antecedência.
* Preço: R$ 4.500,00 por pessoa.%                                                                                                  
  ~ took 24.0s …
  ➜ curl -X POST -H "Content-Type: text/plain" -d "Tem viagem para Amazonas? Me de detalhes." http://localhost:8080/travel

Obrigado! Eu entendi. O Pacote Aventura Amazônia tem uma duração de 7 dias e 6 noites, com atividades como focagem noturna de jacarés, caminhada na selva e visita a comunidades ribeirinhas. O preço deste pacote é R$ 4.500,00 por pessoa e a política de cancelação oferece um reembolso de 80% com antecedência de 30 dias.
Já o Pacote Tesouros do Egito tem uma duração de 10 dias e 9 noites, com atividades como visita às pirâmides de Gizé, cruzeiro no Nilo e tour pelo Museu do Cairo. O preço deste pacote é R$ 12.800,00 por pessoa e a política de cancelação oferece um reembolso de 50% com antecedência de 30 dias.
Isso é tudo que estou capaz de informar neste momento. Se você tem mais questões ou precisa de mais detalhes, por favor, não hesite a perguntar!%                                                                                                                     
~ took 47.2s …
➜ curl -X POST -H "Content-Type: text/plain" -d "Tem viagem para Amazonas? Me de detalhes." http://localhost:8080/travel
O Pacote Aventura Amazônia durará 7 dias e 6 noites, durante este tempo você terá a oportunidade de participar de atividades como focagem noturna de jacarés, caminhada na selva e visita à comunidades ribeirinhas. Se você precisar cancelar seu pacote pode fazer isso com antecedência de 30 dias, receberá um reembolso de 80%. O custo deste pacote é R$ 4.500,00 por pessoa.

Já o Pacote Tesouros do Egito durará 10 dias e 9 noites. Você terá a chance de visitar as pirâmides de Gizé, fazer cruzeiro no Nilo e participar de uma tour pelo Museu do Cairo. Se você precisa cancelar seu pacote pode fazer isso com antecedência de 30 dias, receberá um reembolso de 50%. O custo deste pacote é R$ 12.800,00 por pessoa.

Espero que esteja claro! Se precisar mais informação ou tem alguma dúvida não heite em perguntar.%                                 
~ took 50.0s …
```

curl:
```shell
 curl -X POST -H "Content-Type: text/plain" -d "Estou planejando uma viagem para o Japao. Qual a melhor epoca do ano para visitar e por que? Responsa em portugues." http://localhost:8080/travel 
```



# agencia-viagem-ai

Assistente inteligente de agência de viagens construído com Quarkus e LangChain4j. Utiliza RAG (Retrieval-Augmented Generation) para responder perguntas sobre pacotes turísticos baseado em documentação interna.

## Tecnologias

- **Quarkus 3.32.1** - Framework Java reativo
- **LangChain4j** - Integração com modelos de linguagem
- **Ollama** - Servidor local de LLM (Mistral 7B)
- **Easy RAG** - Sistema de busca em documentos
- **Java 17**
- **Gradle**

## Detalhes Técnicos

### Framework e Runtime

**Quarkus 3.32.1**
- Framework Java nativo para Kubernetes otimizado para GraalVM e HotSpot
- Startup ultrarrápido e baixo consumo de memória
- Hot reload em modo desenvolvimento
- Suporte nativo a programação reativa e imperativa

### Dependências Principais

**quarkus-rest**
- Implementação Jakarta REST (JAX-RS) usando Vert.x
- Processamento em tempo de build para melhor performance
- Suporte a endpoints REST síncronos e assíncronos

**quarkus-arc**
- Container CDI (Contexts and Dependency Injection) do Quarkus
- Injeção de dependências em tempo de build
- Gerenciamento de ciclo de vida de beans

**quarkus-langchain4j-ollama**
- Integração entre Quarkus e LangChain4j para Ollama
- Cliente HTTP otimizado para comunicação com servidor Ollama
- Suporte a streaming de respostas
- Configuração declarativa via application.properties

**quarkus-langchain4j-easy-rag**
- Sistema RAG (Retrieval-Augmented Generation) simplificado
- Indexação automática de documentos em formato Markdown, PDF, TXT
- Embedding e busca vetorial para recuperação de contexto
- Integração transparente com o modelo de linguagem

### Modelo de IA

**Mistral 7B Instruct (Q4_0)**
- Modelo de linguagem com 7 bilhões de parâmetros
- Versão quantizada Q4_0 (4-bit) para otimização de memória
- Especializado em seguir instruções (instruct-tuned)
- Execução local via Ollama sem necessidade de API externa
- Suporte a português e múltiplos idiomas

### Arquitetura RAG

**Pipeline de Processamento**
1. **Ingestão**: Documentos em `src/main/resources/rag/` são carregados na inicialização
2. **Chunking**: Textos divididos em segmentos menores para melhor recuperação
3. **Embedding**: Conversão de texto em vetores numéricos
4. **Indexação**: Armazenamento em índice vetorial para busca semântica
5. **Retrieval**: Busca dos chunks mais relevantes baseado na pergunta do usuário
6. **Augmentation**: Contexto recuperado é injetado no prompt do LLM
7. **Generation**: Modelo gera resposta usando o contexto fornecido

### Build e Empacotamento

**Gradle 9.3.1**
- Sistema de build com cache incremental
- Suporte a compilação nativa com GraalVM
- Geração de uber-jar ou jar modular
- Integração com Quarkus Dev Mode

## Arquitetura

O projeto implementa um chatbot que:
1. Recebe perguntas via API REST
2. Busca contexto relevante nos documentos (RAG)
3. Gera respostas personalizadas usando IA
4. Retorna informações sobre pacotes turísticos

### Componentes

- **TravelAgentResource**: Endpoint REST `/travel` que aceita perguntas em texto plano
- **TravelAgentAssistant**: Interface anotada com `@RegisterAiService` para processamento de IA
- **Base de conhecimento**: Arquivos em `src/main/resources/rag/` com informações dos pacotes

## Pré-requisitos

- Java 17+
- Gradle
- Ollama instalado e rodando

## Configuração do Ollama

### 1. Instalar o Ollama

```bash
# Linux
curl -fsSL https://ollama.com/install.sh | sh

# macOS
brew install ollama

# Windows
# Baixe o instalador em https://ollama.com/download
```

### 2. Iniciar o servidor Ollama

```bash
ollama serve
```

### 3. Baixar o modelo Mistral

```bash
ollama pull mistral:7b-instruct-q4_0
```

### 4. Verificar se o modelo está disponível

```bash
ollama list
```

## Como Executar

### 1. Clonar o repositório

```bash
git clone <url-do-repositorio>
cd agencia-viagem-ai
```

### 2. Executar em modo desenvolvimento

```bash
./gradlew quarkusDev
```

A aplicação estará disponível em `http://localhost:8080`

> **Nota:** O Quarkus Dev UI está disponível em `http://localhost:8080/q/dev/`

### 3. Testar a API

```bash
curl -X POST -H "Content-Type: text/plain" \
  -d "Tem viagem para Amazonas? Me dê detalhes." \
  http://localhost:8080/travel
```

Outros exemplos:

```bash
# Perguntar sobre pacotes disponíveis
curl -X POST -H "Content-Type: text/plain" \
  -d "Quais pacotes de viagem vocês oferecem?" \
  http://localhost:8080/travel

# Perguntar sobre política de cancelamento
curl -X POST -H "Content-Type: text/plain" \
  -d "Qual a política de cancelamento do pacote Egito?" \
  http://localhost:8080/travel
```

## Pacotes Disponíveis

### Pacote Aventura Amazônia
- **Duração**: 7 dias e 6 noites
- **Atividades**: Focagem noturna de jacarés, caminhada na selva, visita a comunidades ribeirinhas
- **Preço**: R$ 4.500,00 por pessoa
- **Cancelamento**: Reembolso de 80% com 30 dias de antecedência

### Pacote Tesouros do Egito
- **Duração**: 10 dias e 9 noites
- **Atividades**: Visita às pirâmides de Gizé, cruzeiro no Nilo, tour pelo Museu do Cairo
- **Preço**: R$ 12.800,00 por pessoa
- **Cancelamento**: Reembolso de 50% com 30 dias de antecedência

## Configuração

As configurações estão em `src/main/resources/application.properties`:

```properties
# URL do Ollama
quarkus.langchain4j.ollama.base-url=http://localhost:11434

# Modelo a ser utilizado
quarkus.langchain4j.ollama.chat-model.model-id=mistral:7b-instruct-q4_0

# Timeout para respostas
quarkus.langchain4j.ollama.timeout=600s

# Diretório com documentos para RAG
quarkus.langchain4j.easy-rag.path=src/main/resources/rag
```

## Adicionando Novos Pacotes

Para adicionar novos pacotes turísticos:

1. Edite o arquivo `src/main/resources/rag/pacotes-viagem.md`
2. Adicione as informações no formato Markdown
3. Reinicie a aplicação (ou aguarde o hot reload em dev mode)

Exemplo:

```markdown
### Pacote Aventura na Patagônia
* Duração: 5 dias e 4 noites.
* Atividades: Trekking em geleiras, observação de fauna, passeio de barco.
* Política de cancelamento: Reembolso de 70% com 30 dias de antecedência.
* Preço: R$ 6.800,00 por pessoa.
```

## Build e Deploy

### Gerar JAR executável

```bash
./gradlew build
java -jar build/quarkus-app/quarkus-run.jar
```

### Gerar uber-jar

```bash
./gradlew build -Dquarkus.package.jar.type=uber-jar
java -jar build/*-runner.jar
```

### Gerar executável nativo

```bash
# Com GraalVM instalado
./gradlew build -Dquarkus.native.enabled=true

# Usando container
./gradlew build -Dquarkus.native.enabled=true -Dquarkus.native.container-build=true

# Executar
./build/agencia-viagem-ai-1.0.0-SNAPSHOT-runner
```

## Estrutura do Projeto

```
agencia-viagem-ai/
├── src/main/java/dev/ia/
│   ├── TravelAgentResource.java      # Endpoint REST
│   └── TravelAgentAssistant.java     # Interface do assistente IA
├── src/main/resources/
│   ├── application.properties        # Configurações
│   └── rag/
│       └── pacotes-viagem.md        # Base de conhecimento
├── build.gradle                      # Dependências
└── README.md
```

## Troubleshooting

### Ollama não está respondendo

Verifique se o Ollama está rodando:

```bash
curl http://localhost:11434/api/tags
```

### Modelo não encontrado

Certifique-se de que o modelo foi baixado:

```bash
ollama pull mistral:7b-instruct-q4_0
```

### Timeout nas respostas

Aumente o timeout em `application.properties`:

```properties
quarkus.langchain4j.ollama.timeout=900s
```

## Recursos Adicionais

- [Documentação do Quarkus](https://quarkus.io/)
- [Quarkus LangChain4j](https://docs.quarkiverse.io/quarkus-langchain4j/dev/index.html)
- [Ollama](https://ollama.com/)
- [LangChain4j](https://docs.langchain4j.dev/)
