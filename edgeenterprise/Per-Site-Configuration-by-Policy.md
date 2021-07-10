---
title: 'ポリシーによるサイトごとの構成 '
ms.author: collw
author: AndreaLBarr
manager: laurawi
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 'ポリシーによるサイトごとの構成 '
ms.openlocfilehash: 4f1bf9a421f0098ba8105e78f77ac4af62530239
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641693"
---
# <a name="persite-configuration-by-policy"></a><span data-ttu-id="60979-103">ポリシーによるサイトごとの構成</span><span class="sxs-lookup"><span data-stu-id="60979-103">PerSite Configuration by Policy</span></span>

## <a name="introduction-browsers-as-decision-makers"></a><span data-ttu-id="60979-104">概要: 意思決定者としてのブラウザー</span><span class="sxs-lookup"><span data-stu-id="60979-104">Introduction: Browsers as Decision Makers</span></span>

<span data-ttu-id="60979-105">すべてのページ読み込みの一環として、ブラウザーは多くの決定をします — 特定の API を利用できるようにする必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="60979-105">As a part of every page load, browsers make many decisions — should a particular API be available?</span></span> <span data-ttu-id="60979-106">リソースの負荷を許可する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="60979-106">Should a resource load be permitted?</span></span> <span data-ttu-id="60979-107">スクリプトの実行を許可する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="60979-107">Should script be allowed to run?</span></span> <span data-ttu-id="60979-108">リストは長いです。</span><span class="sxs-lookup"><span data-stu-id="60979-108">The list is long.</span></span>

<span data-ttu-id="60979-109">ほとんどの場合、決定は、ユーザー設定と決定が行われたページの URL の 2 つの入力によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="60979-109">In most cases, decisions are governed by two inputs: a user setting, and the URL of the page for which the decision is being made.</span></span>

<span data-ttu-id="60979-110">従来の Internet Explorer Web プラットフォームでは、これらの各決定は  [URLAction](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537178%28v%3dvs.85%29) と呼ばれ、インターネット コントロール パネル内の Enterprise グループ ポリシーとユーザー設定は、ブラウザーが各決定を処理する方法を制御しました。</span><span class="sxs-lookup"><span data-stu-id="60979-110">In the legacy Internet Explorer web platform, each of these decisions was called an [URLAction](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537178%28v%3dvs.85%29), and Enterprise Group Policy and user settings inside the Internet Control Panel controlled how the browser would handle each decision.</span></span>  

<span data-ttu-id="60979-111">Microsoft Edge では、サイトごとのアクセス許可の大部分は、ワイルド カードのサポートが制限された単純な構文を使用して表現される設定とポリシーによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="60979-111">In the Microsoft Edge, most per-site permissions are controlled by settings and policies expressed using a simple syntax with limited wild carding support.</span></span> <span data-ttu-id="60979-112">Windows セキュリティ ゾーンは、構成の決定の数が少ない場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="60979-112">Windows Security Zones are still used only for a small number of configuration decisions.</span></span>

## <a name="background-windows-security-zones"></a><span data-ttu-id="60979-113">背景: Windows セキュリティ ゾーン</span><span class="sxs-lookup"><span data-stu-id="60979-113">Background: Windows Security Zones</span></span>

<span data-ttu-id="60979-114">ユーザーまたは管理者の構成を簡素化するために、従来のプラットフォームはサイトを 5 つの異なる **セキュリティ ゾーン** (ローカル コンピューター、ローカル イントラネット、信頼済み、インターネット、制限付きサイト) に分類しました。</span><span class="sxs-lookup"><span data-stu-id="60979-114">To simplify configuration for the user or their administrator, the legacy platform classified sites into five different **Security Zones:** Local Machine, Local Intranet, Trusted, Internet, and Restricted Sites.</span></span>

<span data-ttu-id="60979-115">決定を下す場合、ブラウザーは最初に Web サイトをゾーンにマップしてから、そのゾーンの URLAction の設定を参照して、実行する操作を決定します。</span><span class="sxs-lookup"><span data-stu-id="60979-115">When making a decision, the browser would first map the website to a Zone, then consult the setting for that URLAction for that Zone to decide what to do.</span></span> <span data-ttu-id="60979-116">"イントラネットからの認証の課題を自動的に満たす" のような妥当な既定値は、ほとんどのユーザーが既定から設定を変更する必要がなかったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="60979-116">Reasonable defaults like “Automatically satisfy authentication challenges from my Intranet” meant that most users never needed to change any settings away from their defaults.</span></span>

<span data-ttu-id="60979-117">ユーザーは、インターネット コントロール パネルを使用して、特定のサイトをゾーンに割り当て、各ゾーンのアクセス許可の結果を構成できます。</span><span class="sxs-lookup"><span data-stu-id="60979-117">Users can use the Internet Control Panel to assign specific sites to Zones and to configure the permission results for each zone.</span></span> <span data-ttu-id="60979-118">管理環境では、管理者はグループ ポリシーを使用して、特定のサイトを ("サイトとゾーンの割り当て一覧" ポリシー経由で) ゾーンに割り当て、ゾーンごとに URLActions の設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="60979-118">In managed environments, administrators can use Group Policy to assign specific sites to Zones (via “Site to Zone Assignment List” policy) and specify the settings for URLActions on a per-zone basis.</span></span> <span data-ttu-id="60979-119">手動による管理またはユーザーによるゾーンへのサイトの割り当て以外に、追加のヒューリスティックが [サイトをローカル イントラネット ゾーンに割り当てる](/archive/blogs/ieinternals/the-intranet-zone)可能性があります。</span><span class="sxs-lookup"><span data-stu-id="60979-119">Beyond manual administrative or user assignment of sites to Zones, additional heuristics could [assign sites to the Local Intranet Zone](/archive/blogs/ieinternals/the-intranet-zone).</span></span> <span data-ttu-id="60979-120">特に、ドットレス ホスト名 (例: `http://payroll`) がイントラネット ゾーンに割り当て済みです。</span><span class="sxs-lookup"><span data-stu-id="60979-120">In particular, dotless host names (e.g. `http://payroll`) were assigned to the Intranet Zone.</span></span> <span data-ttu-id="60979-121">プロキシ構成スクリプトが使用されている場合、プロキシをバイパスするように構成されたサイトはイントラネット ゾーンにマップされます。</span><span class="sxs-lookup"><span data-stu-id="60979-121">If a Proxy Configuration script was used, any sites configured to bypass the proxy would be mapped to the Intranet Zone.</span></span>

<span data-ttu-id="60979-122">Microsoft Edge 従来版は、いくつかの単純化された変更を加えて、Internet Explorer の前身からゾーン アーキテクチャを継承しました。</span><span class="sxs-lookup"><span data-stu-id="60979-122">Microsoft Edge Legacy inherited the Zones architecture from its Internet Explorer predecessor with a few simplifying changes:</span></span>

- <span data-ttu-id="60979-123">Windows の 5 つの組み込みゾーンは、インターネット (インターネット)、信頼済み (イントラネット + 信頼済み)、およびローカル コンピューターの 3 つに統合されました。</span><span class="sxs-lookup"><span data-stu-id="60979-123">Windows’ five built-in Zones were collapsed to three: Internet (Internet), Trusted (Intranet+Trusted), and Local Computer.</span></span> <span data-ttu-id="60979-124">制限付きサイト ゾーンは削除されました。</span><span class="sxs-lookup"><span data-stu-id="60979-124">The Restricted Sites Zone was removed.</span></span>

- <span data-ttu-id="60979-125">ゾーンから URLAction へのマッピングはブラウザーにハードコードされ、インターネット コントロール パネルのグループ ポリシーと設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="60979-125">Zone to URLAction mappings were hardcoded into the browser, ignoring Group Policies and settings in the Internet Control Panel.</span></span>

## <a name="per-site-permissions-in-the-microsoft-edge"></a><span data-ttu-id="60979-126">Microsoft Edge でのサイトごとのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="60979-126">Per-Site Permissions in the Microsoft Edge</span></span>

<span data-ttu-id="60979-127">以前のものとは異なり、新しい Microsoft Edge では Windows セキュリティ ゾーンの使用が非常に制限されています。</span><span class="sxs-lookup"><span data-stu-id="60979-127">Unlike its predecessors, the new Microsoft Edge makes very limited use of Windows Security Zones.</span></span> <span data-ttu-id="60979-128">代わりに、 [ポリシー](/deployedge/microsoft-edge-policies)を介して管理者にサイトごとの構成を提供するほとんどのアクセス許可と機能は、 [URL フィルター形式](/DeployEdge/edge-learnmmore-url-list-filter%20format)のルールの一覧に依存します。</span><span class="sxs-lookup"><span data-stu-id="60979-128">Instead, most permissions and features that offer administrators per-site configuration via [policy](/deployedge/microsoft-edge-policies) rely on lists of rules in the [URL Filter Format](/DeployEdge/edge-learnmmore-url-list-filter%20format).</span></span>

<span data-ttu-id="60979-129">エンド ユーザーが開くと <code>edge://settings/content/siteDetails?site=https://example.com</code>、さまざまなアクセス許可の構成スイッチとリストの長い一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="60979-129">When end-users open <code>edge://settings/content/siteDetails?site=https://example.com</code>, they’ll find a long list of configuration switches and lists for various permissions.</span></span> <span data-ttu-id="60979-130">ユーザーが [設定] ページを直接使用することはめったにありません。代わりに、 **[ページ情報]**  ドロップダウン (アドレス バーのロック アイコンをクリックすると表示されます) で、またはアドレス バーの右端にあるさまざまなプロンプトやボタンで、さまざまなウィジェットやトグルを使用して閲覧中に選択を行います。</span><span class="sxs-lookup"><span data-stu-id="60979-130">Users rarely use the Settings Page directly, instead making choices while browsing using various widgets and toggles in the **Page Info** dropdown (which appears when you click the lock icon in the address bar) or via various prompts or buttons at the right-edge of the address bar.</span></span>

<span data-ttu-id="60979-131">企業は、グループ ポリシーを使用して、ブラウザーの動作を制御する個々のポリシーのサイト リストをプロビジョニングできます。</span><span class="sxs-lookup"><span data-stu-id="60979-131">Enterprises can use Group Policy to provision site lists for individual policies that control the browser’s behavior.</span></span> <span data-ttu-id="60979-132">これらのポリシーを見つけるには、 [Microsoft Edge グループ ポリシーのドキュメント](/deployedge/microsoft-edge-policies) を開き、 **ForUrls**  を検索して、読み込まれたサイトの URL に基づいて動作を許可およびブロックするポリシーを検索します。</span><span class="sxs-lookup"><span data-stu-id="60979-132">To find these policies, simply open the [Microsoft Edge Group Policy documentation](/deployedge/microsoft-edge-policies) and search for **ForUrls** to find the policies that allow and block behavior based on the loaded site’s URL.</span></span> <span data-ttu-id="60979-133">関連する設定のほとんどは、 [[コンテンツ設定のグループ ポリシー]](/deployedge/microsoft-edge-policies#content-settings) セクションに一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="60979-133">Most of the relevant settings are listed within the [Group Policy for Content Settings](/deployedge/microsoft-edge-policies#content-settings) section.</span></span>

<span data-ttu-id="60979-134">特定の設定の既定の動作を制御するポリシー (名前に  **Default** が含まれる) も多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="60979-134">There are also a number of policies (whose names contain **Default**) that control the default behavior for a given setting.</span></span>

<span data-ttu-id="60979-135">設定の多くは非常にあいまい (WebSerial、WebMIDI) であり、既定 (Images) から設定を変更する理由がないことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="60979-135">Many of the settings are very obscure (WebSerial, WebMIDI) and there’s very often no reason to change a setting away from the default (Images).</span></span>

## <a name="common-questions"></a><span data-ttu-id="60979-136">一般的な質問</span><span class="sxs-lookup"><span data-stu-id="60979-136">Common Questions</span></span>

## <a name="q-can-the-url-filter-format-match-on-a-sites-ip-address"></a><span data-ttu-id="60979-137">Q: URL フィルター形式はサイトの IP アドレスと一致しますか?</span><span class="sxs-lookup"><span data-stu-id="60979-137">Q: Can the URL Filter Format match on a site’s IP address?</span></span>

<span data-ttu-id="60979-138">いいえ、この形式では、許可リストとブロック リストの IP 範囲の指定はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="60979-138">No, the format does not support specifying an IP-range for allow and block lists.</span></span> <span data-ttu-id="60979-139">個々の IP  **リテラル**の指定はサポートされますが、そのようなルールは、ユーザーが上記のリテラル (例:  <http://127.0.0.1/>) を使用してサイトに移動した場合にのみ尊重されます。</span><span class="sxs-lookup"><span data-stu-id="60979-139">It does support specification of individual IP **literals**, but such rules are only respected if the user navigates to the site using said literal (e.g. <http://127.0.0.1/>).</span></span> <span data-ttu-id="60979-140">ホスト名が使用されている場合 (<http://localhost>)、ホストの解決済み IP がフィルターにリストされた IP と一致していても、IP リテラル ルールは尊重されません。</span><span class="sxs-lookup"><span data-stu-id="60979-140">If a hostname is used (<http://localhost>), the IP Literal rule will not be respected even though the resolved IP of the host matches the filter-listed IP.</span></span>

## <a name="q-can-url-filters-matchjustdotless-host-names"></a><span data-ttu-id="60979-141">Q: URL フィルターはドットレス ホスト名と一致しますか?</span><span class="sxs-lookup"><span data-stu-id="60979-141">Q: Can URL Filters match just dotless host names?</span></span>

<span data-ttu-id="60979-142">いいえ、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="60979-142">No.</span></span> <span data-ttu-id="60979-143">必要なホスト名 (`https://payroll`、`https://stock`、`https://who` など) を個別にリストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="60979-143">You must individually list each desired hostname, e.g. (`https://payroll`, `https://stock`, `https://who`, etc).</span></span>

<span data-ttu-id="60979-144">ホスト名が次の形式になるようにイントラネットを構造化するのに十分な前向きな考えを持っていた場合:</span><span class="sxs-lookup"><span data-stu-id="60979-144">If you were forward-thinking enough to structure your intranet such that your host names are of the form:</span></span>

- <div style="display: inline">`https://payroll.contoso-intranet.com`</div>

- <div style="display: inline">`https://timecard.contoso-intranet.com`</div>

- <div style="display: inline">`https://sharepoint.contoso-intranet.com`</div>

<span data-ttu-id="60979-145">おめでとうございます。ベスト プラクティスを実装しました。</span><span class="sxs-lookup"><span data-stu-id="60979-145">Congratulations, you’ve implemented a best practice.</span></span> <span data-ttu-id="60979-146">\**_.contoso-intranet.com_* エントリを使用して各ポリシーを構成すると、   イントラネット全体がオプトインされます。</span><span class="sxs-lookup"><span data-stu-id="60979-146">You can configure each desired policy with a \**_.contoso-intranet.com_* entry and your entire Intranet will be opted in.</span></span>

## <a name="use-of-security-zones-inthe-microsoft-edge"></a><span data-ttu-id="60979-147">Microsoft Edge でのセキュリティ ゾーンの使用</span><span class="sxs-lookup"><span data-stu-id="60979-147">Use of Security Zones in the Microsoft Edge</span></span>

<span data-ttu-id="60979-148">Microsoft Edge は主に URL フィルター形式を使用する個々のポリシーに依存しますが、これまでゾーン構成に依存してきた企業内での展開を簡素化するために、既定で Windows のセキュリティ ゾーンを少数の場所で引き続き使用します。</span><span class="sxs-lookup"><span data-stu-id="60979-148">While Microsoft Edge mostly relies upon individual policies using the URL Filter format, it continues to use Windows’ Security Zones by default in a small number of places in order to simplify deployment within Enterprises that have historically relied upon Zones configuration.</span></span> <span data-ttu-id="60979-149">次の動作は、ゾーン ポリシーによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="60979-149">The following behaviors are controlled by Zone policy:</span></span>

1. <span data-ttu-id="60979-150">Windows 統合認証 (Kerberos/NTLM) 資格情報を自動的に解放するかどうかを決定する場合</span><span class="sxs-lookup"><span data-stu-id="60979-150">When deciding whether to release Windows Integrated Authentication (Kerberos/NTLM) credentials automatically</span></span>

2. <span data-ttu-id="60979-151">ファイルのダウンロードを処理する方法を決定する場合</span><span class="sxs-lookup"><span data-stu-id="60979-151">When deciding how to handle File Downloads</span></span>

3. <span data-ttu-id="60979-152">Internet Explorer モードの場合</span><span class="sxs-lookup"><span data-stu-id="60979-152">For Internet Explorer Mode</span></span>

## <a name="credential-release"></a><span data-ttu-id="60979-153">資格情報のリリース</span><span class="sxs-lookup"><span data-stu-id="60979-153">Credential Release</span></span>

<span data-ttu-id="60979-154">既定では、Microsoft Edge は URLACTION_CREDENTIALS_USE を評価して Windows 統合認証が自動的に使用されるかどうかを判断するか、代わりにユーザーが手動認証プロンプトを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60979-154">By default, Microsoft Edge will evaluate URLACTION_CREDENTIALS_USE to decide whether Windows Integrated Authentication is used automatically, or the user should instead see a manual authentication prompt.</span></span> <span data-ttu-id="60979-155">[AuthServerAllowlist サイト リスト ポリシー](/deployedge/microsoft-edge-policies#authserverallowlist)を構成すると、ゾーン ポリシーが参照されなくなります。</span><span class="sxs-lookup"><span data-stu-id="60979-155">Configuring an [AuthServerAllowlist site list policy](/deployedge/microsoft-edge-policies#authserverallowlist) will prevent Zone Policy from being consulted.</span></span>

## <a name="file-downloads"></a><span data-ttu-id="60979-156">ファイルのダウンロード</span><span class="sxs-lookup"><span data-stu-id="60979-156">File Downloads</span></span>

<span data-ttu-id="60979-157">ファイルのダウンロードの発生元に関する証拠 (いわゆる "[Web のマーク](https://textslashplain.com/2016/04/04/downloads-and-the-mark-of-the-web/)") は、インターネット ゾーンからダウンロードされたファイルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="60979-157">Evidence about the origins of a file download (the so-called “[Mark of the Web](https://textslashplain.com/2016/04/04/downloads-and-the-mark-of-the-web/) is recorded for files downloaded from the Internet Zone.</span></span> <span data-ttu-id="60979-158">他のアプリケーション (Windows シェル、Microsoft Office など) は、ファイルの処理方法を決定する際に、この発生元の証拠を考慮に入れる場合があります。</span><span class="sxs-lookup"><span data-stu-id="60979-158">Other applications (e.g. the Windows Shell, Microsoft Office, etc) may take this origin evidence into account when deciding how to handle a file.</span></span>

<span data-ttu-id="60979-159">Windows セキュリティ ゾーン ポリシーが [アプリケーションの起動と安全でないファイルの起動] 設定を無効にするように構成されている場合、Microsoft Edge ダウンロード マネージャーは、そのゾーン内のサイトからのファイルのダウンロードをブロックします。"ダウンロードできませんでした - ブロックされました" というメモが付きます。</span><span class="sxs-lookup"><span data-stu-id="60979-159">If the Windows Security Zone policy is configured to Disable the setting Launching applications and unsafe files, the Microsoft Edge download manager will block file downloads from sites in that Zone with a note: “Couldn’t download – Blocked.”</span></span>  

## <a name="ie-mode"></a><span data-ttu-id="60979-160">IE モード</span><span class="sxs-lookup"><span data-stu-id="60979-160">IE mode</span></span>

<span data-ttu-id="60979-161">IE モードは、 [すべてのイントラネット サイトを IE モードで開く](/deployedge/edge-ie-mode#configure-all-intranet-sites)ように構成できます。</span><span class="sxs-lookup"><span data-stu-id="60979-161">IE mode can be configured to [open all Intranet sites in IE mode](/deployedge/edge-ie-mode#configure-all-intranet-sites).</span></span> <span data-ttu-id="60979-162">この構成では、Edge は IE モードで開くかどうかを決定するときに URL のゾーンを評価します。</span><span class="sxs-lookup"><span data-stu-id="60979-162">When in this configuration, Edge evaluates the Zone of a URL when deciding whether or not it should open in IE mode.</span></span> <span data-ttu-id="60979-163">この最初の決定を超えて、IE モード タブは実際に Internet Explorer を実行しており、その結果、Internet Explorer 自体が行ったように、すべてのポリシー決定のゾーン設定を評価します。</span><span class="sxs-lookup"><span data-stu-id="60979-163">Beyond this initial decision, IE mode tabs are really running Internet Explorer, and as a consequence they evaluate Zones settings for every policy decision just as Internet Explorer itself did.</span></span>

## <a name="summary"></a><span data-ttu-id="60979-164">要約</span><span class="sxs-lookup"><span data-stu-id="60979-164">Summary</span></span>

<span data-ttu-id="60979-165">ほとんどの場合、Microsoft Edge の設定は既定値のままにしておくことができます。</span><span class="sxs-lookup"><span data-stu-id="60979-165">In most cases, Microsoft Edge settings can be left at their defaults.</span></span> <span data-ttu-id="60979-166">すべてのサイトまたは特定のサイトの既定値を変更する管理者は、適切なグループ ポリシーを使用してサイト一覧または既定の動作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="60979-166">Administrators who wish to change the defaults for all sites or specific sites can use the appropriate Group Policies to specify Site Lists or default behaviors.</span></span> <span data-ttu-id="60979-167">いくつかのケース (資格情報の解放、ファイルのダウンロード、IE モード) では、管理者は Windows セキュリティ ゾーンの設定を構成することで引き続き動作を制御します。</span><span class="sxs-lookup"><span data-stu-id="60979-167">In a handful of cases (credential release, file download, and IE mode), administrators will continue to control behavior by configuring Windows Security Zones settings.</span></span>
