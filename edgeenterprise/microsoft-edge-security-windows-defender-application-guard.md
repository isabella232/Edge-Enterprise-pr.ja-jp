---
title: Microsoft Edge および Microsoft Defender Application Guard
ms.author: srugh
author: dan-wesley
manager: seanlyn
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge での Microsoft Defender Application Guard のサポート
ms.openlocfilehash: 751201192c3b4e69cc866f35e51a6db23b9972f9
ms.sourcegitcommit: c290b0b0fa6b7d7f94dcdfdda91302da733326ec
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314590"
---
# <span data-ttu-id="b30b9-103">Microsoft Edge での Microsoft Defender Application Guard のサポート</span><span class="sxs-lookup"><span data-stu-id="b30b9-103">Microsoft Edge support for Microsoft Defender Application Guard</span></span>

<span data-ttu-id="b30b9-104">この記事では、Microsoft Edge による Microsoft Defender Application Guard (Application Guard) のサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b30b9-104">This article describes how Microsoft Edge supports Microsoft Defender Application Guard (Application Guard).</span></span>

> [!NOTE]
> <span data-ttu-id="b30b9-105">この記事は Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b30b9-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="b30b9-106">概要</span><span class="sxs-lookup"><span data-stu-id="b30b9-106">Overview</span></span>

<span data-ttu-id="b30b9-107">エンタープライズのセキュリティ設計者は、生産性とセキュリティとの間の葛藤に取り組む必要があります。</span><span class="sxs-lookup"><span data-stu-id="b30b9-107">Security architects in the enterprise must deal with the tension that exists between productivity and security.</span></span> <span data-ttu-id="b30b9-108">ブラウザーをロック ダウンし、少数の信頼されたサイトだけを読み込むようにするのは比較的簡単です。</span><span class="sxs-lookup"><span data-stu-id="b30b9-108">It's relatively easy to lock down a browser and only allow a handful of trusted sites to load.</span></span> <span data-ttu-id="b30b9-109">このアプローチにより全体的なセキュリティ態勢を向上させることはできますが、生産的とは言えないでしょう。</span><span class="sxs-lookup"><span data-stu-id="b30b9-109">This approach will improve the overall security posture but is arguably less productive.</span></span> <span data-ttu-id="b30b9-110">生産性を向上するために制限を緩めると、リスク プロファイルは増大します。</span><span class="sxs-lookup"><span data-stu-id="b30b9-110">If you make it less restrictive to improve productivity, you increase the risk profile.</span></span> <span data-ttu-id="b30b9-111">バランスを取るのは簡単ではありません。</span><span class="sxs-lookup"><span data-stu-id="b30b9-111">It's a hard balance to strike!</span></span>

<span data-ttu-id="b30b9-112">脅威の情勢は常に変化しているため、新たな脅威に対抗し続けるのはさらに大変です。</span><span class="sxs-lookup"><span data-stu-id="b30b9-112">It's even harder to keep up with new emerging threats in this constantly changing threat landscape.</span></span> <span data-ttu-id="b30b9-113">ブラウザーの基本的な役割は、ユーザーが信頼されていないソースからの信頼されていないコンテンツにアクセスし、ダウンロードして開けるようにすることであるため、ブラウザーはクライアント デバイスにおける主要な攻撃対象であり続けています。</span><span class="sxs-lookup"><span data-stu-id="b30b9-113">Browsers remain the primary attack surface on client devices because the browser's basic job is to let users access, download, and open untrusted content from untrusted sources.</span></span> <span data-ttu-id="b30b9-114">悪意のある攻撃者は、ブラウザーに対する新しい形態の攻撃をソーシャル エンジニアリングの手法で仕掛けることに余念がありません。</span><span class="sxs-lookup"><span data-stu-id="b30b9-114">Malicious actors are constantly working to social engineer new forms of attacks against the browser.</span></span> <span data-ttu-id="b30b9-115">セキュリティ インシデントの防止または検出/対応の戦略では、100% の安全性を保証できません。</span><span class="sxs-lookup"><span data-stu-id="b30b9-115">Security incident prevention or detection/response strategies can't guarantee 100% safety.</span></span>

<span data-ttu-id="b30b9-116">検討すべき重要なセキュリティ対策は、[侵害を想定する手法](https://docs.microsoft.com/office365/Enterprise/office-365-monitoring-and-testing#assume-breach-methodology)です。これは、攻撃を防ぐ努力をしたとしても、少なくとも 1 度は攻撃が成功することを受け入れることを意味しています。</span><span class="sxs-lookup"><span data-stu-id="b30b9-116">A key security strategy to consider is the [Assume Breach Methodology](https://docs.microsoft.com/office365/Enterprise/office-365-monitoring-and-testing#assume-breach-methodology), which means there's an acceptance that an attack is going to succeed at least once regardless of efforts to prevent it.</span></span> <span data-ttu-id="b30b9-117">この考え方では、被害を抑えるための防御を構築することが必要になります。こうすれば、このシナリオにおいて、企業のネットワークと他のリソースを保護し続けることが可能になります。</span><span class="sxs-lookup"><span data-stu-id="b30b9-117">This mindset requires building defenses to contain the damage, which ensures that corporate network and other resources remain protected in this scenario.</span></span>  <span data-ttu-id="b30b9-118">Microsoft Edge に Application Guard を展開することは、この戦略にうまく適合します。</span><span class="sxs-lookup"><span data-stu-id="b30b9-118">Deploying Application Guard for Microsoft Edge fits right into this strategy.</span></span>

## <span data-ttu-id="b30b9-119">Application Guard について</span><span class="sxs-lookup"><span data-stu-id="b30b9-119">About Application Guard</span></span>

<span data-ttu-id="b30b9-120">Application Guard は Windows 10 と Microsoft Edge 向けに設計されており、ハードウェア分離のアプローチを採用しています。</span><span class="sxs-lookup"><span data-stu-id="b30b9-120">Designed for Windows 10 and Microsoft Edge, Application Guard uses a hardware isolation approach.</span></span> <span data-ttu-id="b30b9-121">このアプローチでは、信頼されていないサイトへの移動はコンテナー内で行われます。</span><span class="sxs-lookup"><span data-stu-id="b30b9-121">This approach lets untrusted site navigation launch inside a container.</span></span> <span data-ttu-id="b30b9-122">ハードウェア分離により、エンタープライズは、セキュリティが侵害されたサイトや悪意のあるサイトにユーザーがアクセスした場合でも、企業のネットワークとデータを保護することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="b30b9-122">Hardware isolation helps enterprises safeguard their corporate network and data in case users visit a site that is compromised or is malicious.</span></span>

<span data-ttu-id="b30b9-123">エンタープライズ管理者は、信頼済みサイト、クラウド リソース、内部ネットワークを定義します。</span><span class="sxs-lookup"><span data-stu-id="b30b9-123">The enterprise administrator defines what are trusted sites, cloud resources, and internal networks.</span></span> <span data-ttu-id="b30b9-124">信頼済みサイトのリストに入っていないものはすべて、信頼されていないと見なされます。</span><span class="sxs-lookup"><span data-stu-id="b30b9-124">Everything that's not in the trusted sites list is considered untrusted.</span></span> <span data-ttu-id="b30b9-125">これらのサイトは、ユーザーのデバイス上で企業ネットワークとデータから分離されます。</span><span class="sxs-lookup"><span data-stu-id="b30b9-125">These sites are isolated from the corporate network and data on the user's device.</span></span>

<span data-ttu-id="b30b9-126">詳しくは、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b30b9-126">For more information:</span></span>

- <span data-ttu-id="b30b9-127">Application Guard を使用した [Microsoft Edge ブラウザー分離に関するビデオをご覧ください](microsoft-edge-video-security-application-guard.md)</span><span class="sxs-lookup"><span data-stu-id="b30b9-127">watch our video [Microsoft Edge browser isolation using Application Guard](microsoft-edge-video-security-application-guard.md)</span></span>
- <span data-ttu-id="b30b9-128">「[Application Guard の概要とその仕組み](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview#what-is-application-guard-and-how-does-it-work)」を参照してください</span><span class="sxs-lookup"><span data-stu-id="b30b9-128">read [What is Application Guard and how does it work?](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview#what-is-application-guard-and-how-does-it-work)</span></span>

<span data-ttu-id="b30b9-129">次のスクリーンショットは、ユーザーが安全なサイトを閲覧していることを示す Application Guard のメッセージの例です。</span><span class="sxs-lookup"><span data-stu-id="b30b9-129">The next screenshot shows an example of Application Guard's message showing that the user is browsing in a safe space.</span></span>

![安全な閲覧を示す Application Guard のメッセージ](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-1.png)

## <span data-ttu-id="b30b9-131">新着情報</span><span class="sxs-lookup"><span data-stu-id="b30b9-131">What's new</span></span>

<span data-ttu-id="b30b9-132">新しい Microsoft Edge ブラウザーでの Application Guard のサポートは、Microsoft Edge 従来版と機能的に同等であり、いくつかの改善が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b30b9-132">Application Guard support in the new Microsoft Edge  browser has functional parity with Microsoft Edge Legacy and includes several improvements.</span></span>

### <span data-ttu-id="b30b9-133">コンテナー内の拡張機能サポート</span><span class="sxs-lookup"><span data-stu-id="b30b9-133">Extension support inside the container</span></span>

<span data-ttu-id="b30b9-134">コンテナー内の拡張機能サポートは、お客様からの上位のリクエストの 1 つでした。</span><span class="sxs-lookup"><span data-stu-id="b30b9-134">Extension support inside the container has been one of the top requests from the customers.</span></span> <span data-ttu-id="b30b9-135">ブラウザーのパフォーマンスを向上するためにコンテナー内で広告ブロック機能を実行することから、コンテナー内で自社製のカスタム拡張機能を実行できるようにすることまで、シナリオは多岐にわたります。</span><span class="sxs-lookup"><span data-stu-id="b30b9-135">Scenarios ranged from wanting to run ad-blockers inside the container to boost browser performance to having the ability to run custom home-grown extensions inside the container.</span></span>

<span data-ttu-id="b30b9-136">Microsoft Edge バージョン 81 から、コンテナー内での拡張機能のインストールがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b30b9-136">Extension installs in the container is now supported, starting from Microsoft Edge version 81.</span></span> <span data-ttu-id="b30b9-137">このサポートは、ポリシーを使用して制御できます。</span><span class="sxs-lookup"><span data-stu-id="b30b9-137">This support can be controlled via policy.</span></span> <span data-ttu-id="b30b9-138">[ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist) ポリシーで使用される `updateURL` は、Application Guard が使用するネットワークの分離ポリシーでニュートラル リソースとして追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b30b9-138">The `updateURL` that gets used in [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist) policy should be added as Neutral Resources in the Network Isolation policies used by Application Guard.</span></span>

<span data-ttu-id="b30b9-139">コンテナーのサポートの例には、次のようなシナリオが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b30b9-139">Some examples of container support include the following scenarios:</span></span>

- <span data-ttu-id="b30b9-140">ホストでの拡張機能のインストールを強制する</span><span class="sxs-lookup"><span data-stu-id="b30b9-140">Force installs of an extension on the host</span></span>
- <span data-ttu-id="b30b9-141">ホストから拡張機能を削除する</span><span class="sxs-lookup"><span data-stu-id="b30b9-141">Removing an extension from the host</span></span>
- <span data-ttu-id="b30b9-142">ホストで拡張機能がブロックされる</span><span class="sxs-lookup"><span data-stu-id="b30b9-142">Extensions blocked on the host</span></span>

> [!NOTE]
> <span data-ttu-id="b30b9-143">また、拡張機能ストアからコンテナー内に個々の拡張機能を手動でインストールすることも可能です。</span><span class="sxs-lookup"><span data-stu-id="b30b9-143">It's also possible to manually install individual extensions inside the container from the extension store.</span></span> <span data-ttu-id="b30b9-144">手動でインストールされた拡張機能は、[永続化の許可](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard#application-specific-settings)ポリシーが有効な場合にのみ、コンテナーで保持されます。</span><span class="sxs-lookup"><span data-stu-id="b30b9-144">Manually installed extensions will only persist in the container when [Allow Persistence](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard#application-specific-settings) policy is enabled.</span></span>

### <span data-ttu-id="b30b9-145">デュアル プロキシを介した Application Guard トラフィックの識別</span><span class="sxs-lookup"><span data-stu-id="b30b9-145">Identifying Application Guard traffic via Dual Proxy</span></span>

<span data-ttu-id="b30b9-146">一部の企業のお客様は、Microsoft Defender Application Guard コンテナーから送信される Web トラフィックをプロキシ レベルで識別する必要がある特定のユース ケースで Application Guard を展開しています。</span><span class="sxs-lookup"><span data-stu-id="b30b9-146">Some enterprise customers are deploying Application Guard with a specific use case where they need to identify web traffic coming out of a Microsoft Defender Application Guard container at the proxy level.</span></span> <span data-ttu-id="b30b9-147">安定チャネルのバージョン 84 以降、Microsoft Edge はデュアル プロキシをサポートしてこの要件に対応します。</span><span class="sxs-lookup"><span data-stu-id="b30b9-147">Starting with Stable Channel version 84, Microsoft Edge will support dual proxy to address this requirement.</span></span> <span data-ttu-id="b30b9-148">この機能は、[ApplicationGuardContainerProxy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#applicationguardcontainerproxy) ポリシーを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="b30b9-148">You can configure this functionality using the [ApplicationGuardContainerProxy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#applicationguardcontainerproxy) policy.</span></span>

<span data-ttu-id="b30b9-149">次の図は、Microsoft Edge のデュアル プロキシ アーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="b30b9-149">The following drawing shows the dual proxy architecture for Microsoft Edge.</span></span>

![Application Guard のデュアル プロキシ アーキテクチャ](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-dual-proxy.png)

### <span data-ttu-id="b30b9-151">トラブルシューティングのための診断ページ</span><span class="sxs-lookup"><span data-stu-id="b30b9-151">Diagnostic page for troubleshooting</span></span>

<span data-ttu-id="b30b9-152">ユーザーにとってのもう一つの問題点は、問題が報告されたときにデバイス上で Application Guard の構成をトラブルシューティングすることです。</span><span class="sxs-lookup"><span data-stu-id="b30b9-152">Another user pain point is troubleshooting the Application Guard configuration on a device when a problem is reported.</span></span> <span data-ttu-id="b30b9-153">Microsoft Edge には、ユーザーの問題をトラブルシューティングするための診断ページ (`edge://application-guard-internals`) があります。</span><span class="sxs-lookup"><span data-stu-id="b30b9-153">Microsoft Edge has a diagnostics page (`edge://application-guard-internals`) to troubleshoot user issues.</span></span> <span data-ttu-id="b30b9-154">これらの診断の 1 つは、ユーザー デバイス上の構成に基づいて URL の信頼性を確認することです。</span><span class="sxs-lookup"><span data-stu-id="b30b9-154">One of these diagnostics is being able to check the URL trust based on the configuration on the user's device.</span></span>

<span data-ttu-id="b30b9-155">次のスクリーンショットは、デバイス上でユーザーが報告した問題の診断に役立つ、複数のタブを含む診断ページを示しています。</span><span class="sxs-lookup"><span data-stu-id="b30b9-155">The next screenshot shows a multiple tab diagnostics page to help diagnose user reported issues on the device.</span></span>

![Application Guard の診断ページ](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-2.png)

### <span data-ttu-id="b30b9-157">コンテナーでの Microsoft Edge の更新</span><span class="sxs-lookup"><span data-stu-id="b30b9-157">Microsoft Edge updates in the container</span></span>

<span data-ttu-id="b30b9-158">コンテナーでの Microsoft Edge 従来版の更新は、Windows OS の更新サイクルに含まれています。</span><span class="sxs-lookup"><span data-stu-id="b30b9-158">Microsoft Edge Legacy updates in the container are part of the Windows OS update cycle.</span></span> <span data-ttu-id="b30b9-159">新しいバージョンの Microsoft Edge の更新そのものは Windows OS から独立しているため、コンテナーの更新への依存関係はなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b30b9-159">Because the new version of Microsoft Edge updates itself independent of the Windows OS, there is no longer any dependency on container updates.</span></span> <span data-ttu-id="b30b9-160">ホストの Microsoft Edge のチャネルとバージョンは、コンテナー内で複製されます。</span><span class="sxs-lookup"><span data-stu-id="b30b9-160">The channel and version of the host Microsoft Edge is replicated inside the container.</span></span>

## <span data-ttu-id="b30b9-161">前提条件</span><span class="sxs-lookup"><span data-stu-id="b30b9-161">Prerequisites</span></span>

<span data-ttu-id="b30b9-162">次の要件は、Application Guard を Microsoft Edge で使用するデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b30b9-162">The following  requirements apply to devices using Application Guard with Microsoft Edge:</span></span>

- <span data-ttu-id="b30b9-163">Windows 10 1809 (RS5) 以降。</span><span class="sxs-lookup"><span data-stu-id="b30b9-163">Windows 10 1809 (RS5) and above.</span></span>
- <span data-ttu-id="b30b9-164">Windows クライアント SKU のみ</span><span class="sxs-lookup"><span data-stu-id="b30b9-164">Only Windows client SKUs</span></span>

  > [!NOTE]
  > <span data-ttu-id="b30b9-165">Application Guard は、Windows 10 Pro と Windows 10 Enterprise SKU でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="b30b9-165">Application Guard is only supported on Windows 10 Pro and Windows 10 Enterprise SKUs.</span></span>

- <span data-ttu-id="b30b9-166">[ソフトウェア要件](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard#software-requirements)に記載されている管理ソリューションのいずれか</span><span class="sxs-lookup"><span data-stu-id="b30b9-166">One of the management solutions described in [Software requirements](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard#software-requirements)</span></span>

## <span data-ttu-id="b30b9-167">Application Guard のインストール方法</span><span class="sxs-lookup"><span data-stu-id="b30b9-167">How to install Application Guard</span></span>

<span data-ttu-id="b30b9-168">Application Guard をインストールし、Microsoft Edge で構成およびテストするために必要な情報は、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b30b9-168">The following articles provide the information you need to install, configure, and test Application Guard with Microsoft Edge.</span></span>

- [<span data-ttu-id="b30b9-169">システム要件</span><span class="sxs-lookup"><span data-stu-id="b30b9-169">System requirements</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)
- [<span data-ttu-id="b30b9-170">Microsoft Defender Application Guard のインストール</span><span class="sxs-lookup"><span data-stu-id="b30b9-170">Install Microsoft Defender Application Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)
- [<span data-ttu-id="b30b9-171">Microsoft Defender Application Guard ポリシー設定の構成</span><span class="sxs-lookup"><span data-stu-id="b30b9-171">Configure Microsoft Defender group policy settings</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard)
- [<span data-ttu-id="b30b9-172">Application Guard をテストする</span><span class="sxs-lookup"><span data-stu-id="b30b9-172">Test Application Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/test-scenarios-md-app-guard)

## <span data-ttu-id="b30b9-173">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="b30b9-173">Frequently Asked Questions</span></span>

### <span data-ttu-id="b30b9-174">Application Guard は IE モードで動作しますか?</span><span class="sxs-lookup"><span data-stu-id="b30b9-174">Does Application Guard work in IE Mode?</span></span>

<span data-ttu-id="b30b9-175">IE モードは Application Guard の機能をサポートしていますが、IE モードでのこの機能の使用はあまり想定されていません。</span><span class="sxs-lookup"><span data-stu-id="b30b9-175">IE Mode supports Application Guard functionality, but we don't anticipate much use of this feature in IE Mode.</span></span> <span data-ttu-id="b30b9-176">IE モードは信頼済み内部サイトのリストに対して展開されることが推奨されており、Application Guard は信頼されていないサイトのみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="b30b9-176">IE Mode is recommended to be deployed for a list of trusted internal sites, and Application Guard is for untrusted sites only.</span></span> <span data-ttu-id="b30b9-177">Application Guard によって信頼済みリソースとみなされるようにするため、すべての IE モードのサイトや IP アドレスが、ネットワークの分離ポリシーにも追加されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b30b9-177">Make sure all the IE mode sites or IP addresses are also added to the Network Isolation policy to be considered as trusted resource by Application Guard.</span></span>

### <span data-ttu-id="b30b9-178">Application Guard の Chrome 拡張機能をインストールする必要はありますか?</span><span class="sxs-lookup"><span data-stu-id="b30b9-178">Do I need to install the Application Guard Chrome extension?</span></span>

<span data-ttu-id="b30b9-179">いいえ。Application Guard 機能は Microsoft Edge でネイティブでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b30b9-179">No, the Application Guard feature is natively supported in Microsoft Edge.</span></span> <span data-ttu-id="b30b9-180">事実、Application Guard の Chrome 拡張機能の構成は、Microsoft Edge ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b30b9-180">In fact, the Application Guard Chrome extension isn't a supported configuration in Microsoft Edge.</span></span>

### <span data-ttu-id="b30b9-181">FAQ に関連する他のプラットフォームはありますか?</span><span class="sxs-lookup"><span data-stu-id="b30b9-181">Are there any other platform related FAQs?</span></span>

<span data-ttu-id="b30b9-182">はい、できます。</span><span class="sxs-lookup"><span data-stu-id="b30b9-182">Yes.</span></span> [<span data-ttu-id="b30b9-183">よく寄せられる質問: Microsoft Defender Application Guard</span><span class="sxs-lookup"><span data-stu-id="b30b9-183">Frequently asked questions - Microsoft Defender Application Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/faq-md-app-guard) 

## <span data-ttu-id="b30b9-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="b30b9-184">See also</span></span>

- [<span data-ttu-id="b30b9-185">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="b30b9-185">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="b30b9-186">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b30b9-186">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="b30b9-187">ビデオ: Application Guard を使用した Microsoft Edge ブラウザー分離</span><span class="sxs-lookup"><span data-stu-id="b30b9-187">Video: Microsoft Edge browser isolation using Application Guard</span></span>](https://www.youtube.com/watch?v=zQjaRqNXMqw&t=3s)
