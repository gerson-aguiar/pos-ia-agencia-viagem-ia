
<img width="1900" height="781" alt="Captura de tela 2026-03-05 235256" src="https://github.com/user-attachments/assets/290bcc6f-e643-486c-b90c-57bf5ca6fd7d" />


<img width="1905" height="787" alt="Captura de tela 2026-03-05 235247" src="https://github.com/user-attachments/assets/3e448a2f-a5da-4596-8b24-7c4b20544ffe" />


<img width="914" height="535" alt="Captura de tela 2026-03-05 235335" src="https://github.com/user-attachments/assets/64f7cfc1-0b45-484b-9d8b-61db780ddc99" />

```bash
➜ curl -X POST -H "Content-Type: text/plain" -d "Tem viagem para Amazonas? Me de detalhes." http://localhost:8080/travel
### Pacote Aventura Amazônia
O pacote Aventura Amazônia é uma viagem de 7 dias e 6 noites com foco em atividades na selva como a focagem noturna de jacarés, caminhada na selva, e visita a comunidades ribeirinhas. O preço deste pacote é R$ 4.500,00 por pessoa. Em caso de cancelamento, você terá reembolso de 80% dentro de 30 dias de antecedência.

### Pacote Tesouros do Egito
O pacote Tesouros do Egito é uma viagem de 10 dias e 9 noites com atividades como visita às pirâmides de Gizé, cruzeiro no Nilo, e tour pelo Museu do Cairo. O preço deste pacote é R$ 12.800,00 por pessoa. Em caso de cancelação, você terá reembolso de 50% dentro de 30 dias de antecedência.%                                                                                                       
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

This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: <https://quarkus.io/>.

## Running the application in dev mode

You can run your application in dev mode that enables live coding using:

```shell script
./gradlew quarkusDev
```

> **_NOTE:_**  Quarkus now ships with a Dev UI, which is available in dev mode only at <http://localhost:8080/q/dev/>.

## Packaging and running the application

The application can be packaged using:

```shell script
./gradlew build
```

It produces the `quarkus-run.jar` file in the `build/quarkus-app/` directory.
Be aware that it’s not an _über-jar_ as the dependencies are copied into the `build/quarkus-app/lib/` directory.

The application is now runnable using `java -jar build/quarkus-app/quarkus-run.jar`.

If you want to build an _über-jar_, execute the following command:

```shell script
./gradlew build -Dquarkus.package.jar.type=uber-jar
```

The application, packaged as an _über-jar_, is now runnable using `java -jar build/*-runner.jar`.

## Creating a native executable

You can create a native executable using:

```shell script
./gradlew build -Dquarkus.native.enabled=true
```

Or, if you don't have GraalVM installed, you can run the native executable build in a container using:

```shell script
./gradlew build -Dquarkus.native.enabled=true -Dquarkus.native.container-build=true
```

You can then execute your native executable with: `./build/agencia-viagem-ai-1.0.0-SNAPSHOT-runner`

If you want to learn more about building native executables, please consult <https://quarkus.io/guides/gradle-tooling>.

## Related Guides

- REST ([guide](https://quarkus.io/guides/rest)): A Jakarta REST implementation utilizing build time processing and Vert.x. This extension is not compatible with the quarkus-resteasy extension, or any of the extensions that depend on it.
- LangChain4j Ollama ([guide](https://docs.quarkiverse.io/quarkus-langchain4j/dev/guide-ollama.html)): Provides the basic integration of Ollama with LangChain4j

## Provided Code

### REST

Easily start your REST Web Services

[Related guide section...](https://quarkus.io/guides/getting-started-reactive#reactive-jax-rs-resources)
