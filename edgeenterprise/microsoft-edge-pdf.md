---
title: Microsoft Edge の PDF リーダー
ms.author: adigan
author: dan-wesley
manager: balajek
ms.date: 08/05/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge の PDF リーダーについて説明します。
ms.openlocfilehash: c189bc08d4af0c9d5c4d9c573e0b5b7ef32a7fb3
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980523"
---
# <span data-ttu-id="48911-103">Microsoft Edge の PDF リーダー</span><span class="sxs-lookup"><span data-stu-id="48911-103">PDF reader in Microsoft Edge</span></span>

<span data-ttu-id="48911-104">PDFファイルは、日常生活でかなり大きな割合を占めています。</span><span class="sxs-lookup"><span data-stu-id="48911-104">PDF files make up a substantial part of our day-to-day lives.</span></span> <span data-ttu-id="48911-105">これらは、契約書および合意書、ニュースレター、申込用紙、リサーチ記事、履歴書などのフォームに使用されます。</span><span class="sxs-lookup"><span data-stu-id="48911-105">They come in the form of contracts and agreements, newsletters, forms, research articles, resumes, and so on.</span></span> <span data-ttu-id="48911-106">これらのファイルは、企業にとって高い信頼性、安全性、および性能を備えた PDF リーダーを採用する必要性を協調します。</span><span class="sxs-lookup"><span data-stu-id="48911-106">These files highlight the need for a reliable, secure, and powerful PDF reader that can be adopted by Enterprises.</span></span>

<span data-ttu-id="48911-107">Microsoft Edge には、組み込みの PDF リーダーが用意されています。このリーダーを使用すると、ローカル、オンライン、または Web ページに埋め込まれた PDF ファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="48911-107">Microsoft Edge comes with a built-in PDF reader that lets you open your local pdf files, online pdf files, or pdf files embedded in web pages.</span></span> <span data-ttu-id="48911-108">これらのファイルに注釈を付けて、インクや強調表示することができます。</span><span class="sxs-lookup"><span data-stu-id="48911-108">You can annotate these files with ink and highlighting.</span></span> <span data-ttu-id="48911-109">この PDF リーダーでは、Web ページおよび PDF ドキュメントのニーズを満たす単一のアプリケーションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="48911-109">This PDF reader gives users a single application to meet web page and PDF document needs.</span></span> <span data-ttu-id="48911-110">Microsoft Edge PDF リーダーは、Windows および macOS デスクトップ プラットフォームで動作する、安全で信頼性の高いアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="48911-110">The Microsoft Edge PDF reader is a secure and reliable application that works across the Windows and macOS desktop platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="48911-111">この記事は Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="48911-111">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="48911-112">前提条件、サポート、および制約</span><span class="sxs-lookup"><span data-stu-id="48911-112">Prerequisites, support, and constraints</span></span>

<span data-ttu-id="48911-113">次の表は、Microsoft Edge で各 PDF リーダー機能をサポートするチャネルとバージョンを示しています。</span><span class="sxs-lookup"><span data-stu-id="48911-113">The following table shows which channels and versions of Microsoft Edge support each PDF reader feature.</span></span>

| <span data-ttu-id="48911-114">機能</span><span class="sxs-lookup"><span data-stu-id="48911-114">Feature</span></span> | <span data-ttu-id="48911-115">Stable チャネル バージョン</span><span class="sxs-lookup"><span data-stu-id="48911-115">Stable channel version</span></span> |
|---------|------------------------|
| <span data-ttu-id="48911-116">ローカル、オンライン、および埋め込みの PDF ファイルを表示して印刷する</span><span class="sxs-lookup"><span data-stu-id="48911-116">View and print local, online, and embedded PDF files</span></span> | <span data-ttu-id="48911-117">79.0.309.71</span><span class="sxs-lookup"><span data-stu-id="48911-117">79.0.309.71</span></span>                |
| <span data-ttu-id="48911-118">基本フォームの入力</span><span class="sxs-lookup"><span data-stu-id="48911-118">Basic form filling</span></span><br><span data-ttu-id="48911-119">(JavaScript フォームはサポートされていません)</span><span class="sxs-lookup"><span data-stu-id="48911-119">(JavaScript forms aren't supported)</span></span> | <span data-ttu-id="48911-120">79.0.309.71</span><span class="sxs-lookup"><span data-stu-id="48911-120">79.0.309.71</span></span>           |
| <span data-ttu-id="48911-121">インク操作</span><span class="sxs-lookup"><span data-stu-id="48911-121">Inking</span></span>  | <span data-ttu-id="48911-122">80.0.361.48</span><span class="sxs-lookup"><span data-stu-id="48911-122">80.0.361.48</span></span>            |
| <span data-ttu-id="48911-123">インク操作のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="48911-123">Ink customization</span></span> | <span data-ttu-id="48911-124">83.0.478.54</span><span class="sxs-lookup"><span data-stu-id="48911-124">83.0.478.54</span></span>  |
| <span data-ttu-id="48911-125">Highlight</span><span class="sxs-lookup"><span data-stu-id="48911-125">Highlight</span></span>  | <span data-ttu-id="48911-126">81.0.416.53</span><span class="sxs-lookup"><span data-stu-id="48911-126">81.0.416.53</span></span>         |
| <span data-ttu-id="48911-127">音声読み上げ</span><span class="sxs-lookup"><span data-stu-id="48911-127">Read Aloud</span></span> | <span data-ttu-id="48911-128">現在、[Microsoft Edge Insider](https://www.microsoftedgeinsider.com/) チャネルで宣伝中</span><span class="sxs-lookup"><span data-stu-id="48911-128">Currently being promoted in [Microsoft Edge Insider](https://www.microsoftedgeinsider.com/) channels</span></span> |
| <span data-ttu-id="48911-129">MIP 保護ファイルの表示</span><span class="sxs-lookup"><span data-stu-id="48911-129">View MIP protected files</span></span> | <span data-ttu-id="48911-130">80.0.361.48 の Windows サポート</span><span class="sxs-lookup"><span data-stu-id="48911-130">Windows support in 80.0.361.48</span></span><br><span data-ttu-id="48911-131">81.0.416.53 の Mac のサポート</span><span class="sxs-lookup"><span data-stu-id="48911-131">Mac support in 81.0.416.53</span></span> |
|  <span data-ttu-id="48911-132">IRM 保護ファイルの表示</span><span class="sxs-lookup"><span data-stu-id="48911-132">View IRM protected files</span></span>  | <span data-ttu-id="48911-133">83.0.478.37</span><span class="sxs-lookup"><span data-stu-id="48911-133">83.0.478.37</span></span>            |

### <span data-ttu-id="48911-134">制約</span><span class="sxs-lookup"><span data-stu-id="48911-134">Constraints</span></span>

<span data-ttu-id="48911-135">現在の PDF リーダーでは、次のような制約があります。</span><span class="sxs-lookup"><span data-stu-id="48911-135">Note the following constraints for the current PDF reader:</span></span>

-  <span data-ttu-id="48911-136">XML Forms Architecture (XFA) は、Microsoft Edge でサポートされていない旧式のフォームです。</span><span class="sxs-lookup"><span data-stu-id="48911-136">XML Forms Architecture (XFA), is a legacy format of forms that isn't  supported in Microsoft Edge.</span></span>
-  <span data-ttu-id="48911-137">現在サポートされていないアクセシビリティ シナリオに関連するドキュメントは、[Microsoft アクセシビリティ適合レポート](https://cloudblogs.microsoft.com/industry-blog/government/2018/09/11/accessibility-conformance-reports/) ブログに記載されています。</span><span class="sxs-lookup"><span data-stu-id="48911-137">Documentation related to Accessibility scenarios that currently aren't supported can be found on the [Microsoft Accessibility Conformance Reports](https://cloudblogs.microsoft.com/industry-blog/government/2018/09/11/accessibility-conformance-reports/) blog.</span></span>

## <span data-ttu-id="48911-138">機能</span><span class="sxs-lookup"><span data-stu-id="48911-138">Features</span></span>

### <span data-ttu-id="48911-139">インク操作</span><span class="sxs-lookup"><span data-stu-id="48911-139">Inking</span></span>

<span data-ttu-id="48911-140">PDF ファイルのインク操作を行うと、 PDF フォームに手軽に参照できるメモを取ったり、サインしたり、記入したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="48911-140">Inking on PDF files comes in handy to take quick notes for easy reference, sign, or fill out PDF forms.</span></span> <span data-ttu-id="48911-141">この機能は、Microsoft Edge で使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="48911-141">This capability is now available in Microsoft Edge.</span></span> <span data-ttu-id="48911-142">必要に応じた PDF ファイルのインク操作に加えて、PDF の別の部分に注目を集めるために色を使用したりストロークの幅を使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="48911-142">In addition to inking PDF files as needed, you can use color and stroke width to bring attention to different parts of the PDF file.</span></span> <span data-ttu-id="48911-143">次のスクリーンショットは、ユーザーが PDF ページにインク操作を追加できるようにする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="48911-143">The next screenshot shows how a user can add inking to a pdf page.</span></span>

<!-- SCREENSHOT -->
![PDF ページにインク操作を追加する](media/microsoft-edge-pdf/pdf-reader-inking.png)

### <span data-ttu-id="48911-145">Highlight</span><span class="sxs-lookup"><span data-stu-id="48911-145">Highlight</span></span>

<span data-ttu-id="48911-146">Microsoft Edge の PDF リーダーには、強調表示の追加と編集のサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="48911-146">PDF reader in Microsoft Edge comes with support for adding and editing highlights.</span></span> <span data-ttu-id="48911-147">強調表示を作成するには、シンプルにテキストを選択し、それを右クリックしてメニューの [強調表示] を選び、目的の色を選びます。</span><span class="sxs-lookup"><span data-stu-id="48911-147">To create a highlight, the user simply needs to select the text, right-click on it, select highlights in the menu and choose the desired color.</span></span> <span data-ttu-id="48911-148">次のスクリーンショットでは、使用できる強調表示オプションを示しています。</span><span class="sxs-lookup"><span data-stu-id="48911-148">The next screenshot shows the highlight options that are available.</span></span>

![PDF リーダーで強調表示オプションを使用する](media/microsoft-edge-pdf/pdf-reader-highlight.png)

### <span data-ttu-id="48911-150">音声読み上げ</span><span class="sxs-lookup"><span data-stu-id="48911-150">Read Aloud</span></span>

<span data-ttu-id="48911-151">PDF 用の音声読み上げを行うことで、ユーザーは、重要なタスクを実行しながら PDF コンテンツを聞くことができる便利な機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="48911-151">Read Aloud for PDF adds the convenience of listening to PDF content while carrying out other tasks that may be important to users.</span></span> <span data-ttu-id="48911-152">また、聴覚障がいを持つ学習者がコンテンツを絞り込むことができるので、より学習に取り組みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="48911-152">It also helps auditory learners focus on the content, which makes learning much easier.</span></span> <span data-ttu-id="48911-153">次のスクリーンショットに、音声読み上げの例を示します。</span><span class="sxs-lookup"><span data-stu-id="48911-153">The next screenshot shows a Read Aloud example.</span></span> <span data-ttu-id="48911-154">強調表示されているのは、現在読み取り中のテキストです。</span><span class="sxs-lookup"><span data-stu-id="48911-154">The highlighting shows the text that is currently being read.</span></span>

![PDF リーダーで強調表示オプションを使用する](media/microsoft-edge-pdf/pdf-reader-read-aloud-example.png)

### <span data-ttu-id="48911-156">保護された PDF</span><span class="sxs-lookup"><span data-stu-id="48911-156">Protected PDFs</span></span>

<span data-ttu-id="48911-157">[Microsoft Information Protection (MIP)](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) により、ユーザーは組織のコンプライアンス ポリシーに準拠しながら、他のユーザーと安全に共同作業することが可能です。</span><span class="sxs-lookup"><span data-stu-id="48911-157">[Microsoft Information Protection (MIP)](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) enables users to collaborate with others securely, while adhering to your organization's compliance policies.</span></span> <span data-ttu-id="48911-158">ファイルが保護された後、ユーザーがアクセスできるアクションは、割り当てられているアクセス許可によって決まります。</span><span class="sxs-lookup"><span data-stu-id="48911-158">After a file is protected, the actions users can take on it are determined by the permissions assigned to them.</span></span>

<span data-ttu-id="48911-159">これらのファイルは、他のソフトウェアをダウンロードしたり、アドインをインストールしたりすることなく、ブラウザーで直接開くことができます。</span><span class="sxs-lookup"><span data-stu-id="48911-159">These files can be opened directly in the browser, without the need to download any other software, or install any add-in.</span></span> <span data-ttu-id="48911-160">これにより、MIP が提供するセキュリティが直接ブラウザに統合され、シームレスなワークフローを実現します。</span><span class="sxs-lookup"><span data-stu-id="48911-160">This integrates the security provided by MIP directly into the browser, providing a seamless workflow.</span></span>

<!-- SCREENSHOT -->
![保護された PDF ドキュメント。](media/microsoft-edge-pdf/pdf-reader-protected-pdf2.png)

<span data-ttu-id="48911-162">MIP で保護されたファイルに加えて、SharePoint ライブラリに保護された [Information Rights Management (IRM)](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center?view=o365-worldwide) 内の PDFファイルは、ブラウザーでネイティブに開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="48911-162">In addition to MIP protected files, PDF files in [Information Rights Management (IRM)](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center?view=o365-worldwide) protected SharePoint libraries can also be opened natively in the browser.</span></span>

<span data-ttu-id="48911-163">Microsoft Edge では、ユーザーはローカルまたはクラウドに保存されている MIP 保護ファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="48911-163">With Microsoft Edge, users can view MIP protected files saved locally, or in the cloud.</span></span> <span data-ttu-id="48911-164">ローカルに保存した場合、ファイルをブラウザーで直接開くことができます。</span><span class="sxs-lookup"><span data-stu-id="48911-164">If saved locally, the file can be opened directly in the browser.</span></span> <span data-ttu-id="48911-165">クラウドサービスから SharePoint としてファイルを開いた場合、ユーザーは [ブラウザーで開く] オプションを使用することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="48911-165">If the file is opened from a cloud service as SharePoint, the user may need to use the "Open in browser" option.</span></span>

<span data-ttu-id="48911-166">ユーザーが Microsoft Edge にログインしているプロファイルに、少なくともファイルを表示するアクセス許可が与えられている場合、Microsoft Edge でファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="48911-166">If the profile that the user is logged into Microsoft Edge with has at least view permissions to the file, the file will open in Microsoft Edge.</span></span>

<!-- SCREENSHOT -->
![MIP によって保護されている SharePoint PDF ページを保存するかどうかを確認する](media/microsoft-edge-pdf/pdf-reader-sharepoint-irm.png)

## <span data-ttu-id="48911-168">アクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="48911-168">Accessibility</span></span>

<span data-ttu-id="48911-169">PDF リーダーには、Windows および macOS デバイスでのキーボードのアクセシビリティ、ハイコントラスト モード、スクリーンリーダーのサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="48911-169">The PDF reader comes with support for Keyboard accessibility, High contrast mode, and screen reader support across Windows and macOS devices.</span></span>

### <span data-ttu-id="48911-170">キーボードのアクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="48911-170">Keyboard Accessibility</span></span>

<span data-ttu-id="48911-171">ユーザーは、キーボードを使用して、フォームフィールドや強調表示などのユーザーが操作できるドキュメントの一部に移動できます。</span><span class="sxs-lookup"><span data-stu-id="48911-171">Users can use navigate to different parts of the document that a user can interact with, such as form fields and highlights, using the keyboard.</span></span>

<!-- SCREENSHOT -->

### <span data-ttu-id="48911-172">ハイ コントラスト モード</span><span class="sxs-lookup"><span data-stu-id="48911-172">High contrast mode</span></span>

<span data-ttu-id="48911-173">PDF リーダーは、オペレーティング システム レベルで定義された設定を使用して、PDF コンテンツをハイ コントラスト モードで表示します。</span><span class="sxs-lookup"><span data-stu-id="48911-173">PDF reader will use the settings defined at the operating system level to render PDF content in high contrast mode.</span></span>

<!-- SCREENSHOT -->
<!--![High contrast mode for pdf file](media/microsoft-edge-pdf/pdf-reader-high-contrast.png)-->

### <span data-ttu-id="48911-174">スクリーン リーダーのサポート</span><span class="sxs-lookup"><span data-stu-id="48911-174">Screen reader support</span></span>

<span data-ttu-id="48911-175">ユーザーは、Windows および Mac コンピューターのスクリーン リーダーを使用して、PDF ファイル内を移動したり、読んだりすることができます。</span><span class="sxs-lookup"><span data-stu-id="48911-175">Users can navigate through and read PDF files using screen readers on Windows and Mac computers.</span></span> <!--The next screenshot shows the toolbar that users can use for audio settings when they're using the Read Aloud option in PDF reader. -->

<!-- SCREENSHOT -->
<!--
![Screen reader toolbar](media/microsoft-edge-pdf/pdf-reader-read-aloud.png) -->

## <span data-ttu-id="48911-176">セキュリティと信頼性</span><span class="sxs-lookup"><span data-stu-id="48911-176">Security and reliability</span></span>

<span data-ttu-id="48911-177">セキュリティは、あらゆる組織にとって最も重要な原則です。</span><span class="sxs-lookup"><span data-stu-id="48911-177">Security is among the most important tenets for any organization.</span></span> <span data-ttu-id="48911-178">PDF リーダーのセキュリティは、Microsoft Edge セキュリティの設計に必要不可欠です。</span><span class="sxs-lookup"><span data-stu-id="48911-178">PDF reader security is an integral part of the Microsoft Edge security design.</span></span> <span data-ttu-id="48911-179">PDF リーダーの観点から最も重要なセキュリティ機能は2つあります。それは、プロセスの分離および Microsoft Defender Application Guard (Application Guard) です。</span><span class="sxs-lookup"><span data-stu-id="48911-179">Two of the most important security features From a PDF reader perspective, two important security features are process isolation and Microsoft Defender Application Guard (Application Guard).</span></span>

- <span data-ttu-id="48911-180">プロセスの分離。</span><span class="sxs-lookup"><span data-stu-id="48911-180">Process isolation.</span></span> <span data-ttu-id="48911-181">異なる Web サイトから開いた PDF は、プロセスが完全に分離されます。</span><span class="sxs-lookup"><span data-stu-id="48911-181">PDFs opened from different web sites are completely process isolated.</span></span> <span data-ttu-id="48911-182">ブラウザーは、いかなる Web サイトとも通信する必要はなく、別のソースから開いている PDF ファイルと通信する必要もありません。</span><span class="sxs-lookup"><span data-stu-id="48911-182">The browser doesn't have to communicate with any websites, or PDF files opened from another source.</span></span> <span data-ttu-id="48911-183">PDF の閲覧は、危険にさらされた PDF を攻撃の拠点として計画されたいかなる攻撃からもセキュリティで保護されます。</span><span class="sxs-lookup"><span data-stu-id="48911-183">PDF browsing is secure from any attacks that plan to use compromised PDFs as an attack surface.</span></span>

- <span data-ttu-id="48911-184">Application Guard。</span><span class="sxs-lookup"><span data-stu-id="48911-184">Application Guard.</span></span> <span data-ttu-id="48911-185">Application Guard を使用すると、管理者は組織で信頼されるサイトの一覧を設定することが可能です。</span><span class="sxs-lookup"><span data-stu-id="48911-185">With Application Guard, admins can set a list of sites that are trusted by their organization.</span></span> <span data-ttu-id="48911-186">ユーザーが他のいかなるサイトを開いた場合でも、Application Guard ウィンドウによって独自のコンテナーを実行し、分離して開かれます。</span><span class="sxs-lookup"><span data-stu-id="48911-186">If users open any other sites, they are opened in a separate Application Guard window that runs in its own container.</span></span> <span data-ttu-id="48911-187">このコンテナーは、企業ネットワークとユーザーのコンピューター上のあらゆるデータが危険にさらされるのを防止するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="48911-187">The container helps protect the corporate network and any data on user's computer from being compromised.</span></span><br><br>
<span data-ttu-id="48911-188">また、この保護は、表示されるあらゆるオンライン PDF ファイルにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="48911-188">This protection also applies to any online PDF files that are viewed.</span></span> <span data-ttu-id="48911-189">さらに、Application Guard ウィンドウからダウンロードされたいかなる PDF ファイルも保存され、必要があれば、コンテナー内で再び開きます。</span><span class="sxs-lookup"><span data-stu-id="48911-189">Further, any PDF files that are downloaded from an Application Guard window are stored, and when needed, re-opened in the container.</span></span> <span data-ttu-id="48911-190">これにより、ファイルがダウンロードされた場合だけでなく、ライフサイクル全体を通した環境がセキュリティ保護されます。</span><span class="sxs-lookup"><span data-stu-id="48911-190">This helps keeps your environment secure not just when the file is downloaded, but through its whole lifecycle.</span></span> <span data-ttu-id="48911-191">詳細については、「[Application Guard](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-defender-application-guard)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48911-191">For more information, see [Application Guard](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-defender-application-guard).</span></span>

### <span data-ttu-id="48911-192">信頼性</span><span class="sxs-lookup"><span data-stu-id="48911-192">Reliability</span></span>

<span data-ttu-id="48911-193">Microsoft Edge は Chrome がベースなので、ユーザーは Google Chrome の表示に使用されるのと同じレベルの信頼性を期待できます。</span><span class="sxs-lookup"><span data-stu-id="48911-193">Because Microsoft Edge is Chromium-based, users can expect the same level of reliability that they're used to seeing in Google Chrome.</span></span>

## <span data-ttu-id="48911-194">PDF リーダーの展開と更新</span><span class="sxs-lookup"><span data-stu-id="48911-194">Deploy and update PDF reader</span></span>

<span data-ttu-id="48911-195">PDF リーダーは、Microsoft Edge ブラウザーの残りの部分で展開および更新されます。</span><span class="sxs-lookup"><span data-stu-id="48911-195">The PDF reader gets deployed and updated with the rest of the Microsoft Edge browser.</span></span> <span data-ttu-id="48911-196">Microsoft Edge の展開の詳細については、 [[Microsoft Edge を数百から数千の デバイスに展開する]](microsoft-edge-video-deploy.md)ビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="48911-196">To learn more about deploying Microsoft Edge, watch the [Deploy Microsoft Edge to hundreds or thousands of devices](microsoft-edge-video-deploy.md) video.</span></span> <span data-ttu-id="48911-197">展開の詳細については、[Microsoft Edge のドキュメント](https://docs.microsoft.com/DeployEdge/) ランディングページに掲載されています。</span><span class="sxs-lookup"><span data-stu-id="48911-197">You can also find more deployment information on the [Microsoft Edge documentation](https://docs.microsoft.com/DeployEdge/) landing page.</span></span>

> [!TIP]
> <span data-ttu-id="48911-198">組織で Microsoft Edge を既定の PDF リーダーにすることができます。</span><span class="sxs-lookup"><span data-stu-id="48911-198">You can make Microsoft Edge the default PDF reader for your organization.</span></span> <span data-ttu-id="48911-199">これを行うためには、[次の手順を実行します](https://docs.microsoft.com/deployedge/edge-default-browser)。</span><span class="sxs-lookup"><span data-stu-id="48911-199">To do this, [follow these steps](https://docs.microsoft.com/deployedge/edge-default-browser).</span></span>

## <span data-ttu-id="48911-200">ロードマップとフィードバック</span><span class="sxs-lookup"><span data-stu-id="48911-200">Roadmap and feedback</span></span>

<span data-ttu-id="48911-201">Microsoft Edge での PDF リーダーのロードマップは、[こちら](https://techcommunity.microsoft.com/t5/articles/roadmap-for-pdf-reader-in-microsoft-edge/m-p/1467667) で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="48911-201">The roadmap for PDF Reader in Microsoft Edge is available [here](https://techcommunity.microsoft.com/t5/articles/roadmap-for-pdf-reader-in-microsoft-edge/m-p/1467667).</span></span>

<span data-ttu-id="48911-202">お客様からのご意見をお待ちしております。</span><span class="sxs-lookup"><span data-stu-id="48911-202">We're actively looking at feedback from you about the features you find important.</span></span> <span data-ttu-id="48911-203">[Microsoft Edge UserVoice](https://microsoftedge.uservoice.com/) および [Microsoft Edge Insider](https://techcommunity.microsoft.com/t5/microsoft-edge-insider/ct-p/MicrosoftEdgeInsider) フォーラムを通して、フィードバックをお送りください。</span><span class="sxs-lookup"><span data-stu-id="48911-203">Feel free to send us feedback through [Microsoft Edge UserVoice](https://microsoftedge.uservoice.com/) and on [Microsoft Edge Insider](https://techcommunity.microsoft.com/t5/microsoft-edge-insider/ct-p/MicrosoftEdgeInsider) forum.</span></span>

## <span data-ttu-id="48911-204">関連項目</span><span class="sxs-lookup"><span data-stu-id="48911-204">See also</span></span>

- [<span data-ttu-id="48911-205">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="48911-205">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)