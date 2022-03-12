Para times de desenvolvimento que têm a necessidade de conectar softwares de sua empresa através de uma API nossa Stack oferece velocidade e confiança neste processo.

Iniciando seu produto através de nosso template base, trazemos o benefício onde o projeto já pode ser buildado e executado localmente. Vale ressaltar que nossa Stack não é intrusiva, criamos código para ajudar times de desenvolvimento, cada desenvolvedor opta pelo o que quer usar.

Para começar sua jornada de desenvolvimento utilizando os recursos disponibilizados pelo Estúdio Skynet aplique o template base para iniciar o desenvolvimento de uma API completa usando C#, .NET e REST, rodando em um cluster de contêiner. 

### Visão Geral
O **rest-app-cs-template** adiciona em uma stack a capacidade de provisionar serviços rest.

### Pré-requisitos
Para utilizar esse template você precisa utilizar o `cli` do `StackSpot` que você pode baixar [**aqui**](https://stackspot.com.br/).
- .NET 5 e/ou 6 instalados.

### Inputs
Os inputs necessários para utilizar o template são:
| **Campo** | **Valor** | **Descrição** |
| :--- | :--- | :--- |
| Project Name| ex.: MyApp | Nome da aplicação  |
| Target Framework| 5 ou 6 | Framework em que a API será criada  |

## Execução do projeto criado

Após criar o projeto, acesse o diretório `src` e execute o seguinte comando:

```bash
    dotnet restore
```

Realize também a compilação do projeto, através do comando abaixo:

```bash
    dotnet build
```

Para testar a aplicação, acesse o diretório que contém o projeto da API. O nome do diretório é o `<meu App>.Api`. Dentro deste diretório se encontra a `Solution` e os demais arquivos do projeto, execute o seguinte comando:

```bash
    dotnet run
```

> Dica: Você também pode utilizar uma IDE (VSCode, Visual Studio) de sua preferência para realizar os passos acima.

Com a aplicação em execução, acesse a url https://localhost:5001/swagger, acesse os detalhes da aplicação e clique em "Ir para localhost (não seguro)". Ao acessar o endereço acima, você poderá ver a documentação (*Swagger*) de sua aplicação.

> Dica: Neste caso, a estrutura de projeto com exemplo foi criada automaticamente. 

Aplicando este projeto base, ele já vem com as capacidades de observability citadas abaixo: 

#### Logging

 Se possui vários projetos, micro serviços e ou rotinas, com esse plugin você conseguirá manter a qualidade e padrão de informações de log para todas elas considerando diferentes níveis de log, permitindo definir Tags para que você consiga quantificar e/ou classificar erros trazendo uma visão de falhas recorrentes ou permitindo a prevenção de problemas futuros. Oferecemos a facilidade de integração com ferramentas como Splunk ou AWS Cloud Watch para monitorar e visualizar os dados e garantindo observabilidade de suas aplicações.

#### Metrics

Através do plugin de Metrics facilitamos a medição da quantidade de requisições em um endpoint crítico ou monitorar o tamanho de payloads que são enviados para sua API.

#### Trace

Através do plugin de Trace facilitamos a instrumentação de telemetria da sua API através do Opentelemetry com exporter para Jaeger e AWS X-Ray.


Neste projeto base também pode-se adicionar capacidades abaixo: 

#### Queue

Imagine estar em um ambiente descentralizado voltado à micro serviços e que possua diversas comunicações entre eles através de filas de mensagens. Configurar e implementar o manuseio dessas filas será mais simples com o queue plugin. Assim como criar uma classe, abstraindo toda a complexidade para comunicação com sua fila AWS SQS.

#### Secrets

Lidar com informações sensíveis de sistemas com chaves de APIs, tokens de autenticação ou conexões com bases de dados, tendo em vista a utilização de um Secret Manager como o da AWS ficará mais fácil e seguro com o secrets plugin onde ele simplifica o consumo dessas informações e você poderá utilizar no momento que desejar dentro de sua aplicação.  

  
Ao fim do ciclo de desenvolvimento utilizando todas as capacidades que nossa Stack oferece podemos ter uma estrutura completa como ilustra imagem abaixo:

![Caso de Uso](https://raw.githubusercontent.com/stack-spot/skynet-dotnet-stack/main/use-case.png "Caso de Uso")

Veja mais detalhes de cada plugin disponível através do menu lateral esquerdo onde vocês podem ver detalhes mais aprofundados de cada um, casos de uso e formas de uso. 