Inicie sua jornada de desenvolvimento utilizando os recursos disponibilizados pelo Estúdio Skynet, aplique o nossa API que contém uma estrutura completa de observabilidade. Nossa Stack apresenta uma estrutura que utiliza C#, .NET e REST, rodando em um cluster de contêiner, além de contemplar estrutura base de observabilidade que contém: Logging, Trace e Metrics! Nossa API contém uma fácil configuração, desde início de sua jornada (CLI), até a manutenção do código gerado pela nossa Stack.

Oferecemos velocidade e confiança através de nossa Stack para times de desenvolvimento, no processo de conectar softwares da sua empresa através de uma API.  

Ao iniciar o seu produto através do nosso template base, trazemos a possibilidade de você compilar e executar o projeto localmente. É importante lembrar que a nossa Stack não é intrusiva. Nós criamos código para ajudar times de desenvolvimento, mas cada desenvolvedor opta pelo que prefere usar.  

Para começar sua jornada de desenvolvimento utilizando os recursos disponibilizados pelo Estúdio Skynet, aplique o template base para iniciar o desenvolvimento de uma API completa usando C#, .NET e REST, rodando em um cluster de contêiner.  

### Visão Geral
O **rest-app-cs-template** adiciona em uma stack a capacidade de provisionar serviços rest.

### Pré-requisitos
Para utilizar esse template você precisa utilizar o `CLI` do `StackSpot` que você pode baixar [**aqui**](https://stackspot.com.br/).
- .NET 5 e/ou 6 instalados.
- Ao criar sua pipeline da AWS **e não encontrar no campo "Runtime" a opção do dotnet: 5.0**, siga as orientações descritas neste [**link**](https://confluence-itau.tecnologia.prod.ops.aws.cloud.ihf/x/GDaYJ).

### Inputs
Os inputs necessários para utilizar o template são:
| **Campo** | **Valor** | **Descrição** |
| :--- | :--- | :--- |
| Project Name| ex.: MyApp | Nome da aplicação  |
| Target Framework| 5 ou 6 | Framework em que a API será criada  |

## Execução do projeto criado

Após criar o projeto, acesse o diretório onde se encontra a `Solution` e os demais arquivos do projeto. Execute o seguinte comando:

```bash
    dotnet restore <meu App>.Api.sln
```

Realize também a compilação do projeto, através do comando abaixo:

```bash
    dotnet build <meu App>.Api.sln
```

Realize a execução dos testes unitários e de integração. Execute o seguinte comando:

```bash
dotnet test <meu App>.Api.sln
```

Para testar a aplicação, ainda no mesmo diretório da `Solution`. Execute o seguinte comando:

```bash
    dotnet run --project ./src/<meu App>.Api/<meu App>.Api.csproj
```

### Configuração do Docker

Para que o Docker funcione, você precisará adicionar um certificado SSL temporário e montar um volume para manter esse certificado.
Você pode encontrar no [Microsoft Docs](https://docs.microsoft.com/en-us/aspnet/core/security/docker-https?view=aspnetcore-6.0) que descrevem as etapas necessárias para Windows, macOS e Linux.

Para Windows:
O seguinte precisará ser executado a partir do seu terminal para criar um certificado:

```bash
dotnet dev-certs https -ep %USERPROFILE%\.aspnet\https\aspnetapp.pfx -p Your_password123
dotnet dev-certs https --trust
```

NOTA: Ao usar o PowerShell, substitua %USERPROFILE% por $env:USERPROFILE.

PARA macOS:
```bash
dotnet dev-certs https -ep ${HOME}/.aspnet/https/aspnetapp.pfx -p Your_password123
dotnet dev-certs https --trust
```

PARA Linux:
```bash
dotnet dev-certs https -ep ${HOME}/.aspnet/https/aspnetapp.pfx -p Your_password123
dotnet dev-certs https --trust
```

Para construir e executar os containers docker, execute o comando abaixo na raiz da solução onde você encontra o arquivo docker-compose.yml

 ```bash
 docker-compose -f 'docker-compose.yml' up --build
 ```

Em seguida, abra http://localhost:5000 no seu navegador.

> Dica: Você também pode utilizar uma IDE (VSCode, Visual Studio) de sua preferência para realizar os passos acima.

Com a aplicação em execução, acesse a url https://localhost:5001/swagger, acesse os detalhes da aplicação e clique em "Ir para localhost (não seguro)" no Chrome. Ao acessar o endereço acima, você poderá ver a documentação (*Swagger*) da sua aplicação.

> Dica: Neste caso, a estrutura de projeto com exemplo foi criada automaticamente. 

Aplicando este projeto base, ele já vem com as capacidades de observability citadas abaixo: 

#### Logging

Se você possui vários projetos, microsserviços e ou rotinas, com este plugin você conseguirá manter a qualidade e padrão de informações de log para todas elas, considerando diferentes níveis de log. Isso permite definir Tags para que você consiga quantificar e/ou classificar erros, trazendo uma visão de falhas recorrentes ou permitindo a prevenção de problemas futuros.  
Também oferecemos a facilidade de integração com ferramentas como Splunk ou AWS Cloud Watch para monitorar e visualizar os dados, garantindo observabilidade de suas aplicações.  

#### Metrics

Através do plugin de Metrics facilitamos a medição da quantidade de requisições em um endpoint crítico ou monitorar o tamanho de payloads que são enviados para sua API.

#### Trace

Através do plugin de Trace facilitamos a instrumentação de telemetria da sua API através do Opentelemetry com exporter para Jaeger e AWS X-Ray.

#### ErrorHandler

Manipule, padronize e personalize os retornos de erro em sua api REST.
  
Ao fim do ciclo de desenvolvimento, utilizando todas as capacidades que nossa Stack oferece, podemos ter uma estrutura completa como ilustra a imagem abaixo:

![Caso de Uso](https://raw.githubusercontent.com/stack-spot/skynet-dotnet-stack/main/use-case-observability.png "Caso de Uso")

Veja mais detalhes de cada plugin, casos e formas de uso disponíveis através do menu lateral esquerdo. 
