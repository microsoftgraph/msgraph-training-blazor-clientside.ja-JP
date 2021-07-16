---
ms.openlocfilehash: 4c021fe8aac9b42ee0984a15e73366ead847ee06
ms.sourcegitcommit: ef990e983274cb161bfe16a8dff801d30a798f04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53446978"
---
<!-- markdownlint-disable MD002 MD041 -->

まず、Blazor WebAssembly アプリを作成します。

1. プロジェクトを作成するディレクトリでコマンド ライン インターフェイス (CLI) を開きます。 次のコマンドを実行します。

    ```Shell
    dotnet new blazorwasm --auth SingleOrg -o GraphTutorial
    ```

    この `--auth SingleOrg` パラメーターを使用すると、生成されたプロジェクトに、認証用の構成が含Microsoft ID プラットフォーム。

1. プロジェクトが作成されると、現在のディレクトリを **GraphTutorial** ディレクトリに変更し、CLI で次のコマンドを実行して動作します。

    ```Shell
    dotnet watch run
    ```

1. ブラウザーを開き、を参照します `https://localhost:5001` 。 すべてが機能している場合は、"Hello, world! メッセージ。

> [!IMPORTANT]
> **localhost** の証明書が信頼されていないという警告を受け取った場合は、.NET Core CLI を使用して開発証明書をインストールして信頼できます。 特定[のオペレーティング システムの手順については、「ASP.NET Core](/aspnet/core/security/enforcing-ssl)で HTTPS を適用する」を参照してください。

## <a name="add-nuget-packages"></a>NuGet パッケージを追加する

次に進む前に、後で使用NuGet追加のパッケージをインストールします。

- [Microsoft.Graph](https://www.nuget.org/packages/Microsoft.Graph/): Microsoft Graph を呼び出すためのものです。
- タイム ゾーン識別子を IANA 識別子Windows変換する[TimeZoneConverter。](https://github.com/mj1856/TimeZoneConverter)

1. 依存関係をインストールするには、CLI で次のコマンドを実行します。

    ```Shell
    dotnet add package Microsoft.Graph --version 4.0.0
    dotnet add package TimeZoneConverter
    ```

## <a name="design-the-app"></a>アプリを設計する

このセクションでは、アプリケーションの基本的な UI 構造を作成します。

1. テンプレートによって生成されたサンプル ページを削除します。 次のファイルを削除します。

    - **./Pages/Counter.razor**
    - **./Pages/FetchData.razor**
    - **./Shared/SurveyPrompt.razor**
    - **./wwwroot/sample-data/weather.json**

1. **./wwwroot/index.html を開** き、終了タグの直前に次 **のコード** を追加 `</body>` します。

    :::code language="html" source="../demo/GraphTutorial/wwwroot/index.html" id="BootStrapJSSnippet":::

    これにより、 [ブートストラップ javascript](https://getbootstrap.com/docs/4.5/getting-started/introduction/) ファイルが追加されます。

1. **./wwwroot/css/app.css を開** き、次のコードを追加します。

    :::code language="css" source="../demo/GraphTutorial/wwwroot/css/app.css" id="CssSnippet":::

1. **./Shared/NavMenu.razor** を開き、その内容を次に置き換えます。

    :::code language="razor" source="../demo/GraphTutorial/Shared/NavMenu.razor" id="NavMenuSnippet":::

1. **./Pages/Index.razor を開き**、その内容を次に置き換えます。

    :::code language="razor" source="../demo/GraphTutorial/Pages/Index.razor" id="IndexSnippet":::

1. **./Shared/LoginDisplay.razor を開き、** その内容を次に置き換えます。

    ```razor
    @using Microsoft.AspNetCore.Components.Authorization
    @using Microsoft.AspNetCore.Components.WebAssembly.Authentication

    @inject NavigationManager Navigation
    @inject SignOutSessionStateManager SignOutManager

    <AuthorizeView>
        <Authorized>
            <a class="text-decoration-none" data-toggle="dropdown" href="#" role="button">
                <img src="/img/no-profile-photo.png" class="nav-profile-photo rounded-circle align-self-center mr-2">
            </a>
            <div class="dropdown-menu dropdown-menu-right">
                <h5 class="dropdown-item-text mb-0">@context.User.Identity.Name</h5>
                <p class="dropdown-item-text text-muted mb-0">placeholder@contoso.com</p>
                <div class="dropdown-divider"></div>
                <button class="dropdown-item" @onclick="BeginLogout">Log out</button>
            </div>
        </Authorized>
        <NotAuthorized>
            <a href="authentication/login">Log in</a>
        </NotAuthorized>
    </AuthorizeView>

    @code{
        private async Task BeginLogout(MouseEventArgs args)
        {
            await SignOutManager.SetSignOutState();
            Navigation.NavigateTo("authentication/logout");
        }
    }
    ```

1. img という名前の **./wwwroot ディレクトリに新しい** ディレクトリを **作成します**。 このディレクトリに、選択した名前 **のno-profile-photo.pngを** 追加します。 この画像は、ユーザーが Microsoft サーバーで写真を持ってない場合に、ユーザーの写真Graph。

    > [!TIP]
    > これらのスクリーンショットで使用されている画像は、次のページから[GitHub。](https://github.com/microsoftgraph/msgraph-training-blazor-clientside/blob/master/demo/GraphTutorial/wwwroot/img/no-profile-photo.png)

1. すべての変更を保存し、ページを更新します。

    ![デザインが変更されたホーム ページのスクリーンショット](./images/create-app-01.png)
