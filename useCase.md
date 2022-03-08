 Desenhe, desenvolva e publique APIs para conectar softwares da empresa no seu produto. Nossa stack API inclui suporte ao protocolo REST, OpenAPI, Clean Arch, observabilidade, conexão com filas, bancos de dados NoSQL, rodando sobre containers Docker na AWS.

 !["Caso de Uso"](https://github.com/stack-spot/skynet-dotnet-stack/blob/main/use-case.png)

 #### Logging

 Se possui vários projetos, microserviços e ou rotinas, com esse plugin você conseguirá manter a qualidade e padrão de informações de log para todas elas considerando diferentes níveis de log, permitindo definir Tags para que você consiga quantificar e/ou classificar erros trazendo uma visão de falhas recorrentes ou permitindo a prevenção de problemas futuros. 
 Poderá utilizar-se de ferramentas como Splunk ou AWS Cloud Watch para monitorar e visualizar os dados e garantindo observabilidade de suas aplicações.

**Exemplo:**
 ```json
    {
        "timeStamp": "2021-04-06T14:50:33.6610795Z",
        "appName": "MyAppName",
        "message": "An unhandled exception has occurred while executing the request.",
        "logger": "Microsoft.AspNetCore.Diagnostics.DeveloperExceptionPageMiddleware",
        "level": "ERROR",
        "tags": ["Tag01", "Tag02"],
        "data": {
            "field1": "Test01",
            "field2": "Test02"
        },
        "exception": {
            "name": "DivideByZeroException",
            "message": "Attempted to divide by zero.",
            "stackTrace": "   at Sample.WebApi.Controllers.SampleController.Get() in ..."
        },
        "context": {
            "spanId": "1af157b8bee48886",
            "traceId": "1af157b8bee48886",
            "correlationId": "614bc03a1eab685315a897fe1405a935"
        }
    }
 ```

 #### Metrics
Medir a quantidade de requisições em um edpoint crítico ou monitorar o tamanho de payloads que são enviados para sua API, com o **metrics plugin** é possível e muito mais para trazer informações e permitir diagnóstico, alertas e relatórios que ajudarão a garantir a disponibilidade e resiliência das APIs.

#### Queue
Imagine estar em um ambiente descentralizado voltado à microserviços e que possua diversas comunicações entre eles através de filas de mensagens. Configurar e implementar o manuseio dessas filas será mais simples com o **queue plugin**. Assim como criar uma classe, será o que você precisará para comunicar com sua fila AWS SQS.
 !["Caso de Uso"](https://github.com/stack-spot/skynet-dotnet-stack/blob/main/use-case-queue.png)

#### Secrets
Lidar com informações sensíveis de sistemas com chaves de APIs, tokens de autenticação ou conexões com bases de dados, tendo em vista a utilização de um Secret Manager como o da AWS ficará mais fácil e seguro com o **secrets plugin** onde ele simplifica o consumo dessas informações e você poderá utilizar no momento que desejar dentro de sua aplicação.


