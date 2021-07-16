---
ms.openlocfilehash: 25caea9275c57faa9c741e274ac90606959422c2
ms.sourcegitcommit: ef990e983274cb161bfe16a8dff801d30a798f04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53446985"
---
<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="d1b2d-101">このチュートリアルでは、Microsoft Graph API を使用してユーザーの予定表情報を取得するクライアント側の Blazor WebAssembly アプリを構築する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1b2d-101">This tutorial teaches you how to build a client-side Blazor WebAssembly app that uses the Microsoft Graph API to retrieve calendar information for a user.</span></span>

> [!TIP]
> <span data-ttu-id="d1b2d-102">完了したチュートリアルをダウンロードする場合は、リポジトリをダウンロードまたは複製GitHub[できます](https://github.com/microsoftgraph/msgraph-training-blazor-clientside)。</span><span class="sxs-lookup"><span data-stu-id="d1b2d-102">If you prefer to just download the completed tutorial, you can download or clone the [GitHub repository](https://github.com/microsoftgraph/msgraph-training-blazor-clientside).</span></span> <span data-ttu-id="d1b2d-103">アプリ ID とシークレットを使用してアプリを構成する手順については、デモ フォルダーの README ファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1b2d-103">See the README file in the **demo** folder for instructions on configuring the app with an app ID and secret.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d1b2d-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="d1b2d-104">Prerequisites</span></span>

<span data-ttu-id="d1b2d-105">このチュートリアルを開始する前に、開発マシンに [.NET Core SDK](https://dotnet.microsoft.com/download) がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1b2d-105">Before you start this tutorial, you should have the [.NET Core SDK](https://dotnet.microsoft.com/download) installed on your development machine.</span></span> <span data-ttu-id="d1b2d-106">SDK がない場合は、前のリンクにアクセスしてダウンロード オプションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d1b2d-106">If you do not have the SDK, visit the previous link for download options.</span></span>

<span data-ttu-id="d1b2d-107">また、Outlook.com 上のメールボックスを持つ個人用 Microsoft アカウント、または Microsoft の仕事用または学校用のアカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1b2d-107">You should also have either a personal Microsoft account with a mailbox on Outlook.com, or a Microsoft work or school account.</span></span> <span data-ttu-id="d1b2d-108">Microsoft アカウントをお持ちでない場合は、無料アカウントを取得するためのオプションが 2 つご利用できます。</span><span class="sxs-lookup"><span data-stu-id="d1b2d-108">If you don't have a Microsoft account, there are a couple of options to get a free account:</span></span>

- <span data-ttu-id="d1b2d-109">新しい [個人用 Microsoft アカウントにサインアップできます](https://signup.live.com/signup?wa=wsignin1.0&rpsnv=12&ct=1454618383&rver=6.4.6456.0&wp=MBI_SSL_SHARED&wreply=https://mail.live.com/default.aspx&id=64855&cbcxt=mai&bk=1454618383&uiflavor=web&uaid=b213a65b4fdc484382b6622b3ecaa547&mkt=E-US&lc=1033&lic=1)。</span><span class="sxs-lookup"><span data-stu-id="d1b2d-109">You can [sign up for a new personal Microsoft account](https://signup.live.com/signup?wa=wsignin1.0&rpsnv=12&ct=1454618383&rver=6.4.6456.0&wp=MBI_SSL_SHARED&wreply=https://mail.live.com/default.aspx&id=64855&cbcxt=mai&bk=1454618383&uiflavor=web&uaid=b213a65b4fdc484382b6622b3ecaa547&mkt=E-US&lc=1033&lic=1).</span></span>
- <span data-ttu-id="d1b2d-110">開発者プログラム[にサインアップしてOffice 365無料](https://developer.microsoft.com/office/dev-program)のサブスクリプションをOffice 365できます。</span><span class="sxs-lookup"><span data-stu-id="d1b2d-110">You can [sign up for the Office 365 Developer Program](https://developer.microsoft.com/office/dev-program) to get a free Office 365 subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="d1b2d-111">このチュートリアルは、.NET Core SDK バージョン 5.0.302 で記述されています。</span><span class="sxs-lookup"><span data-stu-id="d1b2d-111">This tutorial was written with .NET Core SDK version 5.0.302.</span></span> <span data-ttu-id="d1b2d-112">このガイドの手順は、他のバージョンでも動作しますが、テストされていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d1b2d-112">The steps in this guide may work with other versions, but that has not been tested.</span></span>

## <a name="feedback"></a><span data-ttu-id="d1b2d-113">フィードバック</span><span class="sxs-lookup"><span data-stu-id="d1b2d-113">Feedback</span></span>

<span data-ttu-id="d1b2d-114">このチュートリアルに関するフィードバックは、GitHub[してください](https://github.com/microsoftgraph/msgraph-training-blazor-clientside)。</span><span class="sxs-lookup"><span data-stu-id="d1b2d-114">Please provide any feedback on this tutorial in the [GitHub repository](https://github.com/microsoftgraph/msgraph-training-blazor-clientside).</span></span>
