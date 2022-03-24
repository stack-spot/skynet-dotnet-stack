Oferecemos velocidade e confiança através de nossa Stack para times de desenvolvimento, no processo de conectar softwares de sua empresa através de uma API.  

Iniciando seu produto através de nosso template base, trazemos o benefício onde você pode buildar e executar o projeto localmente. Ressaltamos que nossa Stack não é intrusiva, criamos código para ajudar times de desenvolvimento, mas cada desenvolvedor opta pelo o que prefere usar.  

Para começar sua jornada de desenvolvimento utilizando os recursos disponibilizados pelo Estúdio Skynet aplique o template base para iniciar o desenvolvimento de uma API completa usando C#, .NET e REST, rodando em um cluster de contêiner.  

### Visão Geral
O **rest-app-cs-template** adiciona em uma stack a capacidade de provisionar serviços rest.

### Pré-requisitos
Para utilizar esse template você precisa utilizar o `CLI` do `StackSpot` que você pode baixar [**aqui**](https://stackspot.com.br/).
- .NET 5 e/ou 6 instalados.
- Caso não tenha a opção de configuração do **.NET 5 disponível no Service Now**, siga as orientações descritas neste [**link**](https://confluence-itau.tecnologia.prod.ops.aws.cloud.ihf/x/GDaYJ)

### Inputs
Os inputs necessários para utilizar o template são:
| **Campo** | **Valor** | **Descrição** |
| :--- | :--- | :--- |
| Project Name| ex.: MyApp | Nome da aplicação  |
| Target Framework| 5 ou 6 | Framework em que a API será criada  |

## Execução do projeto criado

Após criar o projeto, acesse o diretório `src` onde se econtra a `Solution` e os demais arquivos do projeto. Execute o seguinte comando:

```bash
    dotnet restore
```

Realize também a compilação do projeto, através do comando abaixo:

```bash
    dotnet build
```

Para testar a aplicação, acesse o diretório que contém o projeto da API. O nome do diretório é o `<meu App>.Api`. Execute o seguinte comando:

```bash
    dotnet run
```

> Dica: Você também pode utilizar uma IDE (VSCode, Visual Studio) de sua preferência para realizar os passos acima.

Com a aplicação em execução, acesse a url https://localhost:5001/swagger, acesse os detalhes da aplicação e clique em "Ir para localhost (não seguro)" no Chrome. Ao acessar o endereço acima, você poderá ver a documentação (*Swagger*) da sua aplicação.

> Dica: Neste caso, a estrutura de projeto com exemplo foi criada automaticamente. 

Aplicando o projeto base pode-se adicionar capacidades ao seu template base tais como: 

#### Logging

 Se possui vários projetos, micro serviços e ou rotinas, com esse plugin você conseguirá manter a qualidade e padrão de informações de log para todas elas considerando diferentes níveis de log, permitindo definir Tags para que você consiga quantificar e/ou classificar erros trazendo uma visão de falhas recorrentes ou permitindo a prevenção de problemas futuros. Oferecemos a facilidade de integração com ferramentas como Splunk ou AWS Cloud Watch para monitorar e visualizar os dados e garantindo observabilidade de suas aplicações.

#### Metrics

Através do plugin de Metrics facilitamos a medição da quantidade de requisições em um endpoint crítico ou monitorar o tamanho de payloads que são enviados para sua API.

#### Trace

Através do plugin de Trace facilitamos a instrumentação de telemetria da sua API através do Opentelemetry com exporter para Jaeger e AWS X-Ray.

#### Queue

Imagine estar em um ambiente descentralizado voltado à micro serviços e que possua diversas comunicações entre eles através de filas de mensagens. Configurar e implementar o manuseio dessas filas será mais simples com o queue plugin. Assim como criar uma classe, abstraindo toda a complexidade para comunicação com sua fila AWS SQS.

#### Secrets

Lidar com informações sensíveis de sistemas com chaves de APIs, tokens de autenticação ou conexões com bases de dados, tendo em vista a utilização de um Secret Manager como o da AWS ficará mais fácil e seguro com o secrets plugin onde ele simplifica o consumo dessas informações e você poderá utilizar no momento que desejar dentro de sua aplicação.  

#### Bucket

Manipule arquivos utilizando este plugin que facilita a instrumentação com a Amazon Simple Storage Service (S3), eliminando a complexidade.

#### Repository

Armazenar dados ou documentos de forma trivial é um desafio para quase todos os sistemas, e com esse plugin você tem todas as capacidades do AWS DynamoDB disponíveis de forma simples e rápida.

#### Authentication

Através deste plugin facilitamos a capacidade de verificar se um usuário/API possui acesso a um determinado recurso restrito trazendo segurança para sua API.
  
Ao fim do ciclo de desenvolvimento utilizando todas as capacidades que nossa Stack oferece podemos ter uma estrutura completa como ilustra imagem abaixo:

![Caso de Uso](https://raw.githubusercontent.com/stack-spot/skynet-dotnet-stack/main/use-case.png "Caso de Uso")

Veja mais detalhes de cada plugin disponível através do menu lateral esquerdo onde vocês podem ver detalhes mais aprofundados de cada um, casos de uso e formas de uso. 
