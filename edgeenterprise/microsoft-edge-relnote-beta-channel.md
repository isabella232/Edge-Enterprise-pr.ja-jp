---
title: Beta チャネルに関する Microsoft Edge のリリース ノート
ms.author: aguta
author: AndreaLBarr
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Beta チャネルに関する Microsoft Edge のリリース ノート
ms.openlocfilehash: 1115c8d7822fef7e3784a465d5d4ddfd7b6bd6b1
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11643163"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a><span data-ttu-id="8af52-103">Microsoft Edge Beta チャネルのリリースノート</span><span class="sxs-lookup"><span data-stu-id="8af52-103">Release notes for Microsoft Edge Beta Channel</span></span>

<span data-ttu-id="8af52-104">これらのリリース ノートでは、Microsoft Edge Beta チャネルに含まれている新機能とセキュリティ以外の更新プログラムに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="8af52-104">These release notes provide information about new features and non-security updates that are included in the Microsoft Edge Beta Channel.</span></span> <span data-ttu-id="8af52-105">これらのリリース ノートのアーカイブ バージョンは、[こちら](microsoft-edge-relnote-archive-beta-channel.md)から入手できます。</span><span class="sxs-lookup"><span data-stu-id="8af52-105">Archived versions of these release notes are available [here](microsoft-edge-relnote-archive-beta-channel.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8af52-106">Microsoft Edge Web プラットフォームは、ユーザー エクスペリエンス、セキュリティ、およびプライバシーを向上させるために絶えず進化しています。</span><span class="sxs-lookup"><span data-stu-id="8af52-106">Microsoft Edge Web Platform constantly evolves to improve user experience, security, and privacy.</span></span> <span data-ttu-id="8af52-107">詳細については、「[Microsoft Edge 向けのサイトの互換性に影響する変更点](/microsoft-edge/web-platform/site-impacting-changes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8af52-107">To learn more, see [Site compatibility-impacting changes coming to Microsoft Edge](/microsoft-edge/web-platform/site-impacting-changes).</span></span>

## <a name="version-92090222-june-21"></a><span data-ttu-id="8af52-108">バージョン 92.0.902.22: 6 月 21 日</span><span class="sxs-lookup"><span data-stu-id="8af52-108">Version 92.0.902.22: June 21</span></span>

### <a name="feature-updates"></a><span data-ttu-id="8af52-109">機能更新プログラム</span><span class="sxs-lookup"><span data-stu-id="8af52-109">Feature updates</span></span>

- <span data-ttu-id="8af52-110">**ユーザーは、Microsoft Edge で Internet Explorer モードに簡単にアクセスできます**。</span><span class="sxs-lookup"><span data-stu-id="8af52-110">**Users can easily get to Internet Explorer mode on Microsoft Edge**.</span></span> <span data-ttu-id="8af52-111">Microsoft Edge バージョン 92 から、ユーザーは、Enterprise モード サイト一覧でサイトが構成されるのを待っている間、スタンドアロンの IE 11 アプリケーションに依存する代わりに、Microsoft Edge の Internet Explorer モードでサイトを再読み込みできます。</span><span class="sxs-lookup"><span data-stu-id="8af52-111">Starting with Microsoft Edge version 92, users can reload a site in Internet Explorer mode on Microsoft Edge instead of relying on the standalone IE 11 application while waiting for a site to be configured in the Enterprise Mode Site List.</span></span> <span data-ttu-id="8af52-112">ユーザーは、サイトをローカル サイト リストに追加するように求められます。Microsoft Edge で同じページに移動すると、次の 30 日間 IE モードで自動的にレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="8af52-112">Users will be prompted to add the site to their local site list such that navigating to the same page in Microsoft Edge will automatically render in IE mode for the next 30 days.</span></span> <span data-ttu-id="8af52-113">*[InternetExplorerIntegrationReloadInIEModeAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed)* ポリシーを使用して、このエクスペリエンスを構成し、IE モードのエントリ ポイントへのアクセスと、ローカル サイト リストにサイトを追加する機能を許可できます。</span><span class="sxs-lookup"><span data-stu-id="8af52-113">You can use the *[InternetExplorerIntegrationReloadInIEModeAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed)* policy to configure this experience and allow access to the IE mode entry points as well as the ability to add sites to the local site list.</span></span> <span data-ttu-id="8af52-114">*[InternetExplorerIntegrationLocalSiteListExpirationDays](/deployedge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays)* ポリシーを使用して、サイトをローカル サイト リストに保持する日数を調整できます。</span><span class="sxs-lookup"><span data-stu-id="8af52-114">You can use the *[InternetExplorerIntegrationLocalSiteListExpirationDays](/deployedge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays)* policy to adjust the number of days to keep sites on the local site list.</span></span>
<span data-ttu-id="8af52-115">Windows 10 バージョン 1909 の場合、KB5003698 以降が必要であることに注意してください。エンド ツー エンドのエクスペリエンスを実現するには、Windows 10 バージョン 2004、Windows 10 バージョン 20H2、または Windows 10 バージョン 21H1 の場合、 KB5003690 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="8af52-115">Note that KB5003698 or later is required for Windows 10, version 1909; or KB5003690 or later is required for Windows 10, version 2004, Windows 10, version 20H2, or Windows 10, version 21H1 for the end-to-end experience.</span></span>

- <span data-ttu-id="8af52-116">**MHTML ファイルは、既定では Internet Explorer モードで開きます**。</span><span class="sxs-lookup"><span data-stu-id="8af52-116">**MHTML files will default to opening in Internet Explorer mode**.</span></span> <span data-ttu-id="8af52-117">Microsoft Edge バージョン 92 Stable 以降、MHTML ファイルの種類は、Internet Explorer (IE11) アプリケーションではなく、Microsoft Edge の Internet Explorer モードで自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="8af52-117">Starting in Microsoft Edge version 92 Stable, MHTML file types will automatically open in Internet Explorer mode on Microsoft Edge instead of the Internet Explorer (IE11) application.</span></span> <span data-ttu-id="8af52-118">これは、ブラウザーで Outlook のメールを表示しようとしているときに最もよく見られます。</span><span class="sxs-lookup"><span data-stu-id="8af52-118">This is most commonly observed while trying to view Outlook emails in a browser.</span></span> <span data-ttu-id="8af52-119">この変更は、IE11 がこのファイルの種類の既定のハンドラーである場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="8af52-119">This change will occur only if IE11 is the default handler for this file type.</span></span> <span data-ttu-id="8af52-120">これを変更したい場合は、[このガイダンス](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)を使用して、Stable バージョン 92 更新プログラムをインストールする前に実行できます。</span><span class="sxs-lookup"><span data-stu-id="8af52-120">If you'd prefer to change this, you can do so prior to installing the Stable version 92 update using [this guidance](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration).</span></span>

- <span data-ttu-id="8af52-121">**支払い手段がデバイス間で同期されるようになりました**。</span><span class="sxs-lookup"><span data-stu-id="8af52-121">**Payment instruments are now synced across devices**.</span></span> <span data-ttu-id="8af52-122">Microsoft Edge バージョン 92 以降には、サインインしたデバイス間で支払い情報を同期するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8af52-122">Beginning with Microsoft Edge version 92, you have the option to synchronize your payment information across your signed in devices.</span></span>
<span data-ttu-id="8af52-123">注: これは制御された機能ロールアウトであり、現在 50% です。</span><span class="sxs-lookup"><span data-stu-id="8af52-123">Please note: this is a Controlled Feature Rollout and we are currently at 50%.</span></span> <span data-ttu-id="8af52-124">この機能が表示されない場合は、ロールアウトを続行しますので、しばらくしてからもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="8af52-124">If you don’t see this feature, please check back shortly as we continue our rollout.</span></span>

- <span data-ttu-id="8af52-125">**"開発者モード拡張機能を無効にする" という警告は完全に無視できます**。</span><span class="sxs-lookup"><span data-stu-id="8af52-125">**"Disable developer mode extensions" warning can be permanently dismissed**.</span></span> <span data-ttu-id="8af52-126">Microsoft Edge バージョン 92 以降では、[これを再度表示しない] オプションをクリックして、"開発者モード拡張機能を無効にする" という警告をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="8af52-126">Beginning with Microsoft Edge version 92, you can turn off the warning "Disable developer mode extensions" by clicking on the 'Don't show this again' option.</span></span>
<span data-ttu-id="8af52-127">注: これは制御された機能ロールアウトであり、現在 25% です。</span><span class="sxs-lookup"><span data-stu-id="8af52-127">Please note: this is a Controlled Feature Rollout and we are currently at 25%.</span></span> <span data-ttu-id="8af52-128">この機能が表示されない場合は、ロールアウトを続行しますので、しばらくしてからもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="8af52-128">If you don’t see this feature, please check back shortly as we continue our rollout.</span></span>

- <span data-ttu-id="8af52-129">**ツール バーから直接拡張機能を管理します**。</span><span class="sxs-lookup"><span data-stu-id="8af52-129">**Manage your extensions right from the toolbar**.</span></span> <span data-ttu-id="8af52-130">ツール バーのまったく新しい拡張機能メニューを使用すると、拡張機能を簡単に非表示またはピン留めできます。</span><span class="sxs-lookup"><span data-stu-id="8af52-130">The all-new extensions menu on the toolbar will allow you to hide/pin extensions easily.</span></span> <span data-ttu-id="8af52-131">拡張機能を管理し、新しい拡張機能を検索するためのクイック リンクでは、新しい拡張機能を簡単に見つけて、既存の拡張機能を管理できます。</span><span class="sxs-lookup"><span data-stu-id="8af52-131">The quick links to manage extensions and find new extensions will make it easy for you to find new extensions and manage your existing ones.</span></span>
<span data-ttu-id="8af52-132">注: これは制御された機能ロールアウトであり、現在 25% です。</span><span class="sxs-lookup"><span data-stu-id="8af52-132">Please note: this is a Controlled Feature Rollout and we are currently at 25%.</span></span> <span data-ttu-id="8af52-133">この機能が表示されない場合は、ロールアウトを続行しますので、しばらくしてからもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="8af52-133">If you don’t see this feature, please check back shortly as we continue our rollout.</span></span>

- <span data-ttu-id="8af52-134">**自動 HTTPS**。</span><span class="sxs-lookup"><span data-stu-id="8af52-134">**Automatic HTTPS**.</span></span> <span data-ttu-id="8af52-135">ユーザーには、このより安全なプロトコルをサポートする可能性が高いドメインで、ナビゲーションを HTTP から HTTPS にアップグレードするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8af52-135">Users will have the option to upgrade navigation from HTTP to HTTPS on domains likely to support this more secure protocol.</span></span> <span data-ttu-id="8af52-136">このサポートは、すべてのドメインに対して HTTPS 経由での配信を試行するように構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8af52-136">This support can also be configured to attempt delivery over HTTPS for all domains.</span></span>
<span data-ttu-id="8af52-137">注: この機能は実験中です。実験をオプトアウトした場合、この動作は見られません。</span><span class="sxs-lookup"><span data-stu-id="8af52-137">Please note: we are experimenting with this feature and this behavior won’t be seen if you have opted out of experiments.</span></span>

- <span data-ttu-id="8af52-138">**フォント レンダリングパフォーマンスの改善**。</span><span class="sxs-lookup"><span data-stu-id="8af52-138">**Improvements to font rendering**.</span></span> <span data-ttu-id="8af52-139">テキストのレンダリングが改善され、明瞭性が向上し、ぼやけ感が軽減されました。</span><span class="sxs-lookup"><span data-stu-id="8af52-139">Improvements have been made to the rendering of text to improve clarity and reduce blurriness.</span></span>
<span data-ttu-id="8af52-140">注: これは制御された機能ロールアウトであり、現在 25% です。</span><span class="sxs-lookup"><span data-stu-id="8af52-140">Please note: this is a Controlled Feature Rollout and we are currently at 25%.</span></span> <span data-ttu-id="8af52-141">この機能が表示されない場合は、ロールアウトを続行しますので、しばらくしてからもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="8af52-141">If you don’t see this feature, please check back shortly as we continue our rollout.</span></span>

### <a name="policy-updates"></a><span data-ttu-id="8af52-142">ポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="8af52-142">Policy updates</span></span>

#### <a name="new-policies"></a><span data-ttu-id="8af52-143">新しいポリシー</span><span class="sxs-lookup"><span data-stu-id="8af52-143">New policies</span></span>

<span data-ttu-id="8af52-144">8 つの新しいポリシーが追加されました。</span><span class="sxs-lookup"><span data-stu-id="8af52-144">Eight new policies were added.</span></span> <span data-ttu-id="8af52-145">更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://www.microsoft.com/edge/business/download)からダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="8af52-145">Download the updated Administrative Templates from the [Microsoft Edge Enterprise landing page](https://www.microsoft.com/edge/business/download).</span></span> <span data-ttu-id="8af52-146">次の新しいポリシーが追加されました。</span><span class="sxs-lookup"><span data-stu-id="8af52-146">The following new policies were added:</span></span>

- <span data-ttu-id="8af52-147">[AADWebSiteSSOUsingThisProfileEnabled](/DeployEdge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) このプロファイルを使用した職場または学校のサイトへのシングル サインオンが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="8af52-147">[AADWebSiteSSOUsingThisProfileEnabled](/DeployEdge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) Single sign-on for work or school sites using this profile enabled.</span></span>
- <span data-ttu-id="8af52-148">[AutomaticHttpsDefault](/DeployEdge/microsoft-edge-policies#automatichttpsdefault) 自動 HTTPS を構成する</span><span class="sxs-lookup"><span data-stu-id="8af52-148">[AutomaticHttpsDefault](/DeployEdge/microsoft-edge-policies#automatichttpsdefault) Configure Automatic HTTPS</span></span>
- <span data-ttu-id="8af52-149">[HeadlessModeEnabled](/DeployEdge/microsoft-edge-policies#headlessmodeenabled) ヘッドレス モードの使用を制御する</span><span class="sxs-lookup"><span data-stu-id="8af52-149">[HeadlessModeEnabled](/DeployEdge/microsoft-edge-policies#headlessmodeenabled) Control use of the Headless Mode</span></span>
- <span data-ttu-id="8af52-150">[InsecurePrivateNetworkRequestsAllowed](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed) 安全でない Web サイトが、よりプライベートなネットワーク エンドポイントに対して要求を行うのを許可するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="8af52-150">[InsecurePrivateNetworkRequestsAllowed](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed)Specifies whether to allow insecure websites to make requests to more-private network endpoints</span></span>
- <span data-ttu-id="8af52-151">[InsecurePrivateNetworkRequestsAllowedForUrls](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls) リストされたサイトが安全でないコンテキストからよりプライベートなネットワーク エンドポイントに要求を行うのを許可する</span><span class="sxs-lookup"><span data-stu-id="8af52-151">[InsecurePrivateNetworkRequestsAllowedForUrls](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls) Allow the listed sites to make requests to more-private network endpoints from insecure contexts</span></span>
- <span data-ttu-id="8af52-152">[InternetExplorerIntegrationLocalSiteListExpirationDays](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) サイトがローカル IE モード サイト リストに残る日数を指定する</span><span class="sxs-lookup"><span data-stu-id="8af52-152">[InternetExplorerIntegrationLocalSiteListExpirationDays](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) Specify the number of days that a site remains on the local IE mode site list</span></span>
- <span data-ttu-id="8af52-153">[InternetExplorerIntegrationReloadInIEModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) Internet Explorer モードで未構成のサイトを再度読み込みできるようにする</span><span class="sxs-lookup"><span data-stu-id="8af52-153">[InternetExplorerIntegrationReloadInIEModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) Allow unconfigured sites to be reloaded in Internet Explorer mode</span></span>
- <span data-ttu-id="8af52-154">[SharedArrayBufferUnrestrictedAccessAllowed](/DeployEdge/microsoft-edge-policies#sharedarraybufferunrestrictedaccessallowed) 非クロスオリジン分離コンテキストで SharedArrayBuffers を使用できるかどうかを指定する</span><span class="sxs-lookup"><span data-stu-id="8af52-154">[SharedArrayBufferUnrestrictedAccessAllowed](/DeployEdge/microsoft-edge-policies#sharedarraybufferunrestrictedaccessallowed) Specifies whether SharedArrayBuffers can be used in a non cross-origin-isolated context</span></span>

#### <a name="obsoleted-policy"></a><span data-ttu-id="8af52-155">非推奨ポリシー</span><span class="sxs-lookup"><span data-stu-id="8af52-155">Obsoleted Policy</span></span>

- <span data-ttu-id="8af52-156">[EnableSha1ForLocalAnchors](/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors) ローカル信頼アンカーによって発行された SHA-1 を使用して署名された証明書を許可します。</span><span class="sxs-lookup"><span data-stu-id="8af52-156">[EnableSha1ForLocalAnchors](/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors) Allow certificates signed using SHA-1 when issued by local trust anchors.</span></span>


## <a name="version-9209029-june-8"></a><span data-ttu-id="8af52-157">バージョン 92.0.902.9: 6 月 8 日</span><span class="sxs-lookup"><span data-stu-id="8af52-157">Version 92.0.902.9: June 8</span></span>

<span data-ttu-id="8af52-158">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-158">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086441-june-3"></a><span data-ttu-id="8af52-159">バージョン 91.0.864.41: 6 月 3 日</span><span class="sxs-lookup"><span data-stu-id="8af52-159">Version 91.0.864.41: June 3</span></span>

<span data-ttu-id="8af52-160">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-160">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086437-may-27"></a><span data-ttu-id="8af52-161">バージョン 91.0.864.37: 5 月 27 日</span><span class="sxs-lookup"><span data-stu-id="8af52-161">Version 91.0.864.37: May 27</span></span>

<span data-ttu-id="8af52-162">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-162">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086436-may-26"></a><span data-ttu-id="8af52-163">バージョン 91.0.864.36: 5 月 26 日</span><span class="sxs-lookup"><span data-stu-id="8af52-163">Version 91.0.864.36: May 26</span></span>

<span data-ttu-id="8af52-164">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-164">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086433-may-21"></a><span data-ttu-id="8af52-165">バージョン 91.0.864.33: 5 月 21 日</span><span class="sxs-lookup"><span data-stu-id="8af52-165">Version 91.0.864.33: May 21</span></span>

<span data-ttu-id="8af52-166">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-166">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086427-may-14"></a><span data-ttu-id="8af52-167">バージョン 91.0.864.27: 5 月 14 日</span><span class="sxs-lookup"><span data-stu-id="8af52-167">Version 91.0.864.27: May 14</span></span>

<span data-ttu-id="8af52-168">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-168">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086419-may-7"></a><span data-ttu-id="8af52-169">バージョン 91.0.864.19: 5 月 7 日</span><span class="sxs-lookup"><span data-stu-id="8af52-169">Version 91.0.864.19: May 7</span></span>

<span data-ttu-id="8af52-170">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-170">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086415-may-3"></a><span data-ttu-id="8af52-171">バージョン 91.0.864.15: 5 月 3 日</span><span class="sxs-lookup"><span data-stu-id="8af52-171">Version 91.0.864.15: May 3</span></span>

<span data-ttu-id="8af52-172">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-172">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086411-april-30"></a><span data-ttu-id="8af52-173">バージョン 91.0.864.11: 4 月 30 日</span><span class="sxs-lookup"><span data-stu-id="8af52-173">Version 91.0.864.11: April 30</span></span>

### <a name="feature-updates"></a><span data-ttu-id="8af52-174">機能更新プログラム</span><span class="sxs-lookup"><span data-stu-id="8af52-174">Feature updates</span></span>

- <span data-ttu-id="8af52-175">**プロキシ レベルで Microsoft Defender Application Guard コンテナーから発信されたネットワーク トラフィックを特定します**。</span><span class="sxs-lookup"><span data-stu-id="8af52-175">**Identify network traffic originating from Microsoft Defender Application Guard containers at the proxy level**.</span></span> <span data-ttu-id="8af52-176">Microsoft Edge バージョン 91 以降、Application Guard コンテナーから発信されるネットワーク トラフィックにタグ付けするためのサポートが組み込まれたため、企業はそれらを識別し、特定のポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="8af52-176">Starting with Microsoft Edge version 91, there’s built in support to tag network traffic originating from Application Guard containers, allowing enterprises to identify them and apply specific policies.</span></span>

- <span data-ttu-id="8af52-177">**ホストから Edge Application Guard コンテナーへのお気に入りの同期を許可するサポート オプション**。</span><span class="sxs-lookup"><span data-stu-id="8af52-177">**Support option to allow synchronizing Favorites from the host to the Edge Application Guard container**.</span></span> <span data-ttu-id="8af52-178">Microsoft Edge バージョン 91 以降、ユーザーには、ホストからコンテナーにお気に入りを同期するように Application Guard を構成するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8af52-178">Starting with Microsoft Edge version 91, users have the option to configure Application Guard to synchronize their favorites from the host to the container.</span></span> <span data-ttu-id="8af52-179">これにより、新しいお気に入りがコンテナーにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="8af52-179">This ensures new favorites appear on the container as well.</span></span>

- <span data-ttu-id="8af52-180">**音声認識 API のサポート**。</span><span class="sxs-lookup"><span data-stu-id="8af52-180">**Support for Speech Recognition APIs**.</span></span> <span data-ttu-id="8af52-181">Microsoft Edge バージョン 91 以降、Google.com および同様のサイトでの音声認識コマンドの API サポートが追加されます。</span><span class="sxs-lookup"><span data-stu-id="8af52-181">Starting with Microsoft Edge version 91, API support for speech recognition commands on Google.com and similar sites will be added.</span></span> <span data-ttu-id="8af52-182">この機能は、実験を有効にしたユーザーのランダムに選択されたグループに限定されます。</span><span class="sxs-lookup"><span data-stu-id="8af52-182">This feature is limited to a randomly selected group of users who have enabled experimentation.</span></span> <span data-ttu-id="8af52-183">これらのユーザーは、機能チームにフィードバックを提供しています。</span><span class="sxs-lookup"><span data-stu-id="8af52-183">These users are giving feedback to the feature team.</span></span>

- <span data-ttu-id="8af52-184">**新しいテーマの色でブラウザーをカスタマイズします**。</span><span class="sxs-lookup"><span data-stu-id="8af52-184">**Personalize your browser with new theme colors**.</span></span> <span data-ttu-id="8af52-185">[設定] > [デザイン ページ] にある 14 の新しいテーマ カラーの 1 つを使用して、Microsoft Edge を独自のものにします。</span><span class="sxs-lookup"><span data-stu-id="8af52-185">Make Microsoft Edge your own with one of the fourteen new theme colors on the Settings -> Appearance page.</span></span> <span data-ttu-id="8af52-186">Microsoft Edge アドオン サイトからカスタム テーマをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8af52-186">You can also install custom themes from the Microsoft Edge Add-on site.</span></span> [<span data-ttu-id="8af52-187">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8af52-187">Learn more</span></span>](https://techcommunity.microsoft.com/t5/articles/make-microsoft-edge-your-own-with-themes/m-p/2083165)

- <span data-ttu-id="8af52-188">**ダウンロードの中断** Microsoft Edge バージョン 91 以降、ブラウザーは、ユーザー操作なしでダウンロードが開始され、SmartScreen アプリケーション評価チェックでサポートされない場合に、コンピューターに害を及ぼす可能性のある種類のダウンロードを自動的に中断します。</span><span class="sxs-lookup"><span data-stu-id="8af52-188">**Interrupt Downloads** Starting with Microsoft Edge version 91 the browser will automatically interrupt downloads of types which could harm your computer if those downloads are started without a user interaction and are not supported by SmartScreen Application Reputation check.</span></span> <span data-ttu-id="8af52-189">ユーザーは、ダウンロード アイテムを右クリックして [保持] を選択することにより、上書きしてダウンロードを続行できます。</span><span class="sxs-lookup"><span data-stu-id="8af52-189">Users may override and continue to download by right clicking and choosing “Keep” on the download item.</span></span>
<span data-ttu-id="8af52-190">企業の管理者は、次の 2 つのポリシーのいずれかでこの動作をオプトアウトできます。</span><span class="sxs-lookup"><span data-stu-id="8af52-190">Enterprise administrators may opt out of this behavior one of these two policies:</span></span>
    - <span data-ttu-id="8af52-191">[ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - ドメイン上の指定されたファイルの種類のダウンロード ファイルの種類の拡張子に基づいた警告を無効にする 詳細については、「[Microsoft Edge セキュリティのダウンロードの中断](/deployedge/microsoft-edge-security-downloads-interruptions)」を参照してください</span><span class="sxs-lookup"><span data-stu-id="8af52-191">[ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - Disable download file type extension-based warnings for specified file types on domains For more information, see [Microsoft Edge Security downloads interruptions](/deployedge/microsoft-edge-security-downloads-interruptions)</span></span>

### <a name="policy-updates"></a><span data-ttu-id="8af52-192">ポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="8af52-192">Policy updates</span></span>

#### <a name="new-policies"></a><span data-ttu-id="8af52-193">新しいポリシー</span><span class="sxs-lookup"><span data-stu-id="8af52-193">New policies</span></span>

<span data-ttu-id="8af52-194">6 つの新しいポリシーが追加されました。</span><span class="sxs-lookup"><span data-stu-id="8af52-194">Six new policies were added.</span></span> <span data-ttu-id="8af52-195">更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://www.microsoft.com/edge/business/download)からダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="8af52-195">Download the updated Administrative Templates from the [Microsoft Edge Enterprise landing page](https://www.microsoft.com/edge/business/download).</span></span> <span data-ttu-id="8af52-196">次の新しいポリシーが追加されました。</span><span class="sxs-lookup"><span data-stu-id="8af52-196">The following new policies were added:</span></span>

- <span data-ttu-id="8af52-197">[ApplicationGuardTrafficIdentificationEnabled](/DeployEdge/microsoft-edge-policies#applicationguardtrafficidentificationenabled) - Application Guard トラフィック ID</span><span class="sxs-lookup"><span data-stu-id="8af52-197">[ApplicationGuardTrafficIdentificationEnabled](/DeployEdge/microsoft-edge-policies#applicationguardtrafficidentificationenabled) - Application Guard Traffic Identification</span></span>
- <span data-ttu-id="8af52-198">[ExplicitlyAllowedNetworkPorts](/DeployEdge/microsoft-edge-policies#explicitlyallowednetworkports) - 明示的に許可されたネットワーク ポート</span><span class="sxs-lookup"><span data-stu-id="8af52-198">[ExplicitlyAllowedNetworkPorts](/DeployEdge/microsoft-edge-policies#explicitlyallowednetworkports) - Explicitly allowed network ports</span></span>
- <span data-ttu-id="8af52-199">[ImportStartupPageSettings](/DeployEdge/microsoft-edge-policies#importstartuppagesettings) - スタートアップ ページ設定のインポートを許可する</span><span class="sxs-lookup"><span data-stu-id="8af52-199">[ImportStartupPageSettings](/DeployEdge/microsoft-edge-policies#importstartuppagesettings) - Allow importing of startup page settings</span></span>
- <span data-ttu-id="8af52-200">[MathSolverEnabled](/DeployEdge/microsoft-edge-policies#mathsolverenabled) - ユーザーが数学の問題を切り取って、Microsoft Edge の段階的な説明で解決策を得ることができる</span><span class="sxs-lookup"><span data-stu-id="8af52-200">[MathSolverEnabled](/DeployEdge/microsoft-edge-policies#mathsolverenabled) - Let users snip a Math problem and get the solution with a step-by-step explanation in Microsoft Edge</span></span>
- <span data-ttu-id="8af52-201">[NewTabPageContentEnabled](/DeployEdge/microsoft-edge-policies#newtabpagecontentenabled) - 新しいタブ ページで Microsoft ニュース コンテンツを許可する</span><span class="sxs-lookup"><span data-stu-id="8af52-201">[NewTabPageContentEnabled](/DeployEdge/microsoft-edge-policies#newtabpagecontentenabled) - Allow Microsoft News content on the new tab page</span></span>
- <span data-ttu-id="8af52-202">[NewTabPageQuickLinksEnabled](/DeployEdge/microsoft-edge-policies#newtabpagequicklinksenabled) - 新しいタブ ページでクイック リンクを許可する</span><span class="sxs-lookup"><span data-stu-id="8af52-202">[NewTabPageQuickLinksEnabled](/DeployEdge/microsoft-edge-policies#newtabpagequicklinksenabled) - Allow quick links on the new tab page</span></span>

#### <a name="obsoleted-policy"></a><span data-ttu-id="8af52-203">非推奨ポリシー</span><span class="sxs-lookup"><span data-stu-id="8af52-203">Obsoleted Policy</span></span>

- <span data-ttu-id="8af52-204">[ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - プロアクティブ認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="8af52-204">[ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - Enable Proactive Authentication</span></span>
<!-- end major 91 -->

## <a name="version-90081846-april-22"></a><span data-ttu-id="8af52-205">バージョン 90.0.818.46: 4 月 22 日</span><span class="sxs-lookup"><span data-stu-id="8af52-205">Version 90.0.818.46: April 22</span></span>

<span data-ttu-id="8af52-206">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-206">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081842-april-20"></a><span data-ttu-id="8af52-207">バージョン 90.0.818.42: 4 月 20 日</span><span class="sxs-lookup"><span data-stu-id="8af52-207">Version 90.0.818.42: April 20</span></span>

<span data-ttu-id="8af52-208">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-208">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081841-april-16"></a><span data-ttu-id="8af52-209">バージョン 90.0.818.41: 4 月 16 日</span><span class="sxs-lookup"><span data-stu-id="8af52-209">Version 90.0.818.41: April 16</span></span>

<span data-ttu-id="8af52-210">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-210">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081838-april-14"></a><span data-ttu-id="8af52-211">バージョン 90.0.818.38: 4 月 14 日</span><span class="sxs-lookup"><span data-stu-id="8af52-211">Version 90.0.818.38: April 14</span></span>

<span data-ttu-id="8af52-212">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-212">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081836-april-12"></a><span data-ttu-id="8af52-213">バージョン 90.0.818.36: 4 月 12 日</span><span class="sxs-lookup"><span data-stu-id="8af52-213">Version 90.0.818.36: April 12</span></span>

<span data-ttu-id="8af52-214">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-214">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081827-april-2"></a><span data-ttu-id="8af52-215">バージョン 90.0.818.27: 4 月 2 日</span><span class="sxs-lookup"><span data-stu-id="8af52-215">Version 90.0.818.27: April 2</span></span>

<span data-ttu-id="8af52-216">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-216">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081822-march-29"></a><span data-ttu-id="8af52-217">バージョン 90.0.818.22: 3 月 29 日</span><span class="sxs-lookup"><span data-stu-id="8af52-217">Version 90.0.818.22: March 29</span></span>

<span data-ttu-id="8af52-218">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-218">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081814-march-22"></a><span data-ttu-id="8af52-219">バージョン 90.0.818.14: 3 月 22 日</span><span class="sxs-lookup"><span data-stu-id="8af52-219">Version 90.0.818.14: March 22</span></span>

<span data-ttu-id="8af52-220">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-220">Fixed various bugs and performance issues.</span></span>
<!-- begin major 90 -->
## <a name="version-9008188-march-16"></a><span data-ttu-id="8af52-221">バージョン 90.0.818.8: 3 月 16 日</span><span class="sxs-lookup"><span data-stu-id="8af52-221">Version 90.0.818.8: March 16</span></span>

### <a name="feature-updates"></a><span data-ttu-id="8af52-222">機能更新プログラム</span><span class="sxs-lookup"><span data-stu-id="8af52-222">Feature updates</span></span>

- <span data-ttu-id="8af52-223">**シングル サインオン (SSO) は、Mac OS の Azure Active Directory (Azure AD) アカウントと Microsoft アカウント (MSA) で利用できます**。</span><span class="sxs-lookup"><span data-stu-id="8af52-223">**Single Sign On (SSO) is now available for Azure Active Directory (Azure AD) accounts and Microsoft Account (MSA) on macOS**.</span></span> <span data-ttu-id="8af52-224">macOS で Microsoft Edge にサインインしたユーザーは、Work アカウントと Microsoft アカウント (bing.com、office.com、msn.com、outlook.com など) でシングル サインオンを許可するように構成された Web サイトに自動的にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8af52-224">A user signed in on Microsoft Edge on macOS will now get automatically signed into websites that are configured to allow single sign on with Work and Microsoft accounts (for example, bing.com, office.com, msn.com, and outlook.com).</span></span>

- **<span data-ttu-id="8af52-225">キオスク モード。</span><span class="sxs-lookup"><span data-stu-id="8af52-225">Kiosk mode.</span></span>** <span data-ttu-id="8af52-226">Microsoft Edge バージョン 90 以降、UI の印刷設定をロックダウンして、構成済みのプリンターと [PDFに印刷] オプションのみを許可しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-226">Starting with Microsoft Edge version 90, we have locked down the UI print settings to only allow the configured printers and “Print to PDF” options.</span></span> <span data-ttu-id="8af52-227">また、割り当てられたアクセスのシングル アプリ キオスク モード内で改善を行い、ブラウザーからの他のアプリケーションの起動を制限しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-227">We have also done improvements within the assigned access single app kiosk mode to restrict the launch of other applications from the browser.</span></span> <span data-ttu-id="8af52-228">キオスク モードの機能の詳細については、[こちら](/deployedge/microsoft-edge-configure-kiosk-mode#kiosk-mode-supported-features)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8af52-228">For more information about the kiosk mode features please go [here](/deployedge/microsoft-edge-configure-kiosk-mode#kiosk-mode-supported-features).</span></span>

- **<span data-ttu-id="8af52-229">印刷:</span><span class="sxs-lookup"><span data-stu-id="8af52-229">Printing:</span></span>**

  - <span data-ttu-id="8af52-230">**PostScript プリンターではないプリンター向けの新しい印刷ラスタライズ モード**。</span><span class="sxs-lookup"><span data-stu-id="8af52-230">**New print rasterization mode for non-PostScript printers**.</span></span> <span data-ttu-id="8af52-231">Microsoft Edge バージョン 90 より、管理者は新しいポリシーを使用して、ユーザーの印刷ラスタライズ モードを定義できます。</span><span class="sxs-lookup"><span data-stu-id="8af52-231">Starting with Microsoft Edge version 90, Admins can use a new policy to define print rasterization mode for their users.</span></span> <span data-ttu-id="8af52-232">このポリシーは、Windows の PostScript プリンターではないプリンターから Microsoft Edge で印刷する方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="8af52-232">This policy  controls how Microsoft Edge prints to non-PostScript printers on Windows.</span></span>  <span data-ttu-id="8af52-233">PostScript プリンターではないプリンターの印刷ジョブが正しく印刷されるようにラスター化する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="8af52-233">Sometimes print jobs on non-PostScript printers need to be rasterized to print correctly.</span></span> <span data-ttu-id="8af52-234">印刷オプションには「フル」と 「高速」が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8af52-234">The print options are Full and Fast.</span></span>

  - <span data-ttu-id="8af52-235">**追加された、印刷用のページ拡大/縮小オプション**。</span><span class="sxs-lookup"><span data-stu-id="8af52-235">**Additional page scaling options for printing**.</span></span> <span data-ttu-id="8af52-236">ユーザーは、追加のオプションを使用して Web ページや PDF ドキュメントを印刷しながらスケーリングをカスタマイズできるようにりました。</span><span class="sxs-lookup"><span data-stu-id="8af52-236">Users are now able to customize scaling while printing webpages and PDF documents using additional options.</span></span> <span data-ttu-id="8af52-237">[ページサイズに合わせて印刷] オプションを使用すると、印刷用に選択した "用紙サイズ" に Web ページまたはドキュメントを収めることがきます。</span><span class="sxs-lookup"><span data-stu-id="8af52-237">The "Fit to Page" option ensures that the webpage or document is fit into the space available in the selected "Paper size" for printing.</span></span> <span data-ttu-id="8af52-238">「実際のサイズ」オプションを選択すと、選択した「用紙サイズ」に関係なく、印刷されるコンテンツのサイズに変更が加えられないようにします。</span><span class="sxs-lookup"><span data-stu-id="8af52-238">The "Actual size" option ensures that there are no changes in the size of the contents being printed regardless of the selected "Paper size".</span></span>

- **<span data-ttu-id="8af52-239">生産性:</span><span class="sxs-lookup"><span data-stu-id="8af52-239">Productivity:</span></span>**

  - <span data-ttu-id="8af52-240">**オートフィル候補が拡張され、クリップボードのアドレス フィールドのコンテンツが含まれるようになりました**。</span><span class="sxs-lookup"><span data-stu-id="8af52-240">**Autofill suggestions are extended to include address fields content from clipboard**.</span></span> <span data-ttu-id="8af52-241">クリップボードの内容は、オートフィル候補として表示するプロフィール フィールドまたはアドレス フィールド (電話番号、メールアドレス、郵便番号、市区町間、州など) をクリックすると解析されます。</span><span class="sxs-lookup"><span data-stu-id="8af52-241">Clipboard content is parsed when you click on a profile/address field (for example, phone, email, zip code, city, state, etc.) to show as autofill suggestions.</span></span>

  - <span data-ttu-id="8af52-242">**ユーザーは、フォームやフィールドが候補として検出されない場合でも、オートフィル候補を検索できます**。</span><span class="sxs-lookup"><span data-stu-id="8af52-242">**Users can search for autofill suggestions even if a form or field isn’t detected**.</span></span> <span data-ttu-id="8af52-243">現在、Microsoft Edge に情報を保存している場合、オートフィル候補が自動的にポップアップ表示され、フォームに入力する時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="8af52-243">Today if you have your information saved on Microsoft Edge, autofill suggestions pop up automatically and help you save time while filling out forms.</span></span> <span data-ttu-id="8af52-244">オートフィルでフォームが見つからない場合や、通常オートフィルを設定しないフォーム (一時的なフォームなど) のデータを取得する場合は、オートフィルを使用して情報を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="8af52-244">In cases where autofill misses a form, or if you want to fetch data in forms that don't typically have autofill (like temporary forms), you can search for your information using autofill.</span></span>

- <span data-ttu-id="8af52-245">**Access はメニュー バーのフライアウトからダウンロードしています**。</span><span class="sxs-lookup"><span data-stu-id="8af52-245">**Access downloads from a flyout in the menu bar**.</span></span> <span data-ttu-id="8af52-246">ダウンロードは右上隅に表示され、アクティブなすべてのダウンロードが 1 か所に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8af52-246">Downloads will appear in the top-right corner with all the active downloads in one place.</span></span> <span data-ttu-id="8af52-247">このメニューは簡単に閉じることができるので、ユーザーは作業を中断することなく、閲覧を続けることができます。また、ダウンロードの全体的な進行状況をツールバーからすぐに監視できます。</span><span class="sxs-lookup"><span data-stu-id="8af52-247">This menu is easily dismissible so users can continue browsing uninterrupted, and they can monitor overall download progress right from the toolbar.</span></span> <span data-ttu-id="8af52-248">[詳しくはこちらをご覧ください](https://techcommunity.microsoft.com/t5/articles/introducing-the-new-downloads-experience/m-p/2111551)。</span><span class="sxs-lookup"><span data-stu-id="8af52-248">[Learn more](https://techcommunity.microsoft.com/t5/articles/introducing-the-new-downloads-experience/m-p/2111551).</span></span>


### <a name="policy-updates"></a><span data-ttu-id="8af52-249">ポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="8af52-249">Policy updates</span></span>

#### <a name="new-policies"></a><span data-ttu-id="8af52-250">新しいポリシー</span><span class="sxs-lookup"><span data-stu-id="8af52-250">New policies</span></span>

<span data-ttu-id="8af52-251">7 個の新しいポリシーが追加されました。</span><span class="sxs-lookup"><span data-stu-id="8af52-251">Seven new policies were added.</span></span> <span data-ttu-id="8af52-252">更新された管理用テンプレートを、[Microsoft Edge Enterprise のランディング ページ](https://www.microsoft.com/edge/business/download)からダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="8af52-252">Download the updated Administrative Templates from the [Microsoft Edge Enterprise landing page](https://www.microsoft.com/edge/business/download).</span></span> <span data-ttu-id="8af52-253">次の新しいポリシーが追加されました。</span><span class="sxs-lookup"><span data-stu-id="8af52-253">The following new policies were added:</span></span>

- <span data-ttu-id="8af52-254">[ApplicationGuardFaitesSyncEnabled](./microsoft-edge-policies.md#applicationguardfavoritessyncenabled) - Application Guard のお気に入りの同期の有効化</span><span class="sxs-lookup"><span data-stu-id="8af52-254">[ApplicationGuardFavoritesSyncEnabled](./microsoft-edge-policies.md#applicationguardfavoritessyncenabled) - Application Guard Favorites Sync Enabled</span></span>
- <span data-ttu-id="8af52-255">[ManagedConfigurationPerOrigin](./microsoft-edge-policies.md#managedconfigurationperorigin) - Web サイトの管理された構成値を特定のオリジンに設定する</span><span class="sxs-lookup"><span data-stu-id="8af52-255">[ManagedConfigurationPerOrigin](./microsoft-edge-policies.md#managedconfigurationperorigin) - Sets managed configuration values for websites to specific origins</span></span>
- <span data-ttu-id="8af52-256">[PrintRasterizationMode](./microsoft-edge-policies.md#printrasterizationmode) - 印刷ラスタライズ モード</span><span class="sxs-lookup"><span data-stu-id="8af52-256">[PrintRasterizationMode](./microsoft-edge-policies.md#printrasterizationmode) - Print Rasterization Mode</span></span>
- <span data-ttu-id="8af52-257">[QuickViewOfficeFilesEnabled](./microsoft-edge-policies.md#quickviewofficefilesenabled) - Microsoft Edge で QuickView Office ファイル機能を管理する</span><span class="sxs-lookup"><span data-stu-id="8af52-257">[QuickViewOfficeFilesEnabled](./microsoft-edge-policies.md#quickviewofficefilesenabled) - Manage QuickView Office files capability in Microsoft Edge</span></span>
- <span data-ttu-id="8af52-258">[SSLErrorOvererrorallowedForOrigins](./microsoft-edge-policies.md#sslerroroverrideallowedfororigins) - 特定の生成元の HTTPS 警告ページからユーザーが進むのを許可する</span><span class="sxs-lookup"><span data-stu-id="8af52-258">[SSLErrorOverrideAllowedForOrigins](./microsoft-edge-policies.md#sslerroroverrideallowedfororigins) - Allow users to proceed from the HTTPS warning page for specific origins</span></span>
- <span data-ttu-id="8af52-259">[WindowOcclusionEnabled](./microsoft-edge-policies.md#windowocclusionenabled) - Window Occlusion を有効にする</span><span class="sxs-lookup"><span data-stu-id="8af52-259">[WindowOcclusionEnabled](./microsoft-edge-policies.md#windowocclusionenabled) - Enable Window Occlusion</span></span>
- <span data-ttu-id="8af52-260">[WindowsHelloForHTTPAuthEnabled](./microsoft-edge-policies.md#windowshelloforhttpauthenabled) - HTTP 認証用 Windows Hello を有効にする</span><span class="sxs-lookup"><span data-stu-id="8af52-260">[WindowsHelloForHTTPAuthEnabled](./microsoft-edge-policies.md#windowshelloforhttpauthenabled) - Windows Hello For HTTP Auth Enabled</span></span>

#### <a name="deprecated-policies"></a><span data-ttu-id="8af52-261">廃止されたポリシー</span><span class="sxs-lookup"><span data-stu-id="8af52-261">Deprecated policies</span></span>

- <span data-ttu-id="8af52-262">[NativeWindowOcclusionEnabled](./microsoft-edge-policies.md#nativewindowocclusionenabled) - ネイティブ ウィンドウ オクルージョンを有効にする。</span><span class="sxs-lookup"><span data-stu-id="8af52-262">[NativeWindowOcclusionEnabled](./microsoft-edge-policies.md#nativewindowocclusionenabled) - Enable Native Window Occlusion</span></span>
- <span data-ttu-id="8af52-263">[SSLVersionMin](./microsoft-edge-policies.md#sslversionmin)- 最小限の TLS バージョンを有効になっています</span><span class="sxs-lookup"><span data-stu-id="8af52-263">[SSLVersionMin](./microsoft-edge-policies.md#sslversionmin)- Minimum TLS version enabled</span></span>
<!-- end major 90 -->

## <a name="version-89077454-march-13"></a><span data-ttu-id="8af52-264">バージョン 89.0.774.54: 3 月 13 日</span><span class="sxs-lookup"><span data-stu-id="8af52-264">Version 89.0.774.54: March 13</span></span>

<span data-ttu-id="8af52-265">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-265">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077450-march-10"></a><span data-ttu-id="8af52-266">バージョン 89.0.774.50: 3 月 10 日</span><span class="sxs-lookup"><span data-stu-id="8af52-266">Version 89.0.774.50: March 10</span></span>

<span data-ttu-id="8af52-267">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-267">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077448-march-8"></a><span data-ttu-id="8af52-268">バージョン 89.0.774.48: 3 月 8 日</span><span class="sxs-lookup"><span data-stu-id="8af52-268">Version 89.0.774.48: March 8</span></span>

<span data-ttu-id="8af52-269">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-269">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077445-march-3"></a><span data-ttu-id="8af52-270">バージョン 89.0.774.45: 3 月 3 日</span><span class="sxs-lookup"><span data-stu-id="8af52-270">Version 89.0.774.45: March 3</span></span>

<span data-ttu-id="8af52-271">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-271">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077439-february-26"></a><span data-ttu-id="8af52-272">バージョン 89.0.774.39: 2 月 26 日</span><span class="sxs-lookup"><span data-stu-id="8af52-272">Version 89.0.774.39: February 26</span></span>

<span data-ttu-id="8af52-273">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-273">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077434-february-22"></a><span data-ttu-id="8af52-274">バージョン 89.0.774.34: 2 月 22 日</span><span class="sxs-lookup"><span data-stu-id="8af52-274">Version 89.0.774.34: February 22</span></span>

<span data-ttu-id="8af52-275">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-275">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077427-february-12"></a><span data-ttu-id="8af52-276">バージョン 89.0.774.27: 2 月 12 日</span><span class="sxs-lookup"><span data-stu-id="8af52-276">Version 89.0.774.27: February 12</span></span>

<span data-ttu-id="8af52-277">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-277">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077423-february-8"></a><span data-ttu-id="8af52-278">バージョン 89.0.774.23: 2 月 8 日</span><span class="sxs-lookup"><span data-stu-id="8af52-278">Version 89.0.774.23: February 8</span></span>

<span data-ttu-id="8af52-279">さまざまなバグとパフォーマンスの問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="8af52-279">Fixed various bugs and performance issues.</span></span>

<!-- begin major 89 -->

<!--- Archived from Version 87.0.664.18: October 26 to to version 89.0.774.18: February 3 ---->
<!--- Archived from Version 87.0.664.12: October 20 to to version 86.0.622.15: September 14 ---->
<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a><span data-ttu-id="8af52-280">関連項目</span><span class="sxs-lookup"><span data-stu-id="8af52-280">See also</span></span>

- [<span data-ttu-id="8af52-281">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="8af52-281">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
