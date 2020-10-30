---
title: '[エンタープライズ新規] タブページの下位互換性'
ms.author: ruchir
author: dan-wesley
manager: vwehren
ms.date: 10/28/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: '[エンタープライズ新規] タブページの下位互換性'
ms.openlocfilehash: c10671a6ec8e1ff4dcb0db3f3c085f82ae973122
ms.sourcegitcommit: af6ab070d0c09bca4a9cf505b107ed7e04839763
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "11144489"
---
# <span data-ttu-id="c9b26-103">[エンタープライズ新規] タブページの下位互換性</span><span class="sxs-lookup"><span data-stu-id="c9b26-103">Backwards compatibility for the Enterprise New tab page</span></span>

<span data-ttu-id="c9b26-104">この記事では、新しいタブページへの変更と、Microsoft Edge バージョン87以前のバージョンと下位互換性を持つために何をしたらよいのかを説明します。</span><span class="sxs-lookup"><span data-stu-id="c9b26-104">This article describes the change to the New tab page and how users can be backwards compatible with Microsoft Edge version 87 and earlier.</span></span>

> [!NOTE]
> <span data-ttu-id="c9b26-105">この記事は Microsoft Edge version 87 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c9b26-105">This article applies to Microsoft Edge version 87 or later.</span></span>

## <span data-ttu-id="c9b26-106">1つのエンドポイントからの情報フィード</span><span class="sxs-lookup"><span data-stu-id="c9b26-106">Information feeds from single endpoint</span></span>

<span data-ttu-id="c9b26-107">新しいバージョンのエンタープライズ向けの新しいタブページでは、対応型Microsoft 365 のコンテンツと、MSN.com エンドポイント経由で配信される業界の関連する対応型情報フィードを組み合わせます。</span><span class="sxs-lookup"><span data-stu-id="c9b26-107">The new version of the Enterprise New tab page combines compliant Microsoft 365 content with industry relevant and compliant information feeds that are served via the MSN.com endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="c9b26-108">Office 365 のコンテンツは、 [Office.com](https://www.office.com) ドメインを使用して提供されていました。</span><span class="sxs-lookup"><span data-stu-id="c9b26-108">Office 365 content was originally served using the [Office.com](https://www.office.com) domain.</span></span>

<span data-ttu-id="c9b26-109">組織の MSN.com ドメインへのアクセスが制限されている場合は、この [url](https://ntp.msn.com)へのアクセス権をユーザーに付与することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c9b26-109">If access to the MSN.com domain is restricted for your organization, we strongly recommend giving users access to this [url](https://ntp.msn.com).</span></span>

<span data-ttu-id="c9b26-110">MSN ドメインへのアクセスを有効にするために、さらに時間が必要な場合は、[NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)を使用して、新しいタブページにMicrosoft ニュースまたは Office 365 のフィードのいずれかを選択できるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c9b26-110">If you need more time to enable access to the MSN domain, we recommend using the [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype), that lets you choose either the Microsoft News or Office 365 feed experience for the new tab page.</span></span>

### <span data-ttu-id="c9b26-111">Office.com の使用を続ける</span><span class="sxs-lookup"><span data-stu-id="c9b26-111">Keep using Office.com</span></span>

 <span data-ttu-id="c9b26-112">**NewTabPageSetFeedType**ポリシーを構成して、非推奨のOffice.com ドメインを引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9b26-112">You can configure the **NewTabPageSetFeedType** policy to keep using the deprecated Office.com domain.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9b26-113">Microsoft Edge バージョン90がリリースされると、 **NewTabPageSetFeedType** ポリシーと、Office 365 のコンテンツに対応する Office.com ドメインは動作を停止します。</span><span class="sxs-lookup"><span data-stu-id="c9b26-113">The **NewTabPageSetFeedType** policy and the Office.com domain that serves Office 365 content will quit working when Microsoft Edge version 90 is released.</span></span>

<span data-ttu-id="c9b26-114">次のポリシー設定では、Enterpriseの新しいタブページで、Office.com ドメインからのOffice ドキュメントのコンテンツが 強制的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9b26-114">The following policy settings will force the Enterprise New tab page to render Office document content from the Office.com domain.</span></span>

- <span data-ttu-id="c9b26-115">ポリシーを**必須**として設定します。</span><span class="sxs-lookup"><span data-stu-id="c9b26-115">Set the policy as **Mandatory**.</span></span>
- <span data-ttu-id="c9b26-116">ポリシーマッピングの値を \*\*Office (1) = Office 365 フィードエクスペリエンス \*\*に設定します。</span><span class="sxs-lookup"><span data-stu-id="c9b26-116">Set the value of the policy mapping to **Office (1) = Office 365 feed experience**.</span></span>

<span data-ttu-id="c9b26-117">Office.com に切り替えることができない場合は、お問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="c9b26-117">If the switch to the Office.com isn't possible, reach out and send us feedback.</span></span> <span data-ttu-id="c9b26-118">もう1つのオプションは、組織で許可されているエンドポイント URL をポイントするように、 [NewTabPageLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagelocation)を構成することです。</span><span class="sxs-lookup"><span data-stu-id="c9b26-118">Another option is to configure the [NewTabPageLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagelocation) so it points to an endpoint URL that's allowed by your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="c9b26-119">**NewTabPageSetFeedType**ポリシーも構成されている場合は、**NewTabPageLocation** ポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="c9b26-119">The **NewTabPageLocation** policy has precedence if the **NewTabPageSetFeedType** policy is also configured.</span></span>

## <span data-ttu-id="c9b26-120">マイフィードを使用して、エンタープライズユーザーが Microsoft ニュースコンテンツを取得できるようになります</span><span class="sxs-lookup"><span data-stu-id="c9b26-120">Enterprise users will now get Microsoft news content via My Feed</span></span>

<span data-ttu-id="c9b26-121">[エンタープライズ新規] タブページでは、Azure Active Directory (Azure AD) アカウントでサインインしているユーザーのために、**マイフィード** と Office 365 のコンテンツ で一目で見られるように業界関連の情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="c9b26-121">The Enterprise New tab page will offer industry relevant information in **My Feed** and Office 365 content in a single view for users signed in with their Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="c9b26-122">Azure Active Directory (Azure AD) を使ってサインインしているユーザーで、[設定] ポップアップで [Microsoft ニュース] オプションを選択した場合は、新しいタブページビューが**マイフィード**の コンテンツに 置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="c9b26-122">For users signed in with their Azure Active Directory (Azure AD) who selected the Microsoft News option in the settings flyout, their new tab page view will be replaced with **My Feed** content.</span></span> <span data-ttu-id="c9b26-123">ブラウザーで新しいタブページを開くと、次のスクリーンショットの例のようになります。</span><span class="sxs-lookup"><span data-stu-id="c9b26-123">When they open a new tab page in the browser it will look like the example in the next screenshot.</span></span>

![[マイフィードのコンテンツを表示する新しいタブページ]。](media/microsoft-edge-ntp-backward-compatibility/microsoft-edge-ntp-myfeed-view.png)

> [!NOTE]
> <span data-ttu-id="c9b26-125">Azure AD でサインインしていないユーザーは、新しいタブを開いたときに引き続き MSN ニュースフィードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9b26-125">Users who aren't signed in with Azure AD will continue to see the MSN News feed when they open a new tab.</span></span>

## <span data-ttu-id="c9b26-126">ページのレイアウト</span><span class="sxs-lookup"><span data-stu-id="c9b26-126">Page layout</span></span>

<span data-ttu-id="c9b26-127">新しいタブページが変更されたため、ページレイアウトでは、2つの特定のコンテンツタイプ (Office 365 と Microsoft ニュース) を制御する必要がなくなりました。したがって、コンテンツの切り替えが使用できません。</span><span class="sxs-lookup"><span data-stu-id="c9b26-127">With the changes to the New tab page, the Page layout no longer has to control two specific content types (Office 365 and Microsoft News), so the content toggle isn't available.</span></span> <span data-ttu-id="c9b26-128">次のスクリーンショットは、ページレイアウトのポップアップを示しています。</span><span class="sxs-lookup"><span data-stu-id="c9b26-128">The next screenshot shows the flyout for the Page layout.</span></span>

![新しいタブページ用のページレイアウトビュー。](media/microsoft-edge-ntp-backward-compatibility/microsoft-edge-ntp-page-layout.png)

<span data-ttu-id="c9b26-130">組織に関連付けられていない Microsoft ニュースコンテンツに引き続きアクセスするには、別のブラウザープロファイルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b26-130">If you want to keep accessing Microsoft News content that isn't tied to your organization, you must use a different browser profile.</span></span> <span data-ttu-id="c9b26-131">*edge://settings/profiles* に移動して、Azure AD プロファイルからサインアウトします。</span><span class="sxs-lookup"><span data-stu-id="c9b26-131">Go to  *edge://settings/profiles* and sign out of your Azure AD profile.</span></span> <span data-ttu-id="c9b26-132">この操作を行うと、[Enterprise新規] タブページの標準ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9b26-132">This action will bring up the  standard view for the Enterprise new tab page.</span></span> 

## <span data-ttu-id="c9b26-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9b26-133">See also</span></span>

- [<span data-ttu-id="c9b26-134">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="c9b26-134">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="c9b26-135">Internet Explorer 11 のエンタープライズ モード</span><span class="sxs-lookup"><span data-stu-id="c9b26-135">Enterprise Mode for Internet Explorer 11</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
