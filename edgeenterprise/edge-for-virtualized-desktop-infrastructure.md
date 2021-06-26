---
title: 仮想化デスクトップ インフラストラクチャのためのMicrosoft Edge
ms.author: anlake
author: AndreaLBarr
manager: collw
ms.date: 06/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 仮想化デスクトップ インフラストラクチャのためのMicrosoft Edge。
ms.openlocfilehash: eaad1b72934b336ce86d14dd8da92a6984d21914
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "11618179"
---
# <a name="microsoft-edge-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="c99c2-103">仮想化デスクトップ インフラストラクチャのためのMicrosoft Edge</span><span class="sxs-lookup"><span data-stu-id="c99c2-103">Microsoft Edge for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="c99c2-104">この記事では、仮想化環境で Microsoft Edge を使用する場合の要件と制約について説明します。</span><span class="sxs-lookup"><span data-stu-id="c99c2-104">This article describes the requirements and limitations for using Microsoft Edge in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="c99c2-105">VDI とは?</span><span class="sxs-lookup"><span data-stu-id="c99c2-105">What is VDI?</span></span>

<span data-ttu-id="c99c2-106">仮想デスクトップ インフラストラクチャ (VDI) は、デスクトップ オペレーティング システムとアプリケーションをデータ センターの一元的なサーバー上でホストする仮想化テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="c99c2-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="c99c2-107">これにより、完全にセキュリティで保護され、法令準拠した一元化されたソースを持つユーザーに対して、完全にカスタマイズされたデスクトップ エクスペリエンスを実現できます。</span><span class="sxs-lookup"><span data-stu-id="c99c2-107">This enables a fully personalized desktop experience for users with a fully secured and compliant centralized source.</span></span>

<span data-ttu-id="c99c2-108">Microsoft Edge は、ローカル デバイスで使用できるのと同じ方法で、このような仮想化環境で使用できます。セキュリティで保護された制御されたサーバー環境から実行されます。</span><span class="sxs-lookup"><span data-stu-id="c99c2-108">Microsoft Edge can be used in such a virtualized environment in much the same ways as it can be used on the local device, all the while running from secure and controlled server environment.</span></span> <span data-ttu-id="c99c2-109">選択した VDI ソリューションによっては、イントラネット アプリケーションとサイトへのシームレスなアクセスをユーザーに提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="c99c2-109">Depending on your chosen VDI solution it may also be possible to give your users seamless access to intranet Applications and Sites.</span></span>

<span data-ttu-id="c99c2-110">Edge のほとんどの機能は、特別な構成なしで VDI 環境でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c99c2-110">Most features of Edge are supported on VDI environments without any special configuration.</span></span> <span data-ttu-id="c99c2-111">ただし、最適なエクスペリエンスを実現するには、以下のガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="c99c2-111">However, to ensure an optimal experience it’s recommended to follow the guidance below.</span></span>

## <a name="platforms-certified-for-edge"></a><span data-ttu-id="c99c2-112">Edge の認定プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="c99c2-112">Platforms certified for Edge</span></span>

- <span data-ttu-id="c99c2-113">Azure 仮想デスクトップ</span><span class="sxs-lookup"><span data-stu-id="c99c2-113">Azure Virtual Desktop</span></span>
- <span data-ttu-id="c99c2-114">Citrix 仮想アプリとデスクトップ (旧称:XenApp および XenDesktop)</span><span class="sxs-lookup"><span data-stu-id="c99c2-114">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop)</span></span>

<span data-ttu-id="c99c2-115">他の VDI ソリューションはまだ Edge チームによって検証されていませんが、Edge で最も一般的なワークフローをサポートすることが期待されています。</span><span class="sxs-lookup"><span data-stu-id="c99c2-115">While other VDI solutions have not yet been verified by the Edge team, it is expected that the most common workflows in Edge should be supported.</span></span> <span data-ttu-id="c99c2-116">以下に示すガイダンスは、選択したソリューションに適用される場合と適用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="c99c2-116">Guidance provided below may or may not be applicable to your chosen solution.</span></span>

## <a name="edge-on-vdi-performance-considerations"></a><span data-ttu-id="c99c2-117">VDI 上の Edge のパフォーマンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="c99c2-117">Edge on VDI performance considerations</span></span>

<span data-ttu-id="c99c2-118">VDI 環境を設計する場合は、最適なパフォーマンスの達成のため、サーバー構成による制限も考慮して、ユーザーのワークフローとニーズを慎重に検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c99c2-118">When designing your VDI environment you should carefully consider the workflows and needs of your users to achieve optimal performance, as well as the limits of your server configuration.</span></span>

<span data-ttu-id="c99c2-119">Edge を VDI 環境に展開するには、以下の最小限の要件をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c99c2-119">Edge recommends the following minimal requirements for deploying Edge to VDI environments:</span></span>

- <span data-ttu-id="c99c2-120">vCPU – ユーザーごとに 2 から 4 のコア</span><span class="sxs-lookup"><span data-stu-id="c99c2-120">vCPU – 2-4 Cores per User</span></span>
- <span data-ttu-id="c99c2-121">RAM – ユーザーあたり 1 GB</span><span class="sxs-lookup"><span data-stu-id="c99c2-121">RAM – 1 GB per User</span></span>

<span data-ttu-id="c99c2-122">大規模な複雑な Web アプリケーションと拡張機能では、より多くのメモリが必要であり、環境を構成するときに考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c99c2-122">Please note that large complex web applications and extensions will require more memory and will have to be accounted for when configuring your environment.</span></span>

## <a name="edge-on-non-persisted-vdi-environments"></a><span data-ttu-id="c99c2-123">非永続的 VDI 環境の Edge</span><span class="sxs-lookup"><span data-stu-id="c99c2-123">Edge on non-persisted VDI environments</span></span>

<span data-ttu-id="c99c2-124">多くの VDI ソリューションでは、セッション間で保持される仮想環境と、ユーザーが複数の利用可能なコンピューターの 1 つ (セッションごとに異なるコンピューターに割り当てられている可能性がある) にユーザーが割り当てられている、保持されない環境へのアクセスを許可しています。ユーザー データはセッション間で同期する場合と同期しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="c99c2-124">Many VDI solutions allow access to persisted environments, where users are assigned a virtual environment that persists between sessions, and non-persisted environments, where users are assigned to one of several available machines, possibly a different machine each session, user data may or may not sync between sessions.</span></span>

<span data-ttu-id="c99c2-125">非永続的環境を使用する場合、通常、必要なアプリと構成を含む各デバイスに使用される "ゴールデン イメージ" が作成されます。</span><span class="sxs-lookup"><span data-stu-id="c99c2-125">When using a non-persisted environment, one usually creates a “golden image” which is used for each device that includes the needed apps and configurations.</span></span> <span data-ttu-id="c99c2-126">次に、このような画像の Edge を準備するための推奨事項を示します。</span><span class="sxs-lookup"><span data-stu-id="c99c2-126">Below are our recommendations for preparing Edge for such an image.</span></span>

### <a name="deploy-edge"></a><span data-ttu-id="c99c2-127">Edge の展開</span><span class="sxs-lookup"><span data-stu-id="c99c2-127">Deploy Edge</span></span>

<span data-ttu-id="c99c2-128">Windows 10 のバージョン 1803 以上を使用している場合は、システムに Microsoft Edge がインストールされているはずです。</span><span class="sxs-lookup"><span data-stu-id="c99c2-128">If you are on Windows 10, version 1803 and above, you should have Microsoft Edge installed on your system.</span></span> <span data-ttu-id="c99c2-129">ただし、 Windows の以前のバージョンを使用している場合や、Edge の異なるチャネルを展開する必要がある場合は、次の手順をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c99c2-129">However, if you are on an older version of Windows or wish to deploy a different channel of Edge, the following steps are recommended.</span></span>

1. <span data-ttu-id="c99c2-130">VDI VM オペレーティング システムに一致するEdge MSI パッケージを次からダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c99c2-130">Download the Edge MSI package matching your VDI VM operating system from:</span></span>

    - [<span data-ttu-id="c99c2-131">Microsoft Edge for Business のダウンロード - Microsoft</span><span class="sxs-lookup"><span data-stu-id="c99c2-131">Download Microsoft Edge for Business - Microsoft</span></span>](https://www.microsoft.com/edge/business/download)

2. <span data-ttu-id="c99c2-132">次のコマンドを実行して、MSI を VDI VM にインストールします。</span><span class="sxs-lookup"><span data-stu-id="c99c2-132">Install the MSI to the VDI VM by running the following command:</span></span>

    - `msiexec /i <path_to_msi> /qn /norestart /l*v <install_logfile_name>`

### <a name="disable-automatic-updates"></a><span data-ttu-id="c99c2-133">自動更新を無効にする</span><span class="sxs-lookup"><span data-stu-id="c99c2-133">Disable automatic updates</span></span>

<span data-ttu-id="c99c2-134">非永続的なコンピューターの場合は、自動更新プログラムを無効にし、代わりに "ゴールデン イメージ" を更新してエッジを更新して、多数のコンピューターの中でバージョンの不一致が発生しないようにすることがベス トプラクティスです。</span><span class="sxs-lookup"><span data-stu-id="c99c2-134">For non-persisted machines it is best practice to disable automatic updates and instead update Edge by updating the “golden image” to ensure that there are no version mismatches among the pool of machines.</span></span>

<span data-ttu-id="c99c2-135">自動更新を無効にする場合は、次のポリシーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c99c2-135">See the following policies for disabling automatic updates:</span></span>

- [<span data-ttu-id="c99c2-136">更新ポリシーのオーバーライド規定</span><span class="sxs-lookup"><span data-stu-id="c99c2-136">Update policy override default</span></span>](/deployedge/microsoft-edge-update-policies#updatedefault)

- [<span data-ttu-id="c99c2-137">更新ポリシーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="c99c2-137">Update policy override</span></span>](/deployedge/microsoft-edge-update-policies#update)

### <a name="profile-management"></a><span data-ttu-id="c99c2-138">プロファイル管理</span><span class="sxs-lookup"><span data-stu-id="c99c2-138">Profile management</span></span>

<span data-ttu-id="c99c2-139">永続的なセットアップでは、VM がセッション間でユーザー状態を維持しない可能性がある場合や、使用したことがない VM がユーザーに割り当てられ、ユーザー データは一切含まれていない可能性があることを考慮することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c99c2-139">On non-persisted setups it is important to consider that VMs may not maintain user state between sessions or users may be assigned a VM they have never used before and as such has none of their user data.</span></span>

<span data-ttu-id="c99c2-140">Edge へのアクセス方法に関係なく、Edge では、ユーザー データを同期する複数の方法をサポートしており、ユーザー データは使用可能です。</span><span class="sxs-lookup"><span data-stu-id="c99c2-140">Edge supports several methods for syncing user data such that it is available regardless of how they are accessing Edge.</span></span>

### <a name="azure-ad-sync"></a><span data-ttu-id="c99c2-141">Azure AD Sync</span><span class="sxs-lookup"><span data-stu-id="c99c2-141">Azure AD Sync</span></span>

<span data-ttu-id="c99c2-142">Azure AD プランでサポートされている場合は、Enterprise 同期が、最も高速かつ簡単に、Edge ユーザー データをすべてのユーザー デバイスに同期する方法です。</span><span class="sxs-lookup"><span data-stu-id="c99c2-142">If your Azure AD plan supports it, Enterprise sync is the fastest and easiest method to ensure that Edge user data is synced to all user devices.</span></span>  

<span data-ttu-id="c99c2-143">要件と構成の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c99c2-143">See the following for more information on requirements and configuration.</span></span>  

- [<span data-ttu-id="c99c2-144">Microsoft Edge エンタープライズ同期の構成|Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="c99c2-144">Configure Microsoft Edge enterprise sync | Microsoft Docs</span></span>](/deployedge/microsoft-edge-enterprise-sync)

### <a name="on-premise-sync-for-active-directory-users"></a><span data-ttu-id="c99c2-145">Active Directory ユーザーのオンプレミス同期</span><span class="sxs-lookup"><span data-stu-id="c99c2-145">On-premise Sync for Active Directory Users</span></span>

<span data-ttu-id="c99c2-146">オンプレミス同期を使用すると Microsoft Edge Active Directory ユーザーのお気に入りや設定をファイルに保存し、異なるコンピューター間で簡単に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="c99c2-146">With on-premises sync, Microsoft Edge saves an Active Directory user's favorites and settings to a file that can easily be moved between different computers.</span></span>  

<span data-ttu-id="c99c2-147">要件と構成の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c99c2-147">See the following for more information on requirements and configuration.</span></span>  

- [<span data-ttu-id="c99c2-148">Active Directory (AD) ユーザーのオンプレミス同期|Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="c99c2-148">On-premises sync for Active Directory (AD) users | Microsoft Docs</span></span>](/deployedge/microsoft-edge-on-premises-sync)

### <a name="user-profile-redirection"></a><span data-ttu-id="c99c2-149">ユーザー プロファイルのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="c99c2-149">User Profile Redirection</span></span>  

<span data-ttu-id="c99c2-150">このような非永続的環境でユーザー コンテキストを維持するために、ユーザー フォルダー全体を移行およびリダイレクトするためのいくつかのソリューションがあります。</span><span class="sxs-lookup"><span data-stu-id="c99c2-150">There are several solutions for migrating and redirecting the entire user folder to ensure that user context is maintained in such non-persisted environments.</span></span> <span data-ttu-id="c99c2-151">推奨されるソリューションを確認するには、VDI プロバイダーに確認してください。</span><span class="sxs-lookup"><span data-stu-id="c99c2-151">Check with your VDI provider to determine the recommended solution.</span></span>

<span data-ttu-id="c99c2-152">一般的なソリューションには、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="c99c2-152">Some popular solutions include:</span></span>

- [<span data-ttu-id="c99c2-153">FSLogix の概要 - FSLogix |Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="c99c2-153">FSLogix Overview - FSLogix | Microsoft Docs</span></span>](/fslogix/overview)
- [<span data-ttu-id="c99c2-154">Citrix プロファイル管理を構成する方法</span><span class="sxs-lookup"><span data-stu-id="c99c2-154">How to Configure Citrix Profile Management</span></span>](https://support.citrix.com/article/CTX222893)

<span data-ttu-id="c99c2-155">また、この方法を使用する場合は、ユーザーがコンピューターにログオンし、プロファイルを移行する際の初期読み込み時間を短縮するために、バックアップされたユーザー フォルダーから不要なフォルダーを除外することが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="c99c2-155">It is also may be recommended that when using this method unnecessary folders be excluded from the backed-up user folder to reduce initial loading times when users are logging on to a machine and the profile is being migrated.</span></span> <span data-ttu-id="c99c2-156">その場合は、サイズを小さくするために、バックアップから次のフォルダーを除外することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c99c2-156">If so, we recommend the following folders be excluded from your backup to reduce size.</span></span>

- <span data-ttu-id="c99c2-157">%LocalAppData%\Microsoft\Edge\User Data\Default\Cache</span><span class="sxs-lookup"><span data-stu-id="c99c2-157">%LocalAppData%\Microsoft\Edge\User Data\Default\Cache</span></span>
- <span data-ttu-id="c99c2-158">%%LocalAppData%\Microsoft\Edge\User Data\Default\Code Cache</span><span class="sxs-lookup"><span data-stu-id="c99c2-158">%LocalAppData%\Microsoft\Edge\User Data\Default\Code Cache</span></span>
- <span data-ttu-id="c99c2-159">%LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsTopSites</span><span class="sxs-lookup"><span data-stu-id="c99c2-159">%LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsTopSites</span></span>
- <span data-ttu-id="c99c2-160">%LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsRecentClosed</span><span class="sxs-lookup"><span data-stu-id="c99c2-160">%LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsRecentClosed</span></span>

## <a name="known-issues"></a><span data-ttu-id="c99c2-161">既知の問題</span><span class="sxs-lookup"><span data-stu-id="c99c2-161">Known issues</span></span>

### <a name="microsoft-edge-crashes-in-older-versions-of-xenapp-and-xendesktop"></a><span data-ttu-id="c99c2-162">XenApp と XenDesktop の以前のバージョンで で Microsoft Edge がクラッシュする</span><span class="sxs-lookup"><span data-stu-id="c99c2-162">Microsoft Edge crashes in older versions of XenApp and XenDesktop</span></span>

<span data-ttu-id="c99c2-163">この問題は新しいバージョンで軽減される必要があります。ただし、お使いの環境でこの問題が発生した場合は、Citrix API Hooks for Edge を無効にして問題を回避できます。「アプリケーションごとに[Citrix API Hooks](https://support.citrix.com/article/CTX107825)を無効にする方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c99c2-163">This issue should be mitigated in newer versions however if you are encountering this issue in your environment, you can work around the issue by disabling Citrix API Hooks for Edge, see [How to Disable Citrix API Hooks on a Per-application Basis.](https://support.citrix.com/article/CTX107825)</span></span>

### <a name="degraded-performance-when-rendering-pages-with-exceptionally-large-html-tables"></a><span data-ttu-id="c99c2-164">非常に大きな HTML テーブルを使用してページをレンダリングする場合のパフォーマンスの低下</span><span class="sxs-lookup"><span data-stu-id="c99c2-164">Degraded performance when rendering pages with exceptionally large HTML tables</span></span>

<span data-ttu-id="c99c2-165">次の Citrix ポリシーは、非常に大きい (30,000 行以上の行数) テーブルを持つ HTML ページのレンダリングを遅くすることが知られています。</span><span class="sxs-lookup"><span data-stu-id="c99c2-165">The following Citrix policies are known to slow rendering of html pages with very large (30,000+ row) tables.</span></span>

- <span data-ttu-id="c99c2-166">キーボードの自動表示</span><span class="sxs-lookup"><span data-stu-id="c99c2-166">Automatic keyboard display</span></span>
- <span data-ttu-id="c99c2-167">コンボ ボックスをリモートで操作する</span><span class="sxs-lookup"><span data-stu-id="c99c2-167">Remote the combo box</span></span>

<span data-ttu-id="c99c2-168">詳細 [については、「モバイル エクスペリエンス ポリシー設定 (citrix.com)」](https://docs.citrix.com/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/mobile-experience-policy-settings.html) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c99c2-168">See [Mobile experience policy settings (citrix.com)](https://docs.citrix.com/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/mobile-experience-policy-settings.html) for more information.</span></span> <span data-ttu-id="c99c2-169">これらのポリシーを無効にすると、問題が軽減されます。</span><span class="sxs-lookup"><span data-stu-id="c99c2-169">Disabling these policies should mitigate the issue.</span></span>

### <a name="windows-account-manager-authorization-scenarios-ie--azure-sync-fail-in-edge-when-run-as-a-citrix-seamless-application"></a><span data-ttu-id="c99c2-170">Windows アカウント マネージャーの承認シナリオ (つまり、 Azure 同期) は、Citrix シームレス アプリケーションとして実行すると Edge で機能しません</span><span class="sxs-lookup"><span data-stu-id="c99c2-170">Windows Account Manager authorization scenarios (i.e.  Azure sync) fail in Edge when run as a Citrix seamless application</span></span>

<span data-ttu-id="c99c2-171">これは、"シームレス" モードで実行するときに初期化されないようにするシナリオに必要な Windows コンポーネントが原因で WAM (Office) を使用する Edge および他のアプリケーションで既知の問題です。</span><span class="sxs-lookup"><span data-stu-id="c99c2-171">This is a known issue in Edge and other applications that use WAM (i.e. Office) due to Windows components necessary for such scenarios not being initialized when running in the “seamless” mode.</span></span> <span data-ttu-id="c99c2-172">この問題を回避するには、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="c99c2-172">To work around this issue:</span></span>

- <span data-ttu-id="c99c2-173">シームレスなリモート アプリケーションとしてではなく、リモート デスクトップ経由で Edge を Citrix ホストに使用します。</span><span class="sxs-lookup"><span data-stu-id="c99c2-173">Use Edge via a Remote Desktop to the Citrix Host instead of as a seamless remote application.</span></span>
- <span data-ttu-id="c99c2-174">代わりに Azure 仮想デスクトップ リモート アプリを使用します。この問題の軽減策になります。</span><span class="sxs-lookup"><span data-stu-id="c99c2-174">Use Azure Virtual Desktop remote apps instead, which has mitigation's for this issue.</span></span>
