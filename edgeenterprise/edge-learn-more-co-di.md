---
title: Microsoft Edge で ClickOnce と DirectInvoke を使用する
ms.author: kele
author: dan-wesley
manager: srugh
ms.date: 09/10/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge での ClickOnce と DirectInvoke の使用について説明します。
ms.openlocfilehash: 1d4e08c0ce3ee2afec7968cd892f77ef7bdc3fff
ms.sourcegitcommit: 4c0b84b03e686a7a2989ce2187dbadf35418104a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012797"
---
# <span data-ttu-id="8e690-103">Microsoft Edge での ClickOnce と DirectInvoke の機能について</span><span class="sxs-lookup"><span data-stu-id="8e690-103">Understand the ClickOnce and DirectInvoke features in Microsoft Edge</span></span>

<span data-ttu-id="8e690-104">ClickOnce と DirectInvoke は、IE および Microsoft Edge (version 45 以前) で利用可能な機能で、Web サイトからファイルをダウンロードするためのファイル ハンドラーの使用をサポートします。</span><span class="sxs-lookup"><span data-stu-id="8e690-104">ClickOnce and DirectInvoke are features available in IE and Microsoft Edge (version 45 and earlier) that support the use of a file handler to download files from a website.</span></span> <span data-ttu-id="8e690-105">この 2 つの機能は異なる目的で使用されますが、どちらの場合も Web サイトでは、ダウンロードが要求されたファイルをユーザー デバイス上のファイル ハンドラーに渡すことを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8e690-105">Although they serve different purposes, both features let websites specify that a file requested for download is passed to a file handler on the user's device.</span></span> <span data-ttu-id="8e690-106">ClickOnce 要求は、Windows のネイティブ ファイル ハンドラーによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="8e690-106">ClickOnce requests are handled by the native file handler in Windows.</span></span> <span data-ttu-id="8e690-107">DirectInvoke 要求は、ファイルをホストしている Web サイトで指定された登録済みのファイル ハンドラーによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="8e690-107">DirectInvoke requests are handled by a registered file handler specified by the website hosting the file.</span></span>

<span data-ttu-id="8e690-108">これらの機能について詳しくは、以下をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8e690-108">For more information about these features, see:</span></span>

- [<span data-ttu-id="8e690-109">ClickOnce</span><span class="sxs-lookup"><span data-stu-id="8e690-109">ClickOnce</span></span>](https://docs.microsoft.com/visualstudio/deployment/clickonce-security-and-deployment?view=vs-2019)
- [<span data-ttu-id="8e690-110">DirectInvoke</span><span class="sxs-lookup"><span data-stu-id="8e690-110">DirectInvoke</span></span>]( https://technet.microsoft.com/learning/jj215788(v=vs.94).aspx)

> [!NOTE]
> <span data-ttu-id="8e690-111">現時点では、ClickOnce または DirectInvoke のネイティブ サポートが Chromium では提供されていません。</span><span class="sxs-lookup"><span data-stu-id="8e690-111">Currently, Chromium doesn't provide native support for ClickOnce or DirectInvoke.</span></span>

## <span data-ttu-id="8e690-112">概要: 前提条件とプロセス</span><span class="sxs-lookup"><span data-stu-id="8e690-112">Overview: prerequisites and process</span></span>

<span data-ttu-id="8e690-113">ClickOnce および DirectInvoke が設計どおりに動作し、ファイル ハンドラーへの要求が正しく行われるためには、ClickOnce または DirectInvoke をサポートするように、ファイル ハンドラーをオペレーティング システムに登録しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e690-113">For ClickOnce and DirectInvoke to work as designed and for the file handler to be successfully requested, the file handler must be registered to the operating system as supporting ClickOnce or DirectInvoke.</span></span> <span data-ttu-id="8e690-114">この登録は通常、元のオペレーティング システムのインストール時か、インストールされた新しいプログラムが更新のために DirectInvoke を使用できるように要求した場合に行われます。</span><span class="sxs-lookup"><span data-stu-id="8e690-114">This registration typically happens when the original operating system is installed or when a new program that's installed requests the ability to use DirectInvoke for updates.</span></span>

<span data-ttu-id="8e690-115">ClickOnce または DirectInvoke を必要とするダウンロード要求を Web サイトが受け取ると、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="8e690-115">When a website receives a download request that requires ClickOnce or DirectInvoke, the following actions happen:</span></span>

- <span data-ttu-id="8e690-116">Web サイトは、指定されたファイル ハンドラーを使用するようにブラウザーに要求します。</span><span class="sxs-lookup"><span data-stu-id="8e690-116">The website requests that the browser use a specified file handler.</span></span>
- <span data-ttu-id="8e690-117">ブラウザーは、オペレーティング システムのレジストリをチェックして、要求されたファイルの種類に対してファイル ハンドラーが登録されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8e690-117">The browser checks the operating system registry to see if the file handler is registered for the requested file type.</span></span>
- <span data-ttu-id="8e690-118">ファイル ハンドラーが登録されている場合、ブラウザーはファイル ハンドラーを呼び出し、引数として URL をファイル ハンドラーに渡します。</span><span class="sxs-lookup"><span data-stu-id="8e690-118">If the file handler is registered, the browser calls the file handler and passes the URL as an argument to the file handler.</span></span>
- <span data-ttu-id="8e690-119">ファイル ハンドラーによって URL が処理され、ファイルがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="8e690-119">The file handler processes the URL and downloads the file.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8e690-120">URL は、ファイルのソースと、ファイルへのアクセス時に使用するパラメーターを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8e690-120">The URL is used to determine the source of the file, as well as any parameters to use when accessing the file.</span></span>  <span data-ttu-id="8e690-121">パラメーターには、エンドポイント、マニフェスト、メタデータなどがあります。</span><span class="sxs-lookup"><span data-stu-id="8e690-121">For example: endpoints, a manifest, or metadata.</span></span>

## <span data-ttu-id="8e690-122">使用例</span><span class="sxs-lookup"><span data-stu-id="8e690-122">Use cases</span></span>

<span data-ttu-id="8e690-123">次に、代表的な使用例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e690-123">The following use cases are representative.</span></span>

<span data-ttu-id="8e690-124">ClickOnce を使用すると、最小限のユーザー操作で、デバイス上のソフトウェアを簡単に展開し、更新できます。</span><span class="sxs-lookup"><span data-stu-id="8e690-124">You can use ClickOnce to easily deploy and update software on devices with minimal user interaction.</span></span> <span data-ttu-id="8e690-125">ユーザーは、Web ページ内のリンクをクリックして、Windows アプリケーションをインストールして実行できます。</span><span class="sxs-lookup"><span data-stu-id="8e690-125">Users can install and run a Windows application by clicking a link in a web page.</span></span> <span data-ttu-id="8e690-126">正しく構成されていれば、ClickOnce アプリケーションは、ユーザーがインストーラー用に構成を設定しなくてもプログラムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="8e690-126">If configured correctly, the ClickOnce application can install programs without having users set configurations for the installer.</span></span> <span data-ttu-id="8e690-127">たとえば、ファイルの場所、インストールするオプションなどです。</span><span class="sxs-lookup"><span data-stu-id="8e690-127">For example, file locations, what options to install, and so on.</span></span>

<span data-ttu-id="8e690-128">DirectInvoke の使用方法は、DirectInvoke を要求している Web サイトの目的によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8e690-128">DirectInvoke use cases depend on the intent of the website requesting DirectInvoke.</span></span> <span data-ttu-id="8e690-129">例として、Microsoft Word での共同作業によるファイル編集機能があります。</span><span class="sxs-lookup"><span data-stu-id="8e690-129">For example, the collaborative file-editing feature of Microsoft Word.</span></span> <span data-ttu-id="8e690-130">リンクをクリックして同僚と一緒に作業中のドキュメントのコピー全体をダウンロードする代わりに、DirectInvoke を使用すると、ドキュメントのうち、変更された部分だけをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="8e690-130">Instead of clicking a link and downloading the entire copy of a document you're working on with your colleagues, DirectInvoke lets you download the parts of the document that have been changed.</span></span> <span data-ttu-id="8e690-131">これにより、転送されるデータの量が減り、ドキュメントを開くために必要な時間を短縮できます。</span><span class="sxs-lookup"><span data-stu-id="8e690-131">This strategy reduces the amount of data transferred and can reduce the time needed to open the document.</span></span>  

## <span data-ttu-id="8e690-132">Microsoft Edge での ClickOnce と DirectInvoke のサポート状況</span><span class="sxs-lookup"><span data-stu-id="8e690-132">Current support for ClickOnce and DirectInvoke in Microsoft Edge</span></span>

<span data-ttu-id="8e690-133">ClickOnce と DirectInvoke のサポート状況は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8e690-133">Support for ClickOnce and DirectInvoke:</span></span>

- <span data-ttu-id="8e690-134">ClickOnce と DirectInvoke は、すべての Windows ユーザーが標準でサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8e690-134">ClickOnce and DirectInvoke are supported out of the box for all Windows users.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8e690-135">ClickOnce のサポートを無効にするユーザーは、*edge://flags/#edge-click-once* に移動し、ドロップダウン リストから **[無効にする]** を選択してください。</span><span class="sxs-lookup"><span data-stu-id="8e690-135">Users that want to disable ClickOnce support can go to *edge://flags/#edge-click-once* and select **Disabled** from the dropdown list.</span></span> <span data-ttu-id="8e690-136">ブラウザーを**再起動**する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e690-136">You'll have to **Restart** the browser.</span></span>

- <span data-ttu-id="8e690-137">ClickOnce と DirectInvoke は、Windows 以外のプラットフォームではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8e690-137">ClickOnce and DirectInvoke aren't supported on any platforms other than Windows.</span></span>

## <span data-ttu-id="8e690-138">ClickOnce と DirectInvoke のファイル処理のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="8e690-138">ClickOnce and DirectInvoke file handling security</span></span>

<span data-ttu-id="8e690-139">ClickOnce と DirectInvoke は、Microsoft Defender SmartScreen の URL レピュテーション スキャン サービスによって保護されます。</span><span class="sxs-lookup"><span data-stu-id="8e690-139">ClickOnce and DirectInvoke are protected by Microsoft Defender SmartScreen's URL reputation scanning service.</span></span>

<span data-ttu-id="8e690-140">Microsoft Defender SmartScreen URL レピュテーション サービスによって ClickOnce 要求または DirectInvoke 要求が安全でないとフラグ付けされた場合、ClickOnce または DirectInvoke を有効にしているユーザーに対して、2 つのポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e690-140">If a ClickOnce or a DirectInvoke request is flagged by the Microsoft Defender SmartScreen URL reputation service as unsafe, users with ClickOnce or DirectInvoke enabled will see two popups.</span></span>

<span data-ttu-id="8e690-141">最初のポップアップは、ファイルを開くかどうかをユーザーに尋ねます。</span><span class="sxs-lookup"><span data-stu-id="8e690-141">The first popup asks the user if they want to open the file.</span></span> <span data-ttu-id="8e690-142">このポップアップは、ファイルに安全であるとフラグ付けされた場合も安全でないとフラグ付けされた場合も、表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e690-142">This popup is displayed regardless of whether the file was flagged as safe or unsafe.</span></span> <span data-ttu-id="8e690-143">ユーザーは、**[このファイルは安全ではないことを報告する]** か、要求を **[キャンセル]** することもできます。続行するには、**[開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e690-143">The user can **Report the file as unsafe**, **Cancel** the request, or click **Open** to continue.</span></span>

   ![ファイルを開くかどうかを尋ねるメッセージ](./media/edge-learn-more-co-di/edge-clickonce-modal-1.png)

<span data-ttu-id="8e690-145">ユーザーがファイルを開こうとしたときに、安全でないというフラグがファイルに設定されている場合は、2 つ目のポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e690-145">If the user tries to open the file, and the file was flagged as unsafe, a second popup is displayed.</span></span>  <span data-ttu-id="8e690-146">このポップアップは、ファイルが安全でないとフラグ付けされていることをユーザーに警告し、それでもファイルをダウンロードするかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8e690-146">This popup warns the user that the file was flagged as unsafe, and asks them if they're sure they want to download the file.</span></span>

<span data-ttu-id="8e690-147">2 番目のポップアップは、次の場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e690-147">The second popup only shows up if:</span></span>

- <span data-ttu-id="8e690-148">ファイルが ClickOnce ファイルまたは DirectInvoke ファイルである</span><span class="sxs-lookup"><span data-stu-id="8e690-148">the file is a ClickOnce or DirectInvoke file</span></span>
- <span data-ttu-id="8e690-149">ClickOnce または DirectInvoke が有効になっている</span><span class="sxs-lookup"><span data-stu-id="8e690-149">ClickOnce or DirectInvoke are enabled</span></span>
- <span data-ttu-id="8e690-150">ファイルが安全でないとフラグ付けされている</span><span class="sxs-lookup"><span data-stu-id="8e690-150">the file is flagged as unsafe</span></span>

 ![安全でないファイルを開くかどうかを尋ねるメッセージ](./media/edge-learn-more-co-di/edge-clickonce-modal-2.png)

> [!NOTE]
> <span data-ttu-id="8e690-152">ClickOnce または DirectInvoke が無効になっている場合、要求されたファイルは通常のダウンロードとして扱われ、安全でないとフラグ付されている場合は、安全ではないとマークされます。</span><span class="sxs-lookup"><span data-stu-id="8e690-152">If ClickOnce or DirectInvoke are disabled, requested files are treated as regular downloads and if flagged as unsafe, will be marked as unsafe.</span></span> <span data-ttu-id="8e690-153">これは、安全でない他のダウンロードの処理と一致しています。</span><span class="sxs-lookup"><span data-stu-id="8e690-153">This is consistent with the treatment of other unsafe downloads.</span></span>

## <span data-ttu-id="8e690-154">ClickOnce と DirectInvoke のポリシー</span><span class="sxs-lookup"><span data-stu-id="8e690-154">ClickOnce and DirectInvoke policies</span></span>

<span data-ttu-id="8e690-155">エンタープライズ ユーザー用に ClickOnce と DirectInvoke を有効または無効にするには、2 つのグループ ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8e690-155">There are two group policies that you can use to enable or disable ClickOnce and DirectInvoke for enterprise users.</span></span> <span data-ttu-id="8e690-156">[ClickOnceEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#clickonceenabled) と [DirectInvokeEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#directinvokeenabled) です。</span><span class="sxs-lookup"><span data-stu-id="8e690-156">These two policies are [ClickOnceEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#clickonceenabled) and [DirectInvokeEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#directinvokeenabled).</span></span> <span data-ttu-id="8e690-157">これら 2 つのポリシーには、グループ ポリシー エディターで、"ユーザーが ClickOnce プロトコルを使用してファイルを開けるようにする" と "ユーザーが DirectInvoke プロトコルを使用してファイルを開けるようにする" というラベルがそれぞれ付けられています。</span><span class="sxs-lookup"><span data-stu-id="8e690-157">These two policies are labeled in the Group Policy Editor as "Allow users to open files using the ClickOnce protocol" and "Allow users to open files using the DirectInvoke protocol" respectively.</span></span>

## <span data-ttu-id="8e690-158">ClickOnce と DirectInvoke の動作</span><span class="sxs-lookup"><span data-stu-id="8e690-158">ClickOnce and DirectInvoke behavior</span></span>

<span data-ttu-id="8e690-159">次の例は、ClickOnce と DirectInvoke が有効または無効になっているときのファイル処理を示しています。</span><span class="sxs-lookup"><span data-stu-id="8e690-159">The following examples show file handling when ClickOnce and DirectInvoke are enabled or disabled.</span></span>

### <span data-ttu-id="8e690-160">ClickOnce が有効になっている場合</span><span class="sxs-lookup"><span data-stu-id="8e690-160">ClickOnce enabled</span></span>

1. <span data-ttu-id="8e690-161">ユーザーが ClickOnce のサポートを要求するページへのリンクを開くと、次のスクリーンショットに示されているメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e690-161">A user opens a link to a page that requests ClickOnce support and gets the prompt in the next screenshot.</span></span>

   ![安全でないファイルを開くかどうかを尋ねるメッセージ](./media/edge-learn-more-co-di/edge-clickonce-enabled-1.png)

2. <span data-ttu-id="8e690-163">ユーザーが **[開く]** をクリックすると、ClickOnce はアプリケーションの起動を試行します。</span><span class="sxs-lookup"><span data-stu-id="8e690-163">After the user clicks **Open**, ClickOnce attempts to launch the application.</span></span>

   ![ClickOnce がアプリケーションの起動を試行する](./media/edge-learn-more-co-di/edge-clickonce-enabled-launch-app.png)

3. <span data-ttu-id="8e690-165">ユーザーが **[開く]** をクリックすると、ブラウザーには、アプリケーションをインストールするかどうかをユーザーに尋ねるポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e690-165">After the user clicks **Open**, the browser shows a popup that asks the user if they're sure they want to install the application.</span></span>

   ![ファイルを開くかどうかを尋ねるメッセージ](./media/edge-learn-more-co-di/edge-clickonce-enabled-2.png)

   > [!NOTE]
   > <span data-ttu-id="8e690-167">ClickOnce ファイル ハンドラーによって表示されるインターフェイス、メッセージ、オプションは、アクセスするファイルの種類と構成によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8e690-167">The interface, messaging, and options shown by the ClickOnce file handler will vary depending on the type and configuration of the file that's accessed.</span></span>

### <span data-ttu-id="8e690-168">ClickOnce が無効になっている場合</span><span class="sxs-lookup"><span data-stu-id="8e690-168">ClickOnce disabled</span></span>

1. <span data-ttu-id="8e690-169">ユーザーが ClickOnce のサポートを要求するページへのリンクを開くと、次のスクリーンショットに示されているようなメッセージがダウンロード トレイに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e690-169">When a user opens a link to a page that requests ClickOnce support, they will see a message in the download tray that is similar to the one in the next screenshot.</span></span>

   ![ファイルのダウンロードを確認するメッセージ](./media/edge-learn-more-co-di/edge-clickonce-disabled-1.png)

### <span data-ttu-id="8e690-171">DirectInvoke が有効になっている場合</span><span class="sxs-lookup"><span data-stu-id="8e690-171">DirectInvoke enabled</span></span>

1. <span data-ttu-id="8e690-172">ユーザーが DirectInvoke のサポートを要求するページへのリンクを開くと、次のスクリーンショットに示されているメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e690-172">A user opens a link to a page that requests DirectInvoke support and gets the prompt in the next screenshot.</span></span>

   ![ファイルを開くかどうかを尋ねるメッセージ](./media/edge-learn-more-co-di/edge-directinvoke-open-link-1.png)

2. <span data-ttu-id="8e690-174">ユーザーが **[開く]** をクリックすると、要求されたファイル ハンドラーが開きます。</span><span class="sxs-lookup"><span data-stu-id="8e690-174">When the user clicks **Open**, the requested file handler is opened.</span></span> <span data-ttu-id="8e690-175">この例では、前のスクリーンショットに示されているドキュメントを開くために Microsoft Word が使用されています。</span><span class="sxs-lookup"><span data-stu-id="8e690-175">In this example, Microsoft Word is used to open the document that's shown in the previous screenshot.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8e690-176">DirectInvoke ファイル ハンドラーによって表示されるインターフェイス、メッセージ、オプションは、アクセスするファイルの種類と構成によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8e690-176">The interface, messaging, and options shown by the DirectInvoke file handler will vary depending on the type and configuration of the file that's accessed.</span></span>

### <span data-ttu-id="8e690-177">DirectInvoke が無効になっている場合</span><span class="sxs-lookup"><span data-stu-id="8e690-177">DirectInvoke disabled</span></span>

1. <span data-ttu-id="8e690-178">ユーザーが DirectInvoke のサポートを要求するページへのリンクを開くと、DirectInvoke は、ClickOnce が無効になっている場合と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="8e690-178">When a user opens a link to a page that requests DirectInvoke support, DirectInvoke behaves the same as when ClickOnce is disabled.</span></span> <span data-ttu-id="8e690-179">次のスクリーンショットのようなメッセージがダウンロード トレイに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e690-179">They will see a message in the download tray that's similar to the one in the next screenshot.</span></span>

   ![ファイルを開くかどうかを尋ねるメッセージ](./media/edge-learn-more-co-di/edge-directinvoke-open-link-2.png)

## <span data-ttu-id="8e690-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e690-181">See also</span></span>

- [<span data-ttu-id="8e690-182">ClickOnce のセキュリティと展開</span><span class="sxs-lookup"><span data-stu-id="8e690-182">ClickOnce security and deployment</span></span>](https://go.microsoft.com/fwlink/?linkid=2099880)
- [<span data-ttu-id="8e690-183">Internet Explorer での DirectInvoke の使用</span><span class="sxs-lookup"><span data-stu-id="8e690-183">DirectInvoke in Internet Explorer</span></span>](https://go.microsoft.com/fwlink/?linkid=2099871)
- [<span data-ttu-id="8e690-184">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="8e690-184">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
