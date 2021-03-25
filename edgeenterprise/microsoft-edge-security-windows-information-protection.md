---
title: Windows 情報保護のための Microsoft Edge のサポート
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 04/24/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Windows 情報保護のための Microsoft Edge のサポート
ms.openlocfilehash: a9981947462627ae4884f18f4df6accf2ee60f12
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447191"
---
# <a name="microsoft-edge-support-for-windows-information-protection-wip"></a><span data-ttu-id="d415e-103">Windows 情報保護 (WIP) のための Microsoft Edge のサポート</span><span class="sxs-lookup"><span data-stu-id="d415e-103">Microsoft Edge support for Windows Information Protection (WIP)</span></span>

<span data-ttu-id="d415e-104">この記事では、Microsoft Edge が Windows 情報保護 (WIP) をサポートする方法をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d415e-104">This article describes how Microsoft Edge supports Windows Information Protection (WIP).</span></span>

> [!NOTE]
> <span data-ttu-id="d415e-105">これは、Microsoft Edge version 81 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d415e-105">This applies to Microsoft Edge version 81 or later.</span></span>

## <a name="overview"></a><span data-ttu-id="d415e-106">概要</span><span class="sxs-lookup"><span data-stu-id="d415e-106">Overview</span></span>

<span data-ttu-id="d415e-107">Windows 情報保護 (WIP) は Windows 10 の機能で、不正または偶発的な漏洩から企業データを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d415e-107">Windows Information Protection (WIP) is a Windows 10 feature that helps protect enterprise data from unauthorized or accidental disclosure.</span></span> <span data-ttu-id="d415e-108">リモート ワークの台頭により、企業のデータを職場外で共有するリスクが高まっています。</span><span class="sxs-lookup"><span data-stu-id="d415e-108">With the rise of remote work, there's an increased risk of sharing corporate data outside the workplace.</span></span> <span data-ttu-id="d415e-109">このリスクは、個人の活動や仕事による活動が企業のデバイス上で発生した場合に増加します。</span><span class="sxs-lookup"><span data-stu-id="d415e-109">This risk increases when personal activities and work activities occur on corporate devices.</span></span>

<span data-ttu-id="d415e-110">Microsoft Edge は、ユーザーがコンテンツを共有し、配信することが多い Web 環境でのコンテンツ保護を支援するために、WIP をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d415e-110">Microsoft Edge supports WIP to help protect content in a web environment where users often share and distribute content.</span></span>

### <a name="system-requirements"></a><span data-ttu-id="d415e-111">システム要件</span><span class="sxs-lookup"><span data-stu-id="d415e-111">System requirements</span></span>

<span data-ttu-id="d415e-112">企業内で WIP を使用するデバイスには、以下の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d415e-112">The follow requirements apply to devices using WIP in the enterprise:</span></span>

- <span data-ttu-id="d415e-113">Windows 10 バージョン 1607 以降</span><span class="sxs-lookup"><span data-stu-id="d415e-113">Windows 10, version 1607 or later</span></span>
- <span data-ttu-id="d415e-114">Windows クライアント SKU のみ</span><span class="sxs-lookup"><span data-stu-id="d415e-114">Only Windows client SKUs</span></span>
- <span data-ttu-id="d415e-115">[WIP の前提条件](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip#prerequisites)に記載されている管理ソリューションのいずれか</span><span class="sxs-lookup"><span data-stu-id="d415e-115">One of the management solutions described in [WIP prerequisites](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip#prerequisites)</span></span>

### <a name="windows-information-protection-benefits"></a><span data-ttu-id="d415e-116">Windows 情報保護のメリット</span><span class="sxs-lookup"><span data-stu-id="d415e-116">Windows Information Protection benefits</span></span>

<span data-ttu-id="d415e-117">WIP には、次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="d415e-117">WIP provides the following benefits:</span></span>

- <span data-ttu-id="d415e-118">個人と企業データが明確に分離されるため、従業員が環境またはアプリを切り替える必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d415e-118">Obvious separation between personal and corporate data, without requiring employees to switch environments or apps.</span></span>
- <span data-ttu-id="d415e-119">アプリを更新することなく、既存の基幹業務アプリのデータ保護が強化されます。</span><span class="sxs-lookup"><span data-stu-id="d415e-119">Additional data protection for existing line-of-business apps without a need to update the apps.</span></span>
- <span data-ttu-id="d415e-120">Intune Mobile Device Management (MDM) に登録されたデバイスから企業データをリモート ワイプし、個人データに影響を与えないようにします。</span><span class="sxs-lookup"><span data-stu-id="d415e-120">The ability to remote wipes corporate data from Intune Mobile Device Management (MDM) enrolled devices while leaving personal data unaffected.</span></span> 
- <span data-ttu-id="d415e-121">監査レポートを通して問題の追跡や、ユーザーへのコンプライアンス トレーニングなどの改善措置を行います。</span><span class="sxs-lookup"><span data-stu-id="d415e-121">Audit reports for tracking issues and for remedial actions such as compliance training for users.</span></span>
- <span data-ttu-id="d415e-122">既存の管理システムとの統合により、WIP の構成、展開、管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d415e-122">Integration with your existing management system to configure, deploy, and manage WIP.</span></span> <span data-ttu-id="d415e-123">いくつかの例としては、Microsoft Intune、Microsoft Endpoint Configuration Manager、または現在ご利用のモバイル デバイス管理 (MDM) システムがあります。</span><span class="sxs-lookup"><span data-stu-id="d415e-123">Some examples are Microsoft Intune, Microsoft Endpoint Configuration Manager, or your current mobile device management (MDM) system.</span></span>

## <a name="wip-policy-and-protection-modes"></a><span data-ttu-id="d415e-124">WIP ポリシーと保護モード</span><span class="sxs-lookup"><span data-stu-id="d415e-124">WIP policy and protection modes</span></span>

<span data-ttu-id="d415e-125">ポリシーを使用して、次の表で説明されている 4 つの保護モードを構成できます。</span><span class="sxs-lookup"><span data-stu-id="d415e-125">Using policies, you can configure the four protection modes described in the following table.</span></span> <span data-ttu-id="d415e-126">詳細については、「[WIP 保護モード](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip#wip-protection-modes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d415e-126">For more information, see [WIP-protection modes](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip#wip-protection-modes).</span></span>

| <span data-ttu-id="d415e-127">モード</span><span class="sxs-lookup"><span data-stu-id="d415e-127">Mode</span></span> | <span data-ttu-id="d415e-128">説明</span><span class="sxs-lookup"><span data-stu-id="d415e-128">Description</span></span> |
|------|-------------|
| <span data-ttu-id="d415e-129">ブロック</span><span class="sxs-lookup"><span data-stu-id="d415e-129">Block</span></span> | <span data-ttu-id="d415e-130">WIP によって不適切なデータ共有操作が検出され、従業員がその操作を完了することは禁止されます。</span><span class="sxs-lookup"><span data-stu-id="d415e-130">WIP looks for inappropriate data sharing practices and stops the employee from completing the action.</span></span> <span data-ttu-id="d415e-131">この検索では、アプリ間での企業データの共有や、組織のネットワーク外部との共有の実行に加え、企業で保護されていないアプリとの企業データの共有も対象となります。</span><span class="sxs-lookup"><span data-stu-id="d415e-131">This search can include sharing enterprise data to non-enterprise-protected apps in addition to sharing enterprise data between apps or attempting to share outside of your organization's network.</span></span> |
| <span data-ttu-id="d415e-132">上書きの許可</span><span class="sxs-lookup"><span data-stu-id="d415e-132">Allow Overrides</span></span> | <span data-ttu-id="d415e-133">WIP によって不適切なデータ共有が検出され、危険と見なされる操作を従業員が実行しようとすると警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d415e-133">WIP looks for inappropriate data sharing, warning employees if they do something deemed potentially unsafe.</span></span> <span data-ttu-id="d415e-134">ただし、この管理モードでは、従業員はポリシーを上書きしてデータを共有でき、従業員が行った操作が監査ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="d415e-134">However, this management mode lets the employee override the policy and share the data, logging the action to your audit log.</span></span> |
| <span data-ttu-id="d415e-135">Silent</span><span class="sxs-lookup"><span data-stu-id="d415e-135">Silent</span></span> | <span data-ttu-id="d415e-136">WIP がメッセージを表示せずに実行され、上書きの許可モードであれば従業員による対話操作を要求する操作を一切禁止せずに、不適切なデータ共有をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="d415e-136">WIP runs silently, logging inappropriate data sharing, without stopping anything that would have been prompted for employee interaction while in Allow Overrides mode.</span></span> <span data-ttu-id="d415e-137">ネットワーク リソースや WIP で保護されたデータにアプリから不適切にアクセスしようとした場合など、許可されていない操作は引き続き禁止されます。</span><span class="sxs-lookup"><span data-stu-id="d415e-137">Unallowed actions, like apps inappropriately trying to access a network resource or WIP-protected data, are still stopped.</span></span> |
| <span data-ttu-id="d415e-138">オフ</span><span class="sxs-lookup"><span data-stu-id="d415e-138">Off</span></span> | <span data-ttu-id="d415e-139">WIP がオフになり、データの保護や監査は行われません。</span><span class="sxs-lookup"><span data-stu-id="d415e-139">WIP is turned off and doesn't help to protect or audit your data.</span></span> <span data-ttu-id="d415e-140">WIP を無効にすると、ローカルで接続されたドライブ上にある WIP タグの付いたファイルに対して暗号化の解除が試みられます。</span><span class="sxs-lookup"><span data-stu-id="d415e-140">After you turn off WIP, an attempt is made to decrypt any WIP-tagged files on the locally attached drives.</span></span> <span data-ttu-id="d415e-141">WIP 保護を再び有効にしても、以前の復号化とポリシーの情報は自動的には再適用されません。</span><span class="sxs-lookup"><span data-stu-id="d415e-141">Your previous decryption and policy info isn't automatically reapplied if you turn WIP protection back on.</span></span>
 |

## <a name="wip-features-supported-in-microsoft-edge"></a><span data-ttu-id="d415e-142">Microsoft Edge でサポートされている WIP の機能</span><span class="sxs-lookup"><span data-stu-id="d415e-142">WIP features supported in Microsoft Edge</span></span>

<span data-ttu-id="d415e-143">Microsoft Edge バージョン 81 以降では、次の機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d415e-143">Starting with Microsoft Edge version 81, the following features are supported:</span></span>

- <span data-ttu-id="d415e-144">ワーク サイトは、アドレス バーに表示されたブリーフケースのアイコンで示されます。</span><span class="sxs-lookup"><span data-stu-id="d415e-144">Work sites will be indicated by a briefcase icon on the address bar.</span></span>  
- <span data-ttu-id="d415e-145">作業場所からダウンロードされたファイルは自動的に暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="d415e-145">Files downloaded from a work location are automatically encrypted.</span></span>
- <span data-ttu-id="d415e-146">作業場所以外の場所への仕事用ファイルのアップロードには、サイレント、ブロック、上書きが強制適用されます。</span><span class="sxs-lookup"><span data-stu-id="d415e-146">Silent/Block/Override enforcement for work file uploads to non-work locations.</span></span>  
- <span data-ttu-id="d415e-147">ファイルのドラッグ アンド ドロップ操作には、サイレント、ブロック、上書きが強制適用されます。</span><span class="sxs-lookup"><span data-stu-id="d415e-147">Silent/Block/Override enforcement for file Drag & Drop actions.</span></span>
- <span data-ttu-id="d415e-148">クリップボード操作には、サイレント、ブロック、上書きが強制適用されます。</span><span class="sxs-lookup"><span data-stu-id="d415e-148">Silent/Block/Override enforcement for Clipboard actions.</span></span>
- <span data-ttu-id="d415e-149">仕事用プロファイル以外のプロファイルからの作業場所の閲覧は、自動的に仕事用プロファイルへとリダイレクトされます (Azure AD の ID に関連付けられています)。</span><span class="sxs-lookup"><span data-stu-id="d415e-149">Browsing to work locations from non-work profiles automatically redirects to the Work Profile (associated with the Azure AD Identity.)</span></span>
- <span data-ttu-id="d415e-150">IE モードは、WIP 機能を完全にサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d415e-150">IE Mode supports full WIP functionality.</span></span>

## <a name="working-with-wip-in-microsoft-edge"></a><span data-ttu-id="d415e-151">Microsoft Edge での WIP の使用</span><span class="sxs-lookup"><span data-stu-id="d415e-151">Working with WIP in Microsoft Edge</span></span>

<span data-ttu-id="d415e-152">Microsoft Edge で WIP サポートが有効になると、ユーザーが仕事関連の情報にアクセスしたときに表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="d415e-152">After WIP support is enabled for Microsoft Edge, users will see when work-related information is accessed.</span></span> <span data-ttu-id="d415e-153">次のスクリーンショットでは、アドレス バーにブリーフケースのアイコンが表示されており、ブラウザ経由で仕事関連の情報にアクセスしていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="d415e-153">The next screenshot shows the briefcase icon in the address bar, indicating that work-related information is accessed via the browser.</span></span>

 !["仕事" としてマークされているサイトのアドレス バー インジケーター](./media/microsoft-edge-security-windows-information-protection/microsoft-edge-wip-notify.png)

<span data-ttu-id="d415e-155">Microsoft Edge では、未承認のウェブサイトの保護されたコンテンツを共有する機能をユーザーに提供しています。</span><span class="sxs-lookup"><span data-stu-id="d415e-155">Microsoft Edge gives users the ability to share protected content in an unapproved website.</span></span> <span data-ttu-id="d415e-156">次のスクリーンショットは、保護されたコンテンツを未承認のウェブサイトで使用できるようにする Microsoft Edge のプロンプトを示しています。</span><span class="sxs-lookup"><span data-stu-id="d415e-156">The next screenshot shows the Microsoft Edge prompt that allows a user to use protected content in an unapproved website.</span></span>

 ![保護されたコンテンツの上書きを要求する](./media/microsoft-edge-security-windows-information-protection/microsoft-edge-wip-override.png)

## <a name="configure-policies-to-support-wip"></a><span data-ttu-id="d415e-158">WIP をサポートするようにポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="d415e-158">Configure policies to support WIP</span></span>

<span data-ttu-id="d415e-159">Microsoft Edge で WIP を使用するには、仕事用プロファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="d415e-159">Using WIP with Microsoft Edge requires the presence of a work profile.</span></span>

### <a name="ensure-the-presence-of-a-work-profile"></a><span data-ttu-id="d415e-160">仕事用プロファイルの存在を確認する</span><span class="sxs-lookup"><span data-stu-id="d415e-160">Ensure the presence of a work profile</span></span>

<span data-ttu-id="d415e-161">ハイブリッドに参加しているコンピューターでは、Microsoft Edge は Azure Active Directory (Azure AD) アカウントで自動的にサインインされます。</span><span class="sxs-lookup"><span data-stu-id="d415e-161">On hybrid joined machines, Microsoft Edge is automatically signed in with the Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="d415e-162">WIP に必要なこのプロファイルをユーザーが削除しないようにするために、次のポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="d415e-162">To make sure that users don't remove this profile, which is needed for WIP, configure the following policy:</span></span>

- [<span data-ttu-id="d415e-163">NonRemovableProfileEnabled</span><span class="sxs-lookup"><span data-stu-id="d415e-163">NonRemovableProfileEnabled</span></span>](./microsoft-edge-policies.md#nonremovableprofileenabled)

> [!NOTE]
> <span data-ttu-id="d415e-164">ハイブリッドに参加していない環境でご利用の場合は、「[Plan your hybrid Azure Active Directory join implementation (ハイブリッド Azure Active Directory への参加の実装を計画する)](/azure/active-directory/devices/hybrid-azuread-join-plan)」の手順を使用してハイブリッドに参加することができます。</span><span class="sxs-lookup"><span data-stu-id="d415e-164">If your environment isn't hybrid joined, you can hybrid join using these instructions: [Plan your hybrid Azure Active Directory join implementation](/azure/active-directory/devices/hybrid-azuread-join-plan).</span></span>

<span data-ttu-id="d415e-165">ハイブリッド参加がオプションではない場合は、オンプレミスの Active Directory アカウントを使用して、Microsoft Edge がユーザーのドメイン アカウントを使用して特別な仕事用プロファイルを自動的に作成できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d415e-165">If hybrid joining isn't an option, you can use on-prem Active Directory accounts to allow Microsoft Edge to auto create a special work profile with the users' domain accounts.</span></span> <span data-ttu-id="d415e-166">オンプレミス アカウントでは、クラウド同期、Office NTP など、Azure AD の機能のすべてを受け取ることが不可能な場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d415e-166">Note that on-premises accounts may not receive all of Azure AD's features, such as cloud sync, Office NTP, and so on.)</span></span>

#### <a name="active-directory-ad-accounts"></a><span data-ttu-id="d415e-167">Active Directory (AD) アカウント</span><span class="sxs-lookup"><span data-stu-id="d415e-167">Active Directory (AD) accounts</span></span>

<span data-ttu-id="d415e-168">AD アカウントの場合、Microsoft Edge に特別な仕事用プロファイルを自動作成させるには、次のポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d415e-168">For AD accounts, you must configure the following policy to have the Microsoft Edge auto create a special work profile.</span></span>

- [<span data-ttu-id="d415e-169">ConfigureOnPremisesAccountAutoSignIn</span><span class="sxs-lookup"><span data-stu-id="d415e-169">ConfigureOnPremisesAccountAutoSignIn</span></span>](./microsoft-edge-policies.md#configureonpremisesaccountautosignin)

### <a name="windows-policies-for-wip"></a><span data-ttu-id="d415e-170">WIP のための Windows ポリシー</span><span class="sxs-lookup"><span data-stu-id="d415e-170">Windows policies for WIP</span></span>

<span data-ttu-id="d415e-171">Windows ポリシーを使用して、WIP を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="d415e-171">You can configure WIP using Windows policies.</span></span> <span data-ttu-id="d415e-172">詳細については、「[Create and deploy WIP policies using Microsoft Intune (Microsoft Intune を使用して WIP ポリシーを作成して展開する)](/windows/security/information-protection/windows-information-protection/overview-create-wip-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d415e-172">For more information, see [Create and deploy WIP policies using Microsoft Intune](/windows/security/information-protection/windows-information-protection/overview-create-wip-policy)</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="d415e-173">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="d415e-173">Frequently Asked Questions</span></span>

### <a name="how-do-i-resolve-error-code--2147024540"></a><span data-ttu-id="d415e-174">エラー コード -2147024540 の解決方法を教えてください</span><span class="sxs-lookup"><span data-stu-id="d415e-174">How do I resolve Error Code -2147024540?</span></span>

<span data-ttu-id="d415e-175">このエラーコードは、次の Windows 情報保護エラーに対応しています: *ERROR_EDP_POLICY_DENIES_OPERATION: 要求された操作は Windows 情報保護ポリシーによってブロックされました。詳細については、システム管理者に問い合わせてください。*</span><span class="sxs-lookup"><span data-stu-id="d415e-175">This error code corresponds to the following Windows Information Protection error: *ERROR_EDP_POLICY_DENIES_OPERATION: The requested operation was blocked by Windows Information Protection policy. For more information, contact your system administrator.*</span></span>

<span data-ttu-id="d415e-176">組織で Windows 情報保護 (WIP) が有効になっており、承認されたアプリケーションを使用するユーザーのみに企業リソースへのアクセスが許可されている場合に、Microsoft Edge によってこのエラーが示されます。</span><span class="sxs-lookup"><span data-stu-id="d415e-176">Microsoft Edge shows this error when the organization has enabled Windows Information Protection (WIP) to only allow users with approved applications to access corporate resources.</span></span> <span data-ttu-id="d415e-177">この場合、承認されたアプリケーションの一覧に Microsoft Edge がないため、管理者は Microsoft Edge へのアクセスが許可されるように WIP ポリシーを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d415e-177">In this case because Microsoft Edge isn't on the approved applications list, the admin will have to update the WIP policies to grant access to Microsoft Edge.</span></span>

<span data-ttu-id="d415e-178">次のスクリーンショットは、Microsoft Intune を使用して Microsoft Edge を許可された WIP 用アプリとして追加するための方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d415e-178">The following screenshot shows how the Microsoft Intune is used to add Microsoft Edge as an allowed app for WIP.</span></span>

 ![Microsoft Intune のダイアログで、Microsoft Edge を WIP 用アプリとして追加します。](./media/microsoft-edge-security-windows-information-protection/microsoft-edge-wip-exemption.png)

<span data-ttu-id="d415e-180">Microsoft Intune を使用していない場合は、[WIP Enterprise AppLocker Policy](https://download.microsoft.com/download/8/9/9/8995d820-065c-4ab1-aa2a-9d6dc0cd7ffa/MsEdge%20-%20WIP%20Enterprise%20AppLocker%20Policy%20Files.zip) ファイルに含まれているポリシー更新をダウンロードして適用してください。</span><span class="sxs-lookup"><span data-stu-id="d415e-180">If you're not using Microsoft Intune, download and apply the policy update in the [WIP Enterprise AppLocker Policy](https://download.microsoft.com/download/8/9/9/8995d820-065c-4ab1-aa2a-9d6dc0cd7ffa/MsEdge%20-%20WIP%20Enterprise%20AppLocker%20Policy%20Files.zip) file.</span></span>

## <a name="see-also"></a><span data-ttu-id="d415e-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="d415e-181">See also</span></span>

- [<span data-ttu-id="d415e-182">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="d415e-182">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise) 
- [<span data-ttu-id="d415e-183">Windows 情報保護を使用して企業データを保護する</span><span class="sxs-lookup"><span data-stu-id="d415e-183">Protect enterprise data using Windows Information Protection</span></span>](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)