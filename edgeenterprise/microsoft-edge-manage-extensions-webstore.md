---
title: セルフホスト型 Microsoft Edge 拡張機能
ms.author: aspoddar
author: AndreaLBarr
manager: balajek
ms.date: 04/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: エンタープライズ内の拡張機能をパッケージ化し、Microsoft Edge をセルフホストする方法について説明します。
ms.openlocfilehash: 403b6879b15c146f40fa2564da76eae59b2abe88
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "11618187"
---
# <a name="self-host-microsoft-edge-extensions"></a><span data-ttu-id="7042e-103">セルフホスト型 Microsoft Edge 拡張機能</span><span class="sxs-lookup"><span data-stu-id="7042e-103">Self-host Microsoft Edge extensions</span></span>

<span data-ttu-id="7042e-104">この記事では、独自の Web ストアでホストする拡張機能をパッケージ化する基本的なガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7042e-104">This article provides basic guidance for packaging an extension to host on your own webstore.</span></span> <span data-ttu-id="7042e-105">また、組織内のデバイスとユーザーに拡張機能を展開する方法に関する手順も含まれています。</span><span class="sxs-lookup"><span data-stu-id="7042e-105">It also includes instructions on how to deploy extensions to devices and users in your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7042e-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="7042e-106">Prerequisites</span></span>

<span data-ttu-id="7042e-107">独自の拡張機能をセルフホストするには、拡張機能とそのマニフェスト ファイルに独自の Web ホスティング サービスを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7042e-107">To self-host your own extensions, you will need to provide your own web hosting services for the extensions and their manifest files.</span></span>

 <span data-ttu-id="7042e-108">次の手順では、ユーザーが既に拡張機能を作成し、XML ファイルの経験を持ち、グループ ポリシーの構成に関する知識を持ち、Windows レジストリの使い方を理解していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="7042e-108">The following steps assume that you’ve already created your extension, have some experience with XML files, have a working knowledge of configuring group policy, and know how to use the Windows registry.</span></span>

## <a name="publish-an-extension"></a><span data-ttu-id="7042e-109">拡張機能を発行する</span><span class="sxs-lookup"><span data-stu-id="7042e-109">Publish an extension</span></span>

<span data-ttu-id="7042e-110">拡張機能を発行する前に、CRX (Chrome 拡張機能) ファイルにパッキングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7042e-110">Before you publish an extension it needs to be packed into a CRX (Chrome extension) file.</span></span> <span data-ttu-id="7042e-111">拡張子を CRX ファイルとしてパッキングするためのガイドとして、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="7042e-111">Use the following steps as a guide to packing an extension as a CRX file.</span></span>

1. <span data-ttu-id="7042e-112">[Microsoft Edgeのアドレス ] バーで、\*[edge://extensions] \* に移動し、まだ有効になっていない場合は**開発者モード**を有効にします。 </span><span class="sxs-lookup"><span data-stu-id="7042e-112">In the Microsoft Edge address bar, go to *edge://extensions* and turn on **Developer mode** if it’s not already enabled.</span></span>
2. <span data-ttu-id="7042e-113">**[インストールされている拡張機能] **で、**[ 拡張機能をパック]** をクリックして、 CRX ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7042e-113">Under **Installed extensions**, click **Pack Extension** to create the CRX file.</span></span>
3. <span data-ttu-id="7042e-114">**[拡張機能をパック]** ダイアログを使用して、拡張機能のソースを含むディレクトリを検索します。</span><span class="sxs-lookup"><span data-stu-id="7042e-114">Use the **Pack extension** dialog to find the directory that has the source for the extension.</span></span> <span data-ttu-id="7042e-115">ディレクトリを選択し、**[拡張機能をパック]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7042e-115">Select the directory and then click **Pack extension**.</span></span>  <span data-ttu-id="7042e-116">これにより、PEM ファイルと共に CRX ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7042e-116">This will create your CRX file, along with a PEM file.</span></span> <span data-ttu-id="7042e-117">PEM ファイルは、拡張機能のバージョン更新に必要なので保存します。</span><span class="sxs-lookup"><span data-stu-id="7042e-117">Save the PEM file because it’s needed for making version updates to the extension.</span></span> <span data-ttu-id="7042e-118">次のスクリーンショットは、拡張機能のルート ディレクトリを検索する **[拡張機能をパック]** ダイアログを示しています。</span><span class="sxs-lookup"><span data-stu-id="7042e-118">The next screenshot shows the **Pack extension** dialog for locating the root directory of the extension.</span></span>

   :::image type="content" source="media/microsoft-edge-manage-extensions-webstore/manage-extensions-pack-dialog.png" alt-text="拡張機能のソース コードを検索する [拡張機能をパック] ダイアログ。":::

   > [!IMPORTANT]
   > <span data-ttu-id="7042e-120">PEM ファイルは拡張機能のキーであり、将来の更新に必要なので、安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="7042e-120">Store the PEM file in a safe location because it’s the key for the extension and it’s needed for future updates.</span></span>

4. <span data-ttu-id="7042e-121">CRX ファイルを [拡張機能] ウィンドウにドラッグし、読み込まれることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7042e-121">Drag the CRX file into your extensions window and make sure that it loads.</span></span>
5. <span data-ttu-id="7042e-122">拡張機能をテストし、ID フィールド (これは CRX ID) とバージョン番号をメモします。</span><span class="sxs-lookup"><span data-stu-id="7042e-122">Test the extension and take note of the ID field (this is the CRX ID) and version number.</span></span> <span data-ttu-id="7042e-123">この情報は後で必要になります。</span><span class="sxs-lookup"><span data-stu-id="7042e-123">You’ll need this information later.</span></span> <span data-ttu-id="7042e-124">次のスクリーンショットは、CRX ID を持つテスト拡張機能を示しています。</span><span class="sxs-lookup"><span data-stu-id="7042e-124">The next screenshot shows a test extension with its CRX ID.</span></span>

   :::image type="content" source="media/microsoft-edge-manage-extensions-webstore/manage-extensions-test-extension.png" alt-text="CRX ID を表示する拡張機能の例":::

6. <span data-ttu-id="7042e-126">CRX ファイルをホストにアップロードし、ダウンロード元の URL をメモします。</span><span class="sxs-lookup"><span data-stu-id="7042e-126">Upload the the CRX file to the host and note the URL of the location it will be downloaded from.</span></span> <span data-ttu-id="7042e-127">この情報は、XML マニフェスト ファイルに必要です。</span><span class="sxs-lookup"><span data-stu-id="7042e-127">This information is needed for the XML manifest file.</span></span>
7. <span data-ttu-id="7042e-128">アプリ/拡張機能 ID、ダウンロード URL、およびバージョンを使用してマニフェスト XML ファイルを作成するには、次のフィールドを定義します。</span><span class="sxs-lookup"><span data-stu-id="7042e-128">To create a manifest XML file with the app/extension ID, download URL, and version, define the following fields:</span></span>  

   - <span data-ttu-id="7042e-129">**appid** - 手順 5 の内線番号 ID</span><span class="sxs-lookup"><span data-stu-id="7042e-129">**appid** - The extension ID from step 5</span></span>
   - <span data-ttu-id="7042e-130">**codebase** - 手順 6 からの CRX ファイルのダウンロード場所</span><span class="sxs-lookup"><span data-stu-id="7042e-130">**codebase** - The download location for the CRX file from step 6</span></span>
   - <span data-ttu-id="7042e-131">**version** - 拡張機能のマニフェストで指定されたバージョンと一致する必要があるアプリ/拡張機能のバージョン。</span><span class="sxs-lookup"><span data-stu-id="7042e-131">**version** - The version of the app/extension, which should match the version specified in the manifest of the extension.</span></span>

   <span data-ttu-id="7042e-132">次のコード スニペットは、XML マニフェスト ファイルの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="7042e-132">The next code snippet shows an example of an XML manifest file.</span></span>

   ```xml
   <?xml version='1.0' encoding='UTF-8'?> 
   <gupdate xmlns='http://www.google.com/update2/response' protocol='2.0'> 
     <app appid='ekilpdeokbpjmminmhfcgkncmmohmfeb'> 
     <updatecheck codebase='https://app.somecompany.com/extensionfolder/helloworld.crx' version='1.0' /> 
     </app> 
   </gupdate> 
   ```

   <span data-ttu-id="7042e-133">詳細については、[「Microsoft Edge の拡張機能の自動更新 - Microsoft Edge の開発」](/microsoft-edge/extensions-chromium/enterprise/auto-update)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7042e-133">For more information, see [Auto-update extensions in Microsoft Edge - Microsoft Edge Development](/microsoft-edge/extensions-chromium/enterprise/auto-update).</span></span>

8. <span data-ttu-id="7042e-134">完了済み XML ファイルを、ダウンロードした元の場所にアップロードして、その URL をメモします。</span><span class="sxs-lookup"><span data-stu-id="7042e-134">Upload the completed XML file to a location where it can be downloaded from, noting the URL.</span></span> <span data-ttu-id="7042e-135">この URL は、グループ ポリシーを使用して拡張機能をインストールするときに必要です。</span><span class="sxs-lookup"><span data-stu-id="7042e-135">This URL will be needed when you install the extension using a group policy.</span></span> <span data-ttu-id="7042e-136">[「プライベート ホスト拡張機能の配布」](#distribute-a-privately-hosted-extension)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7042e-136">See [Distribute a privately hosted extension](#distribute-a-privately-hosted-extension).</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="7042e-137">拡張機能のホスティング場所は認証を必要としません。</span><span class="sxs-lookup"><span data-stu-id="7042e-137">The hosting location for the extension doesn’t need authentication.</span></span> <span data-ttu-id="7042e-138">ユーザー デバイスを使用する場所にユーザー デバイスがアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7042e-138">It needs to be accessible by user devices wherever they might be used.</span></span>

## <a name="publish-updates-to-an-extension"></a><span data-ttu-id="7042e-139">拡張機能への更新プログラムの発行</span><span class="sxs-lookup"><span data-stu-id="7042e-139">Publish updates to an extension</span></span>

<span data-ttu-id="7042e-140">更新された拡張機能を変更してテストした後、公開できます。</span><span class="sxs-lookup"><span data-stu-id="7042e-140">After you change and test the updated extension you can publish it.</span></span> <span data-ttu-id="7042e-141">更新プログラムを発行するためのガイドとして、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="7042e-141">Use the following steps as a guide for publishing an update.</span></span>

1. <span data-ttu-id="7042e-142">次の構文: `"version":"versionString"`を使用して、拡張機能のマニフェスト..JSON ファイルのバージョン番号を高い数値に変更します。</span><span class="sxs-lookup"><span data-stu-id="7042e-142">Change the version number in your extension's manifest.JSON file to a higher number using the following syntax: `"version":"versionString"`.</span></span> <span data-ttu-id="7042e-143">"version":"1.0" の場合は、"version":"1.1" または "1.0" より大きい数値に更新できます。</span><span class="sxs-lookup"><span data-stu-id="7042e-143">If the "version":"1.0", then you can update to "version":"1.1" or any number higher than "1.0".</span></span>
2. <span data-ttu-id="7042e-144">前の手順でマニフェスト ファイルに格納した番号と一致する XML ファイル`<updatecheck>` の "version" を更新します。</span><span class="sxs-lookup"><span data-stu-id="7042e-144">Update the "version" of `<updatecheck>` in the XML file to match the number that you put in the manifest file in the previous step.</span></span> <span data-ttu-id="7042e-145">次に、例を示します。</span><span class="sxs-lookup"><span data-stu-id="7042e-145">For example:</span></span><br>`<updatecheck codebase='https://app.somecompany.com/extensionfolder/helloworld.crx' version='1.1' />`
3. <span data-ttu-id="7042e-146">新しい変更を含む CRX ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7042e-146">Create a CRX file that includes the new changes.</span></span> <span data-ttu-id="7042e-147">*[edge://extensions]* に移動して、**[開発者モード]** を有効にします。</span><span class="sxs-lookup"><span data-stu-id="7042e-147">Go to *edge://extensions* and enable **Developer mode**.</span></span>
4. <span data-ttu-id="7042e-148">**[拡張機能のパック]** をクリックし、拡張ソースのディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="7042e-148">Click **Pack extension** and go to the directory for the extension source.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="7042e-149">CRX ファイルが初めて作成されたときに、生成され保存されたのと同じ PEM ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="7042e-149">Use the same PEM file that was generated and saved the first time the CRX file was created.</span></span> <span data-ttu-id="7042e-150">同じ PEM ファイルを使用しない場合は、拡張機能のアプリ ID が変更され、更新プログラムは新しい拡張機能として扱われます。</span><span class="sxs-lookup"><span data-stu-id="7042e-150">If you don't use the same PEM file the app ID of the extension will change and the update will be treated as a new extension.</span></span>

5. <span data-ttu-id="7042e-151">CRX ファイルを [拡張機能] ウィンドウにドラッグ アンド ドロップし、読み込まれることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7042e-151">Drag and drop the CRX file into the extensions window and verify that it loads.</span></span>
6. <span data-ttu-id="7042e-152">更新された拡張機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="7042e-152">Test the updated extension.</span></span>
7. <span data-ttu-id="7042e-153">古い CRX ファイルと XML ファイルを、更新された拡張子の新しいファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="7042e-153">Replace the old CRX file and XML file with the new files for the updated extension.</span></span>

<span data-ttu-id="7042e-154">拡張機能の変更は、次のポリシー同期サイクル中に取得されます。</span><span class="sxs-lookup"><span data-stu-id="7042e-154">The extension's changes will be picked up during the next policy sync cycle.</span></span> <span data-ttu-id="7042e-155">拡張機能の更新の詳細については、[「URLのアップデート」](/microsoft-edge/extensions-chromium/enterprise/auto-update#update-url) および [「マニフェストのアップデート」](/microsoft-edge/extensions-chromium/enterprise/auto-update#updated-manifest)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7042e-155">For more information about updating extensions, see: [Update URL](/microsoft-edge/extensions-chromium/enterprise/auto-update#update-url) and [Update manifest](/microsoft-edge/extensions-chromium/enterprise/auto-update#updated-manifest).</span></span>

## <a name="distribute-a-privately-hosted-extension"></a><span data-ttu-id="7042e-156">プライベート ホスト拡張機能の配布</span><span class="sxs-lookup"><span data-stu-id="7042e-156">Distribute a privately hosted extension</span></span>

<span data-ttu-id="7042e-157">CRX ファイルがホストされている場所のリンクを共有し、ユーザーがブラウザーで URL を入力するとすぐに拡張機能がダウンロードおよびインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7042e-157">You can share the link of the location where the CRX file is hosted, and as soon as users enter the URL in their browser the extension will be downloaded and installed.</span></span> <span data-ttu-id="7042e-158">ユーザーは、[edge://extensions] ページから拡張機能を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="7042e-158">Users can enable the extension from the edge://extensions page.</span></span> <span data-ttu-id="7042e-159">ユーザーがセルフホスト型拡張機能をインストールするには、拡張機能 CRX ID を [[ExtensionInstallAllowList ]](/deployedge/microsoft-edge-policies#extensioninstallallowlist)ポリシーに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7042e-159">To allow users to install self-hosted extensions, you need to add the extension CRX IDs to the [ExtensionInstallAllowList](/deployedge/microsoft-edge-policies#extensioninstallallowlist) policy.</span></span>

<span data-ttu-id="7042e-160">または、グループ ポリシー [ExtensionInstallForceList](/deployedge/microsoft-edge-manage-extensions-policies#force-install-an-extension) を使用して、ユーザーのデバイスに拡張機能を強制的にインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7042e-160">Alternatively, you can use group policy [ExtensionInstallForceList](/deployedge/microsoft-edge-manage-extensions-policies#force-install-an-extension) to Force-install an extension on your users’ devices.</span></span>

<span data-ttu-id="7042e-161">これらのポリシーは、選択したユーザー、デバイス、または両方に適用できます。</span><span class="sxs-lookup"><span data-stu-id="7042e-161">You can apply these policies to your selected users, devices, or both.</span></span> <span data-ttu-id="7042e-162">ポリシーの更新は即座に行うのではなく、ポリシー設定を有効にするには時間がかかることを覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="7042e-162">Remember though that policy updates are not instantaneous, and it will take time for the policy settings to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="7042e-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="7042e-163">See also</span></span>

- [<span data-ttu-id="7042e-164">エンタープライズの Microsoft Edge 拡張機能を管理する</span><span class="sxs-lookup"><span data-stu-id="7042e-164">Manage Microsoft Edge extensions in the enterprise</span></span>](microsoft-edge-manage-extensions.md)
- [<span data-ttu-id="7042e-165">グループ ポリシーを使用して Microsoft Edge の拡張機能を使用する</span><span class="sxs-lookup"><span data-stu-id="7042e-165">Use group policies to manage Microsoft Edge extensions</span></span>](microsoft-edge-manage-extensions-policies.md)
- [<span data-ttu-id="7042e-166">ExtensionSettings ポリシーの詳細なガイド</span><span class="sxs-lookup"><span data-stu-id="7042e-166">Detailed guide to the ExtensionSettings policy</span></span>](microsoft-edge-manage-extensions-ref-guide.md)
- [<span data-ttu-id="7042e-167">Microsoft Edge の拡張機能についてのよくある質問</span><span class="sxs-lookup"><span data-stu-id="7042e-167">FAQ for Microsoft Edge Extensions</span></span>](microsoft-edge-manage-extensions-faq.md)
- [<span data-ttu-id="7042e-168">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="7042e-168">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
