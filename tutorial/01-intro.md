---
ms.openlocfilehash: 25caea9275c57faa9c741e274ac90606959422c2
ms.sourcegitcommit: ef990e983274cb161bfe16a8dff801d30a798f04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53446985"
---
<!-- markdownlint-disable MD002 MD041 -->

このチュートリアルでは、Microsoft Graph API を使用してユーザーの予定表情報を取得するクライアント側の Blazor WebAssembly アプリを構築する方法について説明します。

> [!TIP]
> 完了したチュートリアルをダウンロードする場合は、リポジトリをダウンロードまたは複製GitHub[できます](https://github.com/microsoftgraph/msgraph-training-blazor-clientside)。 アプリ ID とシークレットを使用してアプリを構成する手順については、デモ フォルダーの README ファイルを参照してください。

## <a name="prerequisites"></a>前提条件

このチュートリアルを開始する前に、開発マシンに [.NET Core SDK](https://dotnet.microsoft.com/download) がインストールされている必要があります。 SDK がない場合は、前のリンクにアクセスしてダウンロード オプションを確認してください。

また、Outlook.com 上のメールボックスを持つ個人用 Microsoft アカウント、または Microsoft の仕事用または学校用のアカウントを持っている必要があります。 Microsoft アカウントをお持ちでない場合は、無料アカウントを取得するためのオプションが 2 つご利用できます。

- 新しい [個人用 Microsoft アカウントにサインアップできます](https://signup.live.com/signup?wa=wsignin1.0&rpsnv=12&ct=1454618383&rver=6.4.6456.0&wp=MBI_SSL_SHARED&wreply=https://mail.live.com/default.aspx&id=64855&cbcxt=mai&bk=1454618383&uiflavor=web&uaid=b213a65b4fdc484382b6622b3ecaa547&mkt=E-US&lc=1033&lic=1)。
- 開発者プログラム[にサインアップしてOffice 365無料](https://developer.microsoft.com/office/dev-program)のサブスクリプションをOffice 365できます。

> [!NOTE]
> このチュートリアルは、.NET Core SDK バージョン 5.0.302 で記述されています。 このガイドの手順は、他のバージョンでも動作しますが、テストされていない場合があります。

## <a name="feedback"></a>フィードバック

このチュートリアルに関するフィードバックは、GitHub[してください](https://github.com/microsoftgraph/msgraph-training-blazor-clientside)。
