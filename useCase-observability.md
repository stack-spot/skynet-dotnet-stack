Oferecemos velocidade e confiança através de nossa Stack para times de desenvolvimento, no processo de conectar softwares da sua empresa através de uma API.  

Ao iniciar o seu produto através do nosso template base, trazemos a possibilidade de você compilar e executar o projeto localmente. É importante lembrar que a nossa Stack não é intrusiva. Nós criamos código para ajudar times de desenvolvimento, mas cada desenvolvedor opta pelo que prefere usar.  

Para começar sua jornada de desenvolvimento utilizando os recursos disponibilizados pelo Estúdio Skynet, aplique o template base para iniciar o desenvolvimento de uma API completa usando C#, .NET e REST, rodando em um cluster de contêiner.  

### Visão Geral
O **rest-app-cs-template** adiciona em uma stack a capacidade de provisionar serviços rest.

### Pré-requisitos
Para utilizar esse template você precisa utilizar o `CLI` do `StackSpot` que você pode baixar [**aqui**](https://stackspot.com.br/).
- .NET 5 e/ou 6 instalados.

### Inputs
Os inputs necessários para utilizar o template são:
| **Campo** | **Valor** | **Descrição** |
| :--- | :--- | :--- |
| Project Name| ex.: MyApp | Nome da aplicação  |
| Target Framework| 5 ou 6 | Framework em que a API será criada  |

## Execução do projeto criado

Após criar o projeto, acesse o diretório `src` onde se encontra a `Solution` e os demais arquivos do projeto. Execute o seguinte comando:

```bash
    dotnet restore
```

Realize também a compilação do projeto, através do comando abaixo:

```bash
    dotnet build
```

Para testar a aplicação, acesse o diretório que contém o projeto da API (`.csproj`). O nome do diretório é o `<meu App>.Api`. Execute o seguinte comando:

```bash
    dotnet run
```

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

  
Ao fim do ciclo de desenvolvimento, utilizando todas as capacidades que nossa Stack oferece, podemos ter uma estrutura completa como ilustra a imagem abaixo:

![Caso de Uso](https://raw.githubusercontent.com/stack-spot/skynet-dotnet-stack/main/use-case-observability.png "Caso de Uso")

Veja mais detalhes de cada plugin, casos e formas de uso disponíveis através do menu lateral esquerdo. 