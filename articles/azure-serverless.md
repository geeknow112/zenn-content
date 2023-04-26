---
title: "初心者エンジニアのためのAzureサーバーレスコンピューティング入門"
emoji: "🌐"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["Azure", "サーバーレス"]
published: true
---

こんにちは。今回は、Azureについて初心者エンジニア向けて、サーバーレスについて解説します。

# はじめに

近年、クラウドサービスの需要が増え、その中でもAzureは多くの企業や個人に利用されています。Azureには、サーバーレスコンピューティングという機能があり、コストの削減やスケーラビリティの向上などに貢献しています。サーバーレスコンピューティングとは、サーバーの管理や設定不要で、必要なときに必要な分だけコンピューティングリソースを利用できる仕組みです。この記事では、Azureのサーバーレスコンピューティングについて詳しく解説します。

# Azureのサーバーレスコンピューティング

Azureのサーバーレスコンピューティングには、Azure FunctionsとAzure Logic Appsがあります。

## Azure Functions

Azure Functionsは、イベント駆動型のコンピューティングサービスです。Function Appという単位で管理され、各Function Appには、Functionという単位でコードを記述します。イベントトリガーに応じて、Functionが実行され、コンピューティングリソースを使用して処理を行います。

Azure Functionsは、C#、Java、JavaScript、Python、PowerShellなど、複数のプログラミング言語に対応しています。また、前処理や後処理を行うことができるバインディングという機能があり、Azure Blob StorageやAzure Queue Storage、Cosmos DBなど、Azureのストレージサービスに簡単にアクセスできます。

以下は、C#で書かれたAzure Functionsのサンプルコードです。

```csharp
using System.Net;
public static async Task<IActionResult> Run(
    [HttpTrigger(AuthorizationLevel.Function, "get", "post", Route = null)] HttpRequest req,
    ILogger log)
{
    log.LogInformation("C# HTTP trigger function processed a request.");

    string name = req.Query["name"];

    string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
    dynamic data = JsonConvert.DeserializeObject(requestBody);
    name = name ?? data?.name;

    string responseMessage = string.IsNullOrEmpty(name)
        ? "This HTTP triggered function executed successfully. Pass a name in the query string or in the request body for a personalized response."
        : $"Hello, {name}. This HTTP triggered function executed successfully.";

    return new OkObjectResult(responseMessage);
}
```

## Azure Logic Apps

Azure Logic Appsは、ビジネスプロセスの自動化に特化したサーバーレスコンピューティングサービスです。Logic App DesignerというGUIツールを使用して、ビジネスプロセスの各ステップを定義し、トリガーに応じて処理を実行します。トリガーには、Recurrence、HTTP、Azure Blob Storageなどがあります。また、カスタムコネクタという機能を使用して、Azure以外のサービスとの連携も可能です。

以下は、Azure Logic Appsのサンプルデザインです。

![Azure Logic Appsのサンプルデザイン](https://docs.microsoft.com/ja-jp/azure/connectors/media/connectors-create-api-azure-functions/logic-apps-api-app-function.png)

# まとめ

この記事では、Azureのサーバーレスコンピューティングについて解説しました。Azure FunctionsとAzure Logic Appsは、それぞれ異なる特徴を持っていますが、どちらもサーバーレスコンピューティングの恩恵を受けることができる優れたサービスです。Azureを使っている方や、これから使おうと考えている方は、ぜひサーバーレスコンピューティングにも注目してみてください。
