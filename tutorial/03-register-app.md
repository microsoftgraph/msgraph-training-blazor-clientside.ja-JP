---
ms.openlocfilehash: c9fb7269969b0ef4e0300b8884c3ed168216b6cc
ms.sourcegitcommit: ef990e983274cb161bfe16a8dff801d30a798f04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53446967"
---
<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="4be09-101">この演習では、管理者センターを使用して新AD Azure Azure Active Directory作成します。</span><span class="sxs-lookup"><span data-stu-id="4be09-101">In this exercise, you will create a new Azure AD web application registration using the Azure Active Directory admin center.</span></span>

1. <span data-ttu-id="4be09-102">ブラウザーを開き、[Azure Active Directory 管理センター](https://aad.portal.azure.com)へ移動します。</span><span class="sxs-lookup"><span data-stu-id="4be09-102">Open a browser and navigate to the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="4be09-103">**個人用アカウント** (別名: Microsoft アカウント)、または **職場/学校アカウント** を使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="4be09-103">Login using a **personal account** (aka: Microsoft Account) or **Work or School Account**.</span></span>

1. <span data-ttu-id="4be09-104">左側のナビゲーションで **[Azure Active Directory]** を選択し、それから **[管理]** で **[アプリの登録]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4be09-104">Select **Azure Active Directory** in the left-hand navigation, then select **App registrations** under **Manage**.</span></span>

    ![<span data-ttu-id="4be09-105">アプリの登録のスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="4be09-105">A screenshot of the App registrations</span></span> ](./images/aad-portal-app-registrations.png)

1. <span data-ttu-id="4be09-106">**[新規登録]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4be09-106">Select **New registration**.</span></span> <span data-ttu-id="4be09-107">**[アプリケーションを登録]** ページで、次のように値を設定します。</span><span class="sxs-lookup"><span data-stu-id="4be09-107">On the **Register an application** page, set the values as follows.</span></span>

    - <span data-ttu-id="4be09-108">`Blazor Graph Tutorial` に **[名前]** を設定します。</span><span class="sxs-lookup"><span data-stu-id="4be09-108">Set **Name** to `Blazor Graph Tutorial`.</span></span>
    - <span data-ttu-id="4be09-109">**[サポートされているアカウントの種類]** を **[任意の組織のディレクトリ内のアカウントと個人用の Microsoft アカウント]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="4be09-109">Set **Supported account types** to **Accounts in any organizational directory and personal Microsoft accounts**.</span></span>
    - <span data-ttu-id="4be09-110">[ **リダイレクト URI] で**、最初のドロップダウンを [単一ページ アプリケーション **(SPA)** に設定し、値をに設定します `https://localhost:5001/authentication/login-callback` 。</span><span class="sxs-lookup"><span data-stu-id="4be09-110">Under **Redirect URI**, set the first drop-down to **Single-page application (SPA)** and set the value to `https://localhost:5001/authentication/login-callback`.</span></span>

    ![[アプリケーションを登録する] ページのスクリーンショット](./images/aad-register-an-app.png)

1. <span data-ttu-id="4be09-112">**[登録]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4be09-112">Select **Register**.</span></span> <span data-ttu-id="4be09-113">**[Blazor Graphチュートリアル**] ページで、**アプリケーション (クライアント) ID** の値をコピーして保存します。次の手順で必要になります。</span><span class="sxs-lookup"><span data-stu-id="4be09-113">On the **Blazor Graph Tutorial** page, copy the value of the **Application (client) ID** and save it, you will need it in the next step.</span></span>

    ![新しいアプリ登録のアプリケーション ID のスクリーンショット](./images/aad-application-id.png)
