---
title: Microsoft Edge と混在したコンテンツのダウンロード
ms.author: kele
author: dan-wesley
manager: srugh
ms.date: 04/30/2020
audience: ITPro
ms.topic: procedural
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge と混在したコンテンツのダウンロード
ms.openlocfilehash: 57da17a8684b97aad88e7837ff9d070f6862357b
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980441"
---
# <span data-ttu-id="b0dff-103">Microsoft Edge と混在したコンテンツのダウンロードについて説明します</span><span class="sxs-lookup"><span data-stu-id="b0dff-103">Learn about Microsoft Edge and mixed content downloads</span></span>

<span data-ttu-id="b0dff-104">この記事では、混在したコンテンツのダウンロードと Microsoft Edge によるその処理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0dff-104">This article explains mixed content downloads and how Microsoft Edge handles them.</span></span>

>[!NOTE]
><span data-ttu-id="b0dff-105">この記事は Microsoft Edge version 85 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b0dff-105">This article applies to Microsoft Edge version 85 or later.</span></span>

## <span data-ttu-id="b0dff-106">混在したコンテンツのダウンロードとは?</span><span class="sxs-lookup"><span data-stu-id="b0dff-106">What are mixed content downloads?</span></span>

<span data-ttu-id="b0dff-107">セキュリティで保護された HTTPS 接続経由で読み込まれた HTML ページからダウンロードを開始するときに、以下のいずれかの条件が存在すると、混在したコンテンツのダウンロードになります。</span><span class="sxs-lookup"><span data-stu-id="b0dff-107">A mixed content download happens when you start a download from an HTML page that was loaded over a secure HTTPS connection, but one of the following conditions exists:</span></span>

- <span data-ttu-id="b0dff-108">1 つ以上のダウンロード場所のリダイレクトが、セキュリティで保護されていない HTTP 接続経由で読み込まれた。</span><span class="sxs-lookup"><span data-stu-id="b0dff-108">One or more of the download location's redirects was loaded over an insecure HTTP connection.</span></span>
- <span data-ttu-id="b0dff-109">最終的なダウンロード場所がセキュリティで保護されていない HTTP 接続経由で読み込まれた。</span><span class="sxs-lookup"><span data-stu-id="b0dff-109">The final download location was loaded over an insecure HTTP connection.</span></span>

<span data-ttu-id="b0dff-110">いずれの場合も、要求はセキュリティで保護された HTTPS を使用して行われましたが、最終的なダウンロード先に到達するまでに HTTP と HTTPS の両方が関係しているため、混在したコンテンツとなります。</span><span class="sxs-lookup"><span data-stu-id="b0dff-110">Either scenario is a mixed content because the request was made using secure HTTPS and both HTTP and HTTPS content are involved in reaching the final download destination.</span></span> <span data-ttu-id="b0dff-111">この種のコンテンツの場合、最新のブラウザーには、アクセス元のページはセキュリティで保護されていてもこのダウンロードがセキュリティで保護されていない状態で転送される可能性があることを示す警告がユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0dff-111">Modern browsers display warnings about this type of content to indicate to the user that this download may be transferred insecurely even though the original page accessed was secure.</span></span>

## <span data-ttu-id="b0dff-112">ダウンロードの警告とユーザー オプション</span><span class="sxs-lookup"><span data-stu-id="b0dff-112">Download warnings and user options</span></span>

<span data-ttu-id="b0dff-113">ダウンロードの警告によって、ダウンロードしているファイルがネットワーク上で悪意のある攻撃者に読み取られる可能性があることをユーザーは確認できます。</span><span class="sxs-lookup"><span data-stu-id="b0dff-113">The download warning ensures that users know that the file they're downloading could be read by malicious attackers on their network.</span></span> <span data-ttu-id="b0dff-114">このように警告されることにより、ユーザーは十分な情報を得たうえでファイルをダウンロードするかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="b0dff-114">This warning lets a user make an informed decision on whether to download the file.</span></span>

<span data-ttu-id="b0dff-115">Microsoft Edge では、混在したコンテンツのダウンロードはブロックされますが、ユーザーは必要に応じてこの設定をオーバーライドして、ファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="b0dff-115">In Microsoft Edge, mixed content downloads will be blocked but users can override and download the file if they want to.</span></span> <span data-ttu-id="b0dff-116">Microsoft Edge での混在したコンテンツの実行可能ファイルのダウンロードのブロックは Microsoft Edge バージョン 85 から開始される予定で、今後のリリースでは各種ファイルがブロックされることになります。</span><span class="sxs-lookup"><span data-stu-id="b0dff-116">Microsoft Edge plans on starting to block mixed content executable file downloads starting with Microsoft Edge version 85 and will block different filetypes in future releases.</span></span>

> [!NOTE]
> <span data-ttu-id="b0dff-117">この機能の展開は、リリース スケジュールとユーザー フィードバックに基づいて変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="b0dff-117">Deployment of this feature is subject to change based on release schedule and user feedback.</span></span>

<!-- The schedule of the block for different filetypes is to be determined and may be impacted by usage data and user feedback. -->

<span data-ttu-id="b0dff-118">ダウンロード シェルフの場合、次のスクリーンショットの例のように、ブロックの警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0dff-118">In the download shelf, the block warning message looks like the example in the next screenshot.</span></span>

 ![ダウンロード トレイの混在したコンテンツの警告](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-tray-warning.png)

<span data-ttu-id="b0dff-120">[ダウンロード] ページでは、次のスクリーンショットのようなブロックに関する警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0dff-120">On the download page, the block warning looks like the following screenshot example:</span></span>

 ![混在したコンテンツのオーバーライドに関するプロンプト](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-page-warning.png)

<span data-ttu-id="b0dff-122">ユーザーがダウンロードの続行を選択すると、そのアクションを確認するためのプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0dff-122">If a user decides to keep the download, they are prompted to confirm their action.</span></span> <span data-ttu-id="b0dff-123">この確認メッセージの例が次のスクリーンショットに示されています。</span><span class="sxs-lookup"><span data-stu-id="b0dff-123">The next screenshot shows an example of this confirmation prompt.</span></span>

 ![Internet Explorer モードを選択する](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-override.png)

## <span data-ttu-id="b0dff-125">サポート ポリシー</span><span class="sxs-lookup"><span data-stu-id="b0dff-125">Supporting policies</span></span>

<span data-ttu-id="b0dff-126">企業が特定の Web サイトから混在したコンテンツのブロックを除外する場合、[InsecureContentAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#insecurecontentallowedforurls) ポリシーを使用して行えます。</span><span class="sxs-lookup"><span data-stu-id="b0dff-126">Enterprises that want to exclude mixed content blocking from specific websites can use the [InsecureContentAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#insecurecontentallowedforurls) policy to do so.</span></span>

## <span data-ttu-id="b0dff-127">コンテンツ ライセンス</span><span class="sxs-lookup"><span data-stu-id="b0dff-127">Content license</span></span>

> [!NOTE]
> <span data-ttu-id="b0dff-128">このページの一部の情報は、Chromium.org によって作成および共有されている著作物に基づいており、[Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/) に記載されている条項に従って使用されています。</span><span class="sxs-lookup"><span data-stu-id="b0dff-128">Portions of this page are modifications based on work created and shared by Chromium.org and used according to terms described in the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).</span></span> <span data-ttu-id="b0dff-129">元のページは[こちら](https://developers.google.com/web/fundamentals/security/prevent-mixed-content/what-is-mixed-content)です。</span><span class="sxs-lookup"><span data-stu-id="b0dff-129">The original page can be found [here](https://developers.google.com/web/fundamentals/security/prevent-mixed-content/what-is-mixed-content).</span></span>
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span data-ttu-id="b0dff-130">この著作物は、<a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a> に従って使用許諾されています。</span><span class="sxs-lookup"><span data-stu-id="b0dff-130">This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.</span></span>

## <span data-ttu-id="b0dff-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0dff-131">See also</span></span>

- [<span data-ttu-id="b0dff-132">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="b0dff-132">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
