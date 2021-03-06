Inicie a sua jornada de desenvolvimento utilizando os recursos disponibilizados pelo Estúdio Skynet. Aplique a nossa API que contém uma estrutura completa de observabilidade. A Stack apresenta uma estrutura que utiliza C#, .NET e REST, rodando em um cluster de contêiner, além de contemplar estrutura base de observabilidade que contém: **Logging**, **Trace** e **Metrics**! A API pode ser configurada facilmente, desde o início de sua jornada na STK CLI, até a manutenção do código gerado pela Stack.

No processo de conectar softwares de uma empresa através de uma API, a Stack oferece velocidade e confiança para times de desenvolvimento.

Ao iniciar o seu produto através do template base oferecido, é possível compilar e executar o projeto localmente. É importante lembrar que a Stack não é intrusiva. Os códigos são criados para ajudar times de desenvolvimento, mas cada desenvolvedor opta pelo que prefere usar.  

Para começar sua jornada de desenvolvimento utilizando os recursos disponibilizados pelo Estúdio Skynet, aplique o template base para iniciar o desenvolvimento de uma API completa usando **C#**, **.NET** e **REST**, rodando em um cluster de contêiner.   

### Visão Geral
O template **rest-app-cs-template** adiciona em uma stack a capacidade de provisionar serviços REST.

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

Após criar o projeto, acesse o diretório onde está a **`Solution`** e os demais arquivos do projeto. Depois disso, execute o seguinte comando:  

```bash
    dotnet restore <meu App>.Api.sln
```

Faça a compilação do projeto, através do seguinte comando:  

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
Você pode encontrar isso no [**Microsoft Docs**](https://docs.microsoft.com/en-us/aspnet/core/security/docker-https?view=aspnetcore-6.0), que descreve as etapas necessárias para **Windows**, **macOS** e **Linux**.

- Para Windows:  
O seguinte comando precisará ser executado a partir do seu terminal para criar um certificado:  

```bash
dotnet dev-certs https -ep %USERPROFILE%\.aspnet\https\aspnetapp.pfx -p Your_password123
dotnet dev-certs https --trust
```

NOTA: Ao usar o PowerShell, substitua **%USERPROFILE%** por **$env:USERPROFILE**.

- Para macOS:  

```bash
dotnet dev-certs https -ep ${HOME}/.aspnet/https/aspnetapp.pfx -p Your_password123
dotnet dev-certs https --trust
```

- Para Linux:  
```bash
dotnet dev-certs https -ep ${HOME}/.aspnet/https/aspnetapp.pfx -p Your_password123
dotnet dev-certs https --trust
```

1. Para construir e executar os containers Docker, execute o seguinte comando na raiz da solução onde você encontra o arquivo **`docker-compose.yml`**: 

 ```bash
 docker-compose -f 'docker-compose.yml' up --build
 ```

2. Em seguida, abra http://localhost:5000 no seu navegador.

> Dica: Você também pode utilizar uma IDE (VSCode, Visual Studio) de sua preferência para realizar os passos acima.

Com a aplicação em execução, acesse a url https://localhost:5001/swagger, acesse os detalhes da aplicação e clique em **"Ir para localhost (não seguro)"** no Chrome. Ao acessar o endereço acima, você poderá ver a documentação (*Swagger*) da sua aplicação.

> Dica: Neste caso, a estrutura de projeto com exemplo foi criada automaticamente. 

Aplicando este projeto base, ele já vem com as capacidades de Observability citadas abaixo: 

#### Logging  
Se você possui vários projetos, microsserviços e ou rotinas, com este plugin você conseguirá manter a qualidade e padrão de informações de log para todas elas, considerando diferentes níveis de log. Isso permite definir Tags para que você consiga quantificar e/ou classificar erros, trazendo uma visão de falhas recorrentes ou permitindo a prevenção de problemas futuros.  
Além disso, é fácil fazer a integração com ferramentas como Splunk ou AWS Cloud Watch para monitorar e visualizar os dados, garantindo observabilidade de suas aplicações.  

#### Metrics  
O plugin de Metrics facilita a medição da quantidade de requisições em um endpoint crítico ou o monitoramento do tamanho de payloads que são enviados para a sua API.  

#### Trace  
Já o plugin de Trace facilita a instrumentação de telemetria da sua API, através do Opentelemetry com exporter para Jaeger e AWS X-Ray.  

#### ErrorHandler  
Manipule, padronize e personalize os retornos de erro em sua API REST.
  
Ao fim do ciclo de desenvolvimento, utilizando todas as capacidades que a Stack oferece, é possível ter uma estrutura completa como ilustra a imagem abaixo:  

![Caso de Uso](https://raw.githubusercontent.com/stack-spot/skynet-dotnet-stack/main/use-case-observability.png "Caso de Uso")

Veja mais detalhes de cada plugin, casos e formas de uso disponíveis através do menu lateral esquerdo. 
