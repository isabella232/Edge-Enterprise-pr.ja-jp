---
title: IE モードに関する FAQ
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 12/21/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: IE モードの Microsoft Edge に関する FAQ とトラブルシューティング
ms.openlocfilehash: 62bf8afc5ac908e18d2f503fa9248a19f78fd6f6
ms.sourcegitcommit: 306582403d4272831bcac390154c7cc7041a9b7e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2020
ms.locfileid: "11238174"
---
# <span data-ttu-id="3f3e5-103">IE モードに関する FAQ</span><span class="sxs-lookup"><span data-stu-id="3f3e5-103">IE mode FAQ</span></span>

<span data-ttu-id="3f3e5-104">この記事では、Microsoft Edge (バージョン 77 以降) に関するトラブルシューティングのヒントと FAQ を示します。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-104">This article provides troubleshooting tips and an FAQ for Microsoft Edge (version 77 or later).</span></span>

> [!NOTE]
> <span data-ttu-id="3f3e5-105">この記事は、Microsoft Edge version 77 (**Stable**、**Beta**、および **Dev** チャネル) 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-105">This article applies to Microsoft Edge **Stable**, **Beta** and **Dev** Channels, version 77 or later.</span></span>

## <span data-ttu-id="3f3e5-106">IE モードのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3f3e5-106">Troubleshoot IE mode</span></span>

<span data-ttu-id="3f3e5-107">IE モードの問題を診断して解決するには、このセクションの情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-107">Use the information in this section to diagnose and fix IE mode problems.</span></span>

### <span data-ttu-id="3f3e5-108">Internet Explorer モードの診断情報</span><span class="sxs-lookup"><span data-stu-id="3f3e5-108">Internet Explorer mode diagnostic information</span></span>

<span data-ttu-id="3f3e5-109">Internet Explorer モードの診断情報は、[Microsoft Edge の互換性] タブに表示されます。このタブを開くには、*edge://compat/iediagnostic* に移動します。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-109">You can get Internet Explorer mode diagnostic information on the Microsoft Edge Compatibility tab. To open this tab, go to *edge://compat/iediagnostic*.</span></span> <span data-ttu-id="3f3e5-110">このページには、診断メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-110">This page may show diagnostic messages.</span></span> <span data-ttu-id="3f3e5-111">このページでは、以下のカテゴリの構成情報も提供します。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-111">This page also provides configuration information for the following categories:</span></span>

- <span data-ttu-id="3f3e5-112">**レジストリ キーの確認**。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-112">**Registry key check**.</span></span> <span data-ttu-id="3f3e5-113">(確認が失敗した場合にのみ表示されます)。Internet Explorer 統合が、レジストリで正しく設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-113">(Displayed only if the check fails.) Checks to see if Internet Explorer integration is set up correctly in the registry.</span></span> <span data-ttu-id="3f3e5-114">設定されていない場合、ユーザーは **[修正]** をクリックして、この問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-114">If not, the user can click **Fix it** to resolve the problem.</span></span>
- <span data-ttu-id="3f3e5-115">**Internet Explorer モード**。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-115">**Internet Explorer mode**.</span></span> <span data-ttu-id="3f3e5-116">構成と OS に基づいて使用される API のバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-116">Shows the API version that's used, based on the configuration and OS.</span></span> <span data-ttu-id="3f3e5-117">問題がある場合、ユーザーは **Windows Update** のインストールを求められることがあります。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-117">If there's a problem, the user may be prompted to install a **Windows Update**.</span></span>
- <span data-ttu-id="3f3e5-118">**Internet Explorer モードの設定**。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-118">**Internet Explorer mode setting**.</span></span> <span data-ttu-id="3f3e5-119">Internet Explorer モードが有効かどうか、およびその構成方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-119">Shows whether Internet Explorer mode is enabled, and how it's configured.</span></span>
- <span data-ttu-id="3f3e5-120">**コマンド ライン**。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-120">**Command line**.</span></span> <span data-ttu-id="3f3e5-121">Microsoft Edge を開始するために使用されるコマンド ライン文字列とスイッチを示します。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-121">Shows the command line string and switches used to start Microsoft Edge.</span></span>
- <span data-ttu-id="3f3e5-122">**グループ ポリシー設定**。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-122">**Group policy settings**.</span></span> <span data-ttu-id="3f3e5-123">グループ ポリシーを使用して IE モードが構成されているかどうか、および適用されているポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-123">Shows whether IE mode is configured using group policies, and the policies that are applied.</span></span>

### <span data-ttu-id="3f3e5-124">エラー メッセージ: 「このページを Internet Explorer モードで開くには、管理者特権で Microsoft Edge を再インストールしてください。」</span><span class="sxs-lookup"><span data-stu-id="3f3e5-124">Error message: "To open this page in Internet Explorer mode, reinstall Microsoft Edge with administrator privileges."</span></span>

<span data-ttu-id="3f3e5-125">必要な Windows Update がすべてインストールされていない場合、このエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-125">You may see this error if you don't have all required Windows Updates.</span></span> <span data-ttu-id="3f3e5-126">必要なバージョンの Windows および Microsoft Edge については、「[IE モードの概要](https://docs.microsoft.com/deployedge/edge-ie-mode)」に記載されている前提条件をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-126">See the prerequisites listed in [About IE mode](https://docs.microsoft.com/deployedge/edge-ie-mode) for the required versions of Windows and Microsoft Edge.</span></span>

<span data-ttu-id="3f3e5-127">必要な Windows Update がすべて既にインストールされている場合、このエラーが表示されるのは以下の理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-127">If you've already installed all required Windows Updates, you may see this error if:</span></span>

- <span data-ttu-id="3f3e5-128">Canary チャネルを使用しています。これは、既定でユーザー レベルでインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-128">You're using the Canary channel, which is installed at the user level by default.</span></span>
- <span data-ttu-id="3f3e5-129">Stable、Beta、Dev のいずれかのチャネルを使用しているが、昇格のインストール中に昇格のプロンプトがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-129">You're using the Stable, Beta, or Dev channel, but when prompted for elevation when installing the elevation was canceled.</span></span> <span data-ttu-id="3f3e5-130">昇格のプロンプトをキャンセルすると、ユーザー レベルでインストールは続行されます。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-130">When you cancel the elevation prompt, the installation will continue at the user level.</span></span>
- <span data-ttu-id="3f3e5-131">Windows の機能で Internet Explorer 11 が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-131">Internet Explorer 11 has been disabled in Windows Features.</span></span>

<span data-ttu-id="3f3e5-132">考えられる解決方法:</span><span class="sxs-lookup"><span data-stu-id="3f3e5-132">Possible solutions:</span></span>

- <span data-ttu-id="3f3e5-133">任意のチャネルのインストーラーをシステム レベルで実行します: `installer.exe --system-level`</span><span class="sxs-lookup"><span data-stu-id="3f3e5-133">Run the installer for any channel at the system level: `installer.exe --system-level`.</span></span>
- <span data-ttu-id="3f3e5-134">Windows の機能で Internet Explorer 11 を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-134">Enable Internet Explorer 11 in Windows Features.</span></span>

<span data-ttu-id="3f3e5-135">Microsoft Edge がシステム レベルでインストールされていることを確認するには、Microsoft Edge アドレス バーに「edge://version」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-135">To check if Microsoft Edge is installed at the systems level, type "edge://version" in the Microsoft Edge address bar.</span></span> <span data-ttu-id="3f3e5-136">[実行可能ファイルのパス] に、*C:\Program Files...* から始まるパスが表示されます。これは、システム インストールであることを示します。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-136">The Executable path will show a path starting with *C:\Program Files*, which indicates a system install.</span></span> <span data-ttu-id="3f3e5-137">[実行可能ファイルのパス] が \*C:\Users\* から始まっている場合は、Microsoft Edge をアンインストールしてから、管理者特権で再インストールします。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-137">If the Executable path begins with \*C:\Users\*, uninstall and then reinstall Microsoft Edge with administrator privileges.</span></span>

### <span data-ttu-id="3f3e5-138">エラー メッセージ: 「このページを IE モードで開くには、Microsoft Edge を再起動してみてください。」</span><span class="sxs-lookup"><span data-stu-id="3f3e5-138">Error message: "To open this page in IE mode, try restarting Microsoft Edge."</span></span>

<span data-ttu-id="3f3e5-139">Internet Explorer で予期しないエラーが発生した場合、このエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-139">You may see this error if there was an unexpected error in Internet Explorer.</span></span> <span data-ttu-id="3f3e5-140">Microsoft Edge を再起動すると、通常はこのエラーが解決されます。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-140">Restarting Microsoft Edge usually fixes this error.</span></span>

### <span data-ttu-id="3f3e5-141">エラー メッセージ: 「リモート デバッグを無効にして、IE モードでこのサイトを開きます。このようにしないと、サイトが正しく動作しない可能性があります。」</span><span class="sxs-lookup"><span data-stu-id="3f3e5-141">Error message: "Turn off remote debugging to open this site in IE mode otherwise it might not work as expected."</span></span>

<span data-ttu-id="3f3e5-142">リモート デバッグ中に、IE モードで実行するように構成された Web ページに移動する場合、このエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-142">You may see this error if you're remote debugging and navigate to a web page configured to run in IE mode.</span></span> <span data-ttu-id="3f3e5-143">続行できますが、ページは Microsoft Edge を使用して表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-143">You can continue, but the page will be rendered using Microsoft Edge.</span></span>

## <span data-ttu-id="3f3e5-144">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="3f3e5-144">Frequently Asked Questions</span></span>

### <span data-ttu-id="3f3e5-145">IE モードは Internet Explorer 11 に代わる機能ですか?</span><span class="sxs-lookup"><span data-stu-id="3f3e5-145">Will IE mode replace Internet Explorer 11?</span></span>

<span data-ttu-id="3f3e5-146">Internet Explorer は、信頼できる安全なブラウザーとしてサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-146">We're committed to keeping Internet Explorer a supported, reliable, and safe browser.</span></span> <span data-ttu-id="3f3e5-147">Internet Explorer が Windows のコンポーネントであることに変わりはなく、サポートは、インストールされている OS のサポート ライフサイクルに従って行われます。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-147">Internet Explorer is still a component of Windows and follows the support lifecycle of the OS on which it's installed.</span></span> <span data-ttu-id="3f3e5-148">詳しくは、「[ライフサイクルに関する FAQ - Internet Explorer](https://support.microsoft.com/help/17454/)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-148">For details, see [Lifecycle FAQ - Internet Explorer](https://support.microsoft.com/help/17454/).</span></span> <span data-ttu-id="3f3e5-149">Microsoft による Internet Explorer のサポートと更新は続行しますが、最新の機能更新プログラムとプラットフォーム更新プログラムは Microsoft Edge のみで利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-149">While Microsoft continues to support and update Internet Explorer, the latest features and platform updates will only be available in Microsoft Edge.</span></span>

### <span data-ttu-id="3f3e5-150">IE モードで SharePoint で [エクスプローラー​​で開く] または [エクスプローラーで表示] を使用できますか?</span><span class="sxs-lookup"><span data-stu-id="3f3e5-150">Can I use "Open with Explorer" or "View in File Explorer" in SharePoint with IE mode?</span></span>

<span data-ttu-id="3f3e5-151">はい。スタンドアロン Internet Explorer 11 で動作する場合は、IE モードで動作します。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-151">Yes, if this works in standalone Internet Explorer 11 it will work in IE mode.</span></span> <span data-ttu-id="3f3e5-152">ただし、[エクスプローラー​​で開く] オプションを使用するのではなく、SharePoint 外部のファイルやフォルダを管理するための推奨アプローチは、[SharePoint ファイルの同期](https://support.office.com/en-us/article/sync-sharepoint-files-with-the-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)または [SharePoint でのファイルの移動またはコピー](https://support.office.com/en-us/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc)です。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-152">However, rather than use the Open with Explorer option, the recommended approach to managing files and folders outside of SharePoint is to [sync your SharePoint files](https://support.office.com/en-us/article/sync-sharepoint-files-with-the-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88) or [move or copy files in SharePoint](https://support.office.com/en-us/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc).</span></span>

### <span data-ttu-id="3f3e5-153">Microsoft Edge の IE モードでは、Internet Explorer 11 でサポートされている *nomerge* オプションをサポートしていますか?</span><span class="sxs-lookup"><span data-stu-id="3f3e5-153">Does IE mode on Microsoft Edge support the *nomerge* option that was supported in Internet Explorer 11?</span></span>

<span data-ttu-id="3f3e5-154">Microsoft Edge には、*nomerge* オプションをミラーリングする明示的なコマンドはありませんが、この機能性を提供する、推奨される代替方法がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-154">There is no explicit command line in Microsoft Edge to mirror the *nomerge* option, but there are a couple of alternatives that we recommend to provide this functionality.</span></span>

1. <span data-ttu-id="3f3e5-155">Microsoft Edge のプロファイルを使用すると、各プロファイルが異なる IE セッションにマッピングされ、*nomerge* オプションと同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-155">Use Profiles in Microsoft Edge - Each profile maps to a different IE session for IE mode pages, so it behaves identically to the *nomerge* option.</span></span>
2. <span data-ttu-id="3f3e5-156">`--user-data-dir=<path>` のコマンド ラインを使用しますが、各セッションには異なるパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-156">Use the `--user-data-dir=<path>` command line, but with a different path for each session.</span></span> <span data-ttu-id="3f3e5-157">必要な場合は、Microsoft Edge の起動とセッション用パスの変更を両方実行するユーティリティを作成することが可能です。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-157">If needed, you can create a utility for the user to run that both launches Microsoft Edge and changes the path for the session.</span></span>

<span data-ttu-id="3f3e5-158">上記のいずれのオプションもお客様のシナリオでうまくいかない場合は、Microsoft サポート、[TechCommunity フォーラム](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise)、[Microsoft Edge UserVoice](https://microsoftedge.uservoice.com/forums/928825-enterprise)のフィードバック チャネルのいずれかをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-158">If neither of the above options works for your scenario, reach out through one of our feedback channels:  Microsoft support, [TechCommunity forum](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise), or [Microsoft Edge UserVoice](https://microsoftedge.uservoice.com/forums/928825-enterprise).</span></span>

### <span data-ttu-id="3f3e5-159">Internet Explorer モードでリンクを Web ページとして保存できますか?</span><span class="sxs-lookup"><span data-stu-id="3f3e5-159">Can I save links as webpages in Internet Explorer mode?</span></span>
 
<span data-ttu-id="3f3e5-160">はい。Microsoft Edge のInternet Explorer モードで、コンテキスト メニューの [名前を付けて保存] オプションを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-160">Yes, you can enable the Save Target As option in the context menu for Internet Explorer mode in Microsoft Edge.</span></span> <span data-ttu-id="3f3e5-161">これを行うには、*[コンピューターの構成] > [管理用テンプレート] > [Windows コンポーネント] > [Internet Explorer]* にあるグループポリシー *"Internet Explorer モードで「名前をつけて保存」を許可する"* を構成します。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-161">To do this, configure the group policy *"Allow Save Target As in Internet Explorer mode"* located at *Computer Configuration > Administrative Templates > Windows Components > Internet Explorer*.</span></span>
<span data-ttu-id="3f3e5-162">保存メカニズムは Internet Explorer の場合と同じように動作し、ターゲットが html ファイルとして保存されている場合は、ファイルを再び開くと Microsoft Edge でページをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-162">The save mechanism works the same as it does in Internet Explorer and if the target is saved as an html file, re-opening the file will render the page in Microsoft Edge.</span></span>
 
<span data-ttu-id="3f3e5-163">この機能には、次の最小限のオペレーティング システム更新プログラムが必要です。</span><span class="sxs-lookup"><span data-stu-id="3f3e5-163">Note that this functionality requires the following minimum operating system updates:</span></span>
- <span data-ttu-id="3f3e5-164">Windows 10、バージョン 2004、Windows Server バージョン 2004、Windows 10、バージョン 20H2 : [KB4580364](https://support.microsoft.com/help/4580364/windows-10-update-kb4580364)</span><span class="sxs-lookup"><span data-stu-id="3f3e5-164">Windows 10, version 2004, Windows Server version 2004, Windows 10, version 20H2 : [KB4580364](https://support.microsoft.com/help/4580364/windows-10-update-kb4580364)</span></span>
- <span data-ttu-id="3f3e5-165">Windows 10、バージョン 1903、Windows 10、 バージョン 1909、Windows Server バージョン 1903: [KB4580386](https://support.microsoft.com/help/4580386/windows-10-update-kb4580386)</span><span class="sxs-lookup"><span data-stu-id="3f3e5-165">Windows 10, version 1903, Windows 10, version 1909, Windows Server version 1903: [KB4580386](https://support.microsoft.com/help/4580386/windows-10-update-kb4580386)</span></span>
- <span data-ttu-id="3f3e5-166">Windows 10、バージョン 1809、Windows Server バージョン 1809、Windows Server 2019: [KB4580390](https://support.microsoft.com/help/4580390/windows-10-update-kb4580390)</span><span class="sxs-lookup"><span data-stu-id="3f3e5-166">Windows 10, version 1809, Windows Server version 1809, Windows Server 2019: [KB4580390](https://support.microsoft.com/help/4580390/windows-10-update-kb4580390)</span></span>
- <span data-ttu-id="3f3e5-167">Windows 10、バージョン 1803: [KB4586785](https://support.microsoft.com/help/4586785/windows-10-update-kb4586785)</span><span class="sxs-lookup"><span data-stu-id="3f3e5-167">Windows 10, version 1803: [KB4586785](https://support.microsoft.com/help/4586785/windows-10-update-kb4586785)</span></span>
- <span data-ttu-id="3f3e5-168">Windows 10、バージョン 1607: [KB4586830](https://support.microsoft.com/help/4586830/windows-10-update-kb4586830)</span><span class="sxs-lookup"><span data-stu-id="3f3e5-168">Windows 10, version 1607: [KB4586830](https://support.microsoft.com/help/4586830/windows-10-update-kb4586830)</span></span>
- <span data-ttu-id="3f3e5-169">Windows 10、バージョン 1507: [KB4586787](https://support.microsoft.com/help/4586787/windows-10-update-kb4586787)</span><span class="sxs-lookup"><span data-stu-id="3f3e5-169">Windows 10, version 1507: [KB4586787](https://support.microsoft.com/help/4586787/windows-10-update-kb4586787)</span></span>


## <span data-ttu-id="3f3e5-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f3e5-170">See also</span></span>

- [<span data-ttu-id="3f3e5-171">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="3f3e5-171">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="3f3e5-172">IE モードの概要</span><span class="sxs-lookup"><span data-stu-id="3f3e5-172">About IE mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [<span data-ttu-id="3f3e5-173">その他のエンタープライズ モード情報</span><span class="sxs-lookup"><span data-stu-id="3f3e5-173">Additional Enterprise Mode information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
