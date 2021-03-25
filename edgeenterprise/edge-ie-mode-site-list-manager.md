---
title: 'Microsoft Edge の Enterprise Site List Manager '
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 02/02/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 'Microsoft Edge で Enterprise Site List Manager を有効にして使用する '
ms.openlocfilehash: 51d431f838bcb385a5cd8f4ef85651e9254aed62
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447351"
---
# <a name="enterprise-site-list-manager-in-microsoft-edge"></a><span data-ttu-id="adb92-103">Microsoft Edge の Enterprise Site List Manager</span><span class="sxs-lookup"><span data-stu-id="adb92-103">Enterprise Site List Manager in Microsoft Edge</span></span>

<span data-ttu-id="adb92-104">この記事では、Microsoft Edge で Enterprise Site List Manager にアクセスして、Internet Explorer モード用の Enterprise Mode Site List を作成、編集、およびエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="adb92-104">This article explains how to enable access to and use the Enterprise Site List Manager in Microsoft Edge to create, edit and export your Enterprise Mode Site List for Internet Explorer mode.</span></span>

> [!NOTE]
> <span data-ttu-id="adb92-105">この記事は、Microsoft Edge バージョン 89 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="adb92-105">This article applies to Microsoft Edge version 89 or later.</span></span> 

## <a name="overview"></a><span data-ttu-id="adb92-106">概要</span><span class="sxs-lookup"><span data-stu-id="adb92-106">Overview</span></span>

<span data-ttu-id="adb92-107">Enterprise Site List Manager は、[スタンドアロンの Enterprise Mode Site List Manager ツール](https://www.microsoft.com/download/details.aspx?id=49974)のブラウザー版で、組織のサイト リストを作成、編集、およびエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="adb92-107">The Enterprise Site List Manager is an in-browser version of the [standalone Enterprise Mode Site List Manager tool](https://www.microsoft.com/download/details.aspx?id=49974) that lets you create, edit, and export your organization’s site list.</span></span>

<span data-ttu-id="adb92-108">機能が強化された Internet Explorer モード用のツールは、今後 Microsoft Edge の Enterprise Site List Manager で利用可能になる予定です。</span><span class="sxs-lookup"><span data-stu-id="adb92-108">Future improvements to the tool for Internet Explorer mode will be available through Enterprise Site List Manager in Microsoft Edge.</span></span> <span data-ttu-id="adb92-109">スタンドアロン ツールは引き続きダウンロード センターから入手できますが、機能は更新されません。</span><span class="sxs-lookup"><span data-stu-id="adb92-109">The standalone tool will continue to be available in the Download Center but won't get any feature updates.</span></span>

## <a name="enabling-access-to-enterprise-site-list-manager"></a><span data-ttu-id="adb92-110">Enterprise Site List Manager へのアクセスの有効化</span><span class="sxs-lookup"><span data-stu-id="adb92-110">Enabling access to Enterprise Site List Manager</span></span>

<span data-ttu-id="adb92-111">[EnterpriseModeSiteListManagerAllowed](./microsoft-edge-policies.md#enterprisemodesitelistmanagerallowed) グループ ポリシーを使用して、ツールへのアクセスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="adb92-111">You can configure access to the tool by using the [EnterpriseModeSiteListManagerAllowed](./microsoft-edge-policies.md#enterprisemodesitelistmanagerallowed) group policy.</span></span>

<span data-ttu-id="adb92-112">有効にすると、左側のナビゲーション ウィンドウに Enterprise Site List Manager という名前のオプションが *edge://compat* に表示されます。</span><span class="sxs-lookup"><span data-stu-id="adb92-112">If enabled, your users will see an option named Enterprise Site List Manager on the left navigation pane in *edge://compat*.</span></span> <span data-ttu-id="adb92-113">[無効] の場合、左側のナビゲーション ウィンドウにエンタープライズ サイト リスト マネージャーへのエントリ ポイントは表示されません。</span><span class="sxs-lookup"><span data-stu-id="adb92-113">If disabled, users will not see the entry point to Enterprise Site List Manager in the left navigation pane.</span></span> <span data-ttu-id="adb92-114">これは既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="adb92-114">This is the default behavior.</span></span>

## <a name="using-the-enterprise-site-list-manager"></a><span data-ttu-id="adb92-115">Enterprise Site List Manager の使用</span><span class="sxs-lookup"><span data-stu-id="adb92-115">Using the Enterprise Site List Manager</span></span>

<span data-ttu-id="adb92-116">Enterprise Site List Manager ツールは、スキーマの v.2 バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="adb92-116">The Enterprise Site List Manager tool uses the v.2 version of the schema.</span></span> <span data-ttu-id="adb92-117">Enterprise Site List Manager (スキーマ v.2) に v.1 バージョン スキーマをインポートすると、XML が v.2 バージョンのスキーマに保存されます。</span><span class="sxs-lookup"><span data-stu-id="adb92-117">If you import a v.1 version schema into the Enterprise Site List Manager (schema v.2), the XML is saved into the v.2 version of the schema.</span></span> <span data-ttu-id="adb92-118">「[エンタープライズ モード スキーマ v.2 ガイダンス](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adb92-118">See [Enterprise Mode schema v.2 guidance](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>

### <a name="add-single-sites-to-your-site-list"></a><span data-ttu-id="adb92-119">サイト リストへの単一サイトの追加</span><span class="sxs-lookup"><span data-stu-id="adb92-119">Add single sites to your site list</span></span>  

<span data-ttu-id="adb92-120">サイト リストに個々のサイトを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="adb92-120">Use the following steps to add individual sites to your site list.</span></span>

> [!NOTE]
> <span data-ttu-id="adb92-121">特定の URL だけを追加できます。インターネット ゾーンやイントラネット ゾーンを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="adb92-121">You can only add specific URLs, not Internet or Intranet Zones.</span></span>

1. <span data-ttu-id="adb92-122">Enterprise Site List Manager で、 **[サイトを追加する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="adb92-122">In the Enterprise Site List Manager, click **Add a site**.</span></span>
2. <span data-ttu-id="adb92-123">追加する Web サイトの URL を入力します (例: URL ボックスに  <domain>.com または  <domain>.com/<path>  を入力)。</span><span class="sxs-lookup"><span data-stu-id="adb92-123">Type the URL for the website you’d like to add, for example: <domain>.com or <domain>.com/<path> in the URL box.</span></span>
3. <span data-ttu-id="adb92-124">**[開く]**  リストから、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="adb92-124">Select one of the following options from the **Open in** list:</span></span>

   - <span data-ttu-id="adb92-125">**IE11**。</span><span class="sxs-lookup"><span data-stu-id="adb92-125">**IE11**.</span></span> <span data-ttu-id="adb92-126">IE11 アプリケーションでサイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="adb92-126">Opens the site in the IE11 application.</span></span>
   - <span data-ttu-id="adb92-127">**IE モード**。</span><span class="sxs-lookup"><span data-stu-id="adb92-127">**IE mode**.</span></span> <span data-ttu-id="adb92-128">Microsoft Edge が有効の場合は Internet Explorer モードで、有効でない場合は IE11 アプリでサイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="adb92-128">Opens the site in Internet Explorer mode on Microsoft Edge if enabled and in the IE11 app otherwise.</span></span> <span data-ttu-id="adb92-129">「 [Microsoft Edge の Internet Explorer モード](./edge-ie-mode.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adb92-129">See [Internet Explorer mode on Microsoft Edge](./edge-ie-mode.md).</span></span>
   - <span data-ttu-id="adb92-130">**MSEdge**。</span><span class="sxs-lookup"><span data-stu-id="adb92-130">**MSEdge**.</span></span> <span data-ttu-id="adb92-131">Microsoft Edge でサイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="adb92-131">Opens the site in Microsoft Edge.</span></span>
   - <span data-ttu-id="adb92-132">**設定可能**。</span><span class="sxs-lookup"><span data-stu-id="adb92-132">**Configurable**.</span></span> <span data-ttu-id="adb92-133">サイトが IE モード エンジンの決定に参加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="adb92-133">Allows the site to participate in IE mode engine determination.</span></span> <span data-ttu-id="adb92-134">「[IE モードで構成可能なサイト](./edge-learnmore-configurable-sites-ie-mode.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adb92-134">See [Configurable sites in IE mode](./edge-learnmore-configurable-sites-ie-mode.md)</span></span>
   - <span data-ttu-id="adb92-135">**なし**。</span><span class="sxs-lookup"><span data-stu-id="adb92-135">**None**.</span></span> <span data-ttu-id="adb92-136">ユーザーが選択したブラウザーで開きます。</span><span class="sxs-lookup"><span data-stu-id="adb92-136">Opens in whatever browser the user chooses.</span></span>  

4. <span data-ttu-id="adb92-137"> *\*[互換モード]** で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="adb92-137">Under **Compat Mode**, choose one of the following options:</span></span>

   - <span data-ttu-id="adb92-138">**IE8Enterprise**。</span><span class="sxs-lookup"><span data-stu-id="adb92-138">**IE8Enterprise**.</span></span> <span data-ttu-id="adb92-139">IE8 エンタープライズ モードでサイトを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="adb92-139">Loads the site in IE8 Enterprise Mode.</span></span>
   - <span data-ttu-id="adb92-140">**IE7Enterprise**。</span><span class="sxs-lookup"><span data-stu-id="adb92-140">**IE7Enterprise**.</span></span> <span data-ttu-id="adb92-141">IE7 エンタープライズ モードでサイトを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="adb92-141">Loads the site in IE7 Enterprise Mode.</span></span>
   - <span data-ttu-id="adb92-142">**IE[x]**。</span><span class="sxs-lookup"><span data-stu-id="adb92-142">**IE[x]**.</span></span> <span data-ttu-id="adb92-143">[x] はドキュメント モードの番号を示し、サイトは指定されたドキュメント モードで読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="adb92-143">Where [x] is the document mode number and the site loads in the specified document mode.</span></span>
   - <span data-ttu-id="adb92-144">**既定のモード**。</span><span class="sxs-lookup"><span data-stu-id="adb92-144">**Default Mode**.</span></span> <span data-ttu-id="adb92-145">ページの既定の互換モードを使ってサイトを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="adb92-145">Loads the site using the default compatibility mode for the page.</span></span>

   <span data-ttu-id="adb92-146">ドメイン内のパスには、ドメイン自体とは別の互換モードが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="adb92-146">The path within a domain can require a different compatibility mode from the domain itself.</span></span> <span data-ttu-id="adb92-147">たとえば、既定の IE11 ブラウザーではドメインに問題がないように見えても、パスに問題があるためエンタープライズ モードを使う必要がある場合などです。</span><span class="sxs-lookup"><span data-stu-id="adb92-147">For example, the domain might look fine in the default IE11 browser, but the path might have problems and require the use of Enterprise Mode.</span></span> <span data-ttu-id="adb92-148">以前にドメインを追加した場合、最初に選んだ互換性が保持されます。</span><span class="sxs-lookup"><span data-stu-id="adb92-148">If you added the domain previously, your original compatibility choice is still selected.</span></span> <span data-ttu-id="adb92-149">ただし、ドメインが新しい場合、自動的に  **[IE8 エンタープライズ モード]**  が選ばれます。</span><span class="sxs-lookup"><span data-stu-id="adb92-149">However, if the domain is new, **IE8 Enterprise Mode** is automatically selected.</span></span>

   <span data-ttu-id="adb92-150">エンタープライズ モードはドキュメント モードより優先されるため、エンタープライズ モード サイト一覧に既に含まれているサイトはこの更新の影響を受けず、引き続き通常どおりエンタープライズ モードで読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="adb92-150">Enterprise Mode takes precedence over document modes, so sites that are already included in the Enterprise Mode site list won’t be affected by this update and will continue to load in Enterprise Mode, as usual.</span></span> <span data-ttu-id="adb92-151">ドキュメント モードの使用方法について詳しくは、「  [ドキュメント モードとエンタープライズ モード サイト一覧を使って Web 互換性の問題を修正する](/internet-explorer/ie11-deploy-guide/fix-compat-issues-with-doc-modes-and-enterprise-mode-site-list)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="adb92-151">For more specific information about using document modes, see [Fix web compatibility issues using document modes and the Enterprise Mode site list](/internet-explorer/ie11-deploy-guide/fix-compat-issues-with-doc-modes-and-enterprise-mode-site-list).</span></span>

5. <span data-ttu-id="adb92-152">**[リダイレクトを許可する**] チェックボックスは、サーバ側リダイレクトの処理に適用されます。</span><span class="sxs-lookup"><span data-stu-id="adb92-152">The **Allow Redirect** checkbox applies to the treatment of server-side redirects.</span></span> <span data-ttu-id="adb92-153">このチェックボックスをオンにすると、[開く] タグで指定されたブラウザーでサーバ側リダイレクトが開きます。</span><span class="sxs-lookup"><span data-stu-id="adb92-153">If you check this box, server-side redirects will open in the browser specified by the open-in tag.</span></span> <span data-ttu-id="adb92-154">詳細については、 [こちら](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance#updated-schema-attributes)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adb92-154">For more information, see [here](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance#updated-schema-attributes).</span></span>
6. <span data-ttu-id="adb92-155">Web サイトに関するコメントを  **[コメント]** ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="adb92-155">Type any comments about the website into the **Comment** box.</span></span> <span data-ttu-id="adb92-156">管理者は、このツールを使用している間のみコメントを表示でき、これらのコメントはサイト リストの xml に保持されます。</span><span class="sxs-lookup"><span data-stu-id="adb92-156">Administrators can only see comments while they’re in this tool and these comments are retained in the site list xml.</span></span>
7. <span data-ttu-id="adb92-157"> *\*[追加]** をクリックして、サイトをサイト リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="adb92-157">Click **Add** to add the site to your site list.</span></span>

### <a name="export-site-list-to-xml"></a><span data-ttu-id="adb92-158">XML にサイト一覧をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="adb92-158">Export site list to XML</span></span>

<span data-ttu-id="adb92-159">Enterprise Site List Manager でサイト一覧を作成すると、その内容をエンタープライズ モード (.EMIE) または XML ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="adb92-159">After you create your site list in the Enterprise Site List Manager, you can export the contents to an Enterprise Mode (.EMIE) or XML file.</span></span> 

> [!NOTE]
> <span data-ttu-id="adb92-160">このファイルには、互換モードの選択を含むすべての URL が含まれているため、安全な場所に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="adb92-160">This file includes all of your URLs, including your compatibility mode selections and should be stored somewhere safe.</span></span>

<span data-ttu-id="adb92-161">サイト一覧をエクスポートするには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="adb92-161">To export the site list, follow these steps:</span></span>

1. <span data-ttu-id="adb92-162">Enterprise Site List Manager で、**[XML にエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="adb92-162">In the Enterprise Site List Manager, click **Export to XML**.</span></span>
2. <span data-ttu-id="adb92-163">**バージョン番号**と**ファイル名**を入力します。</span><span class="sxs-lookup"><span data-stu-id="adb92-163">Enter a **Version number** and a **File name**.</span></span>
3. <span data-ttu-id="adb92-164">**[エクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="adb92-164">Click **Export**.</span></span>

<span data-ttu-id="adb92-165">ファイルは、ローカルにもネットワーク共有にも保存できます。</span><span class="sxs-lookup"><span data-stu-id="adb92-165">You can save the file locally or to a network share.</span></span> <span data-ttu-id="adb92-166">ただし、必ずレジストリ キーで指定された場所に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="adb92-166">However, you must make sure you deploy it to the location specified in your registry key.</span></span> <span data-ttu-id="adb92-167">詳細については、「 [Internet Explorer モードをオンにして、サイト一覧を使用する](./edge-ie-mode-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adb92-167">For more information, see [Turn on Internet Explorer mode and use a site list](./edge-ie-mode-policies.md).</span></span>

### <a name="import-multiple-sites-to-your-site-list"></a><span data-ttu-id="adb92-168">サイト一覧に複数のサイトをインポートする</span><span class="sxs-lookup"><span data-stu-id="adb92-168">Import multiple sites to your site list</span></span>

<span data-ttu-id="adb92-169">.xml ファイルを作成したら、**[XML からインポート** を使用して、エディターにサイトを一括追加できます。</span><span class="sxs-lookup"><span data-stu-id="adb92-169">After you create your .xml file, you can bulk add sites to the editor using **Import from XML**.</span></span>

<span data-ttu-id="adb92-170">エディターのすべての内容を置き換える場合は、省略記号 (…) をクリックし、**[リストのクリア]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="adb92-170">If you want to replace all the contents in the editor, click  the ellipsis (…) and then choose **Clear list**.</span></span> <span data-ttu-id="adb92-171">エディターをクリアしたら、次の手順でサイトをインポートします。</span><span class="sxs-lookup"><span data-stu-id="adb92-171">After you clear the editor, use the following steps to import the site.</span></span>

1. <span data-ttu-id="adb92-172">Enterprise Site List Manager で、**[XML からインポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="adb92-172">In the Enterprise Site List Manager, click **Import from XML**.</span></span> 
2. <span data-ttu-id="adb92-173">**[ファイルの選択]** をクリックしてサイト一覧を選択し、含まれているサイトをツールに追加します。</span><span class="sxs-lookup"><span data-stu-id="adb92-173">Click **Choose file** to select your site list to add the included sites to the tool.</span></span> <span data-ttu-id="adb92-174">追加するサイト一覧を選択し、 **[開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="adb92-174">Pick the site list you want to add and then click **Open**.</span></span> <span data-ttu-id="adb92-175">インポートでサポートされる形式は、Enterprise Mode Site List の v.2 スキーマを含む .xml、.emie、または .txt です。</span><span class="sxs-lookup"><span data-stu-id="adb92-175">Supported formats for Import are .xml, .emie or .txt containing the v.2 schema for Enterprise Mode Site List.</span></span> <span data-ttu-id="adb92-176">「[エンタープライズ モード スキーマ v.2 ガイダンス](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adb92-176">See [Enterprise Mode schema v.2 guidance](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>
3. <span data-ttu-id="adb92-177"> *\*[読み込み]**  をクリックして、エディターでファイル tp からサイトを追加します。</span><span class="sxs-lookup"><span data-stu-id="adb92-177">Click **Load** to add the sites from the file tp the editor.</span></span>

<span data-ttu-id="adb92-178">ファイルは、ローカルにもネットワーク共有にも保存できます。</span><span class="sxs-lookup"><span data-stu-id="adb92-178">You can save the file locally or to a network share.</span></span> <span data-ttu-id="adb92-179">ただし、必ずレジストリ キーで指定された場所に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="adb92-179">However, you must make sure you deploy it to the location specified in your registry key.</span></span> <span data-ttu-id="adb92-180">詳細については、「 [Internet Explorer モードをオンにして、サイト一覧を使用する](./edge-ie-mode-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adb92-180">For more information, see [Turn on Internet Explorer mode and use a site list](./edge-ie-mode-policies.md).</span></span>

### <a name="edit-sites-in-your-site-list"></a><span data-ttu-id="adb92-181">サイト一覧内のサイトを編集する</span><span class="sxs-lookup"><span data-stu-id="adb92-181">Edit sites in your site list</span></span>

 <span data-ttu-id="adb92-182">Enterprise Site List Manager で既存のサイト エントリの属性を編集できます。</span><span class="sxs-lookup"><span data-stu-id="adb92-182">You can edit attributes of existing site entries in the Enterprise Site List Manager.</span></span> <span data-ttu-id="adb92-183">関連付けられたコメントを追加したり削除したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="adb92-183">You can also add, remove, or delete associated comments.</span></span>

1. <span data-ttu-id="adb92-184">Enterprise Site List Manager で省略記号 (…) をクリックし、編集する URL で **[サイトの編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="adb92-184">In the Enterprise Site List Manager, click the ellipsis (…) and choose **Edit site** for the URL you want to edit.</span></span>
2. <span data-ttu-id="adb92-185">URL 以外のサイト エントリの任意の属性を編集できます。</span><span class="sxs-lookup"><span data-stu-id="adb92-185">You can edit any attribute of the site entry except the URL.</span></span> <span data-ttu-id="adb92-186">編集が終了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="adb92-186">Click **Save** after you finish editing.</span></span>

   > [!NOTE]
   > <span data-ttu-id="adb92-187">サイト エントリを削除する場合は、手順 1 で **[サイトの削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="adb92-187">If you want to delete a site entry, choose **Delete site** in step 1.</span></span>

3. <span data-ttu-id="adb92-188">**[XML にエクスポート]** をクリックし、更新されたファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="adb92-188">Click **Export to XML**, and save the updated file.</span></span>

<span data-ttu-id="adb92-189">ファイルは、ローカルにもネットワーク共有にも保存できます。</span><span class="sxs-lookup"><span data-stu-id="adb92-189">You can save the file locally or to a network share.</span></span> <span data-ttu-id="adb92-190">ただし、必ずレジストリ キーで指定された場所に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="adb92-190">However, you must make sure you deploy it to the location specified in your registry key.</span></span> <span data-ttu-id="adb92-191">詳細については、「 [Internet Explorer モードをオンにして、サイト一覧を使用する](./edge-ie-mode-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adb92-191">For more information, see [Turn on Internet Explorer mode and use a site list](./edge-ie-mode-policies.md).</span></span>

### <a name="preview-your-site-list-in-xml-format"></a><span data-ttu-id="adb92-192">XML 形式でサイト一覧をプレビューする</span><span class="sxs-lookup"><span data-stu-id="adb92-192">Preview your site list in XML format</span></span>

<span data-ttu-id="adb92-193">エクスポートしてサイト一覧の場所に保存する前に、エディターでサイトを XML 形式でプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="adb92-193">You can preview the sites in the editor in XML format before you export and save to your site list location.</span></span> <span data-ttu-id="adb92-194">**[XML プレビュー]** をクリックして、新しいタブでファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="adb92-194">Click **XML preview** to open the file in a new tab.</span></span>

### <a name="search-in-the-enterprise-site-list-manager"></a><span data-ttu-id="adb92-195">Enterprise Site List Manager で検索する</span><span class="sxs-lookup"><span data-stu-id="adb92-195">Search in the Enterprise Site List Manager</span></span>

<span data-ttu-id="adb92-196">特定のサイトが既にサイト一覧に存在するかどうかは、検索して調べることができるため、もう一度追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="adb92-196">You can search to see if a specific site already appears in your site list so you don’t try to add it again.</span></span>

<span data-ttu-id="adb92-197">検索するには、エディターの右上隅にある  **[URL でサイトをフィルター処理する**] 検索ボックスに URL の一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="adb92-197">To search, type part of the URL into the **Filter sites by URL** search box on the top right-hand corner of the editor.</span></span>

## <a name="see-also"></a><span data-ttu-id="adb92-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="adb92-198">See also</span></span>

- [<span data-ttu-id="adb92-199">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="adb92-199">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="adb92-200">IE モードの概要</span><span class="sxs-lookup"><span data-stu-id="adb92-200">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="adb92-201">エンタープライズ モード スキーマ v.2 ガイダンス</span><span class="sxs-lookup"><span data-stu-id="adb92-201">Enterprise Mode schema v.2 guidance</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)
- [<span data-ttu-id="adb92-202">その他のエンタープライズ モード情報</span><span class="sxs-lookup"><span data-stu-id="adb92-202">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)