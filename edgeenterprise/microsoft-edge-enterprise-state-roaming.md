---
title: Microsoft Edge と Enterprise State Roaming
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 02/14/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge と Enterprise State Roaming
ms.openlocfilehash: 6090ecfda2f792d49e452771943bc6348066a3d8
ms.sourcegitcommit: 90b8eab62edbed0e0a84780abd7d3854bf95c130
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2021
ms.locfileid: "11328059"
---
# <span data-ttu-id="3dbf4-103">Microsoft Edge と Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="3dbf4-103">Microsoft Edge and Enterprise State Roaming</span></span>

<span data-ttu-id="3dbf4-104">この記事では、Enterprise State Roaming (ESR) サービスでの Microsoft Edge の動作がどのように変更され、プラットフォームおよびデバイス間での同期のサポートがどのように向上しているかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-104">This article explains how Microsoft Edge participation in the Enterprise State Roaming (ESR) offering is changing to better support sync across platforms and devices.</span></span>

> [!NOTE]
> <span data-ttu-id="3dbf4-105">この記事は Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="3dbf4-106">はじめに</span><span class="sxs-lookup"><span data-stu-id="3dbf4-106">Introduction</span></span>

<span data-ttu-id="3dbf4-107">Windows 10 を使用することで、[Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) ユーザーは、ユーザー設定とアプリケーション設定のデータをクラウドに安全に同期できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-107">With Windows 10, [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) users gained the ability to securely synchronize their user settings and application settings data to the cloud.</span></span> <span data-ttu-id="3dbf4-108">[Enterprise State Roaming (ESR)](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) は、ユーザーが所有する複数の Windows デバイスで統一されたエクスペリエンスを実現し、新しいデバイスを構成するために必要な時間を短縮します。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-108">[Enterprise State Roaming (ESR)](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) provides users with a unified experience across their Windows devices and reduces the time needed for configuring a new device.</span></span>

<span data-ttu-id="3dbf4-109">Microsoft Edge での Chromium プラットフォーム採用の一環として、Microsoft Edge の同期ソリューションは Windows の同期フレームワークから切り離されました。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-109">As part of Microsoft Edge adopting the Chromium platform, its sync solution is now disconnected from Windows sync framework.</span></span> <span data-ttu-id="3dbf4-110">これは、Microsoft Edge と ESR サービスの関係にも影響します。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-110">This affects the relationship of Microsoft Edge to the ESR offering.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3dbf4-111">新しい Microsoft Edge は、ESR サービスの対象には含まれません。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-111">The new Microsoft Edge does not participate in the ESR offering.</span></span>

## <span data-ttu-id="3dbf4-112">Microsoft Edge の変更点</span><span class="sxs-lookup"><span data-stu-id="3dbf4-112">What’s changing with Microsoft Edge?</span></span>

<span data-ttu-id="3dbf4-113">新しい Microsoft Edge の同期ソリューションは、Windows 同期エコシステムに結び付けられていません。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-113">With the new Microsoft Edge, the sync solution isn’t tied to Windows sync ecosystem.</span></span> <span data-ttu-id="3dbf4-114">これにより、Microsoft は、Windows 7、Windows 8.1、iOS、Android、macOS など、すべてのプラットフォームで Microsoft Edge を提供できます。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-114">This enables us to offer Microsoft Edge across all the platforms, such as Windows 7, Windows 8.1, iOS, Android and macOS.</span></span> <span data-ttu-id="3dbf4-115">また、Windows でプライマリ アカウント以外のアカウントでも同期を実行できます。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-115">This also enables us to offer sync for non-primary accounts on Windows.</span></span> <span data-ttu-id="3dbf4-116">さらに、Windows よりも頻繁かつ柔軟に Microsoft Edge をリリースできます </span><span class="sxs-lookup"><span data-stu-id="3dbf4-116">In addition, we can ship Microsoft Edge at a more frequent and flexible release cadence than Windows.</span></span> <span data-ttu-id="3dbf4-117">(詳しくは、「[次のバージョンの Microsoft Edge をサポートする Windows 更新プログラム](microsoft-edge-sysupdate-windows-updates.md)」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-117">(For more information, see [Windows updates to support the next version of Microsoft Edge](microsoft-edge-sysupdate-windows-updates.md).</span></span> <span data-ttu-id="3dbf4-118">これらの要素はすべて、ESR サービスでの Microsoft Edge の処理を再評価することの必要性を示していました。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-118">All these factors highlighted the need to re-assess Microsoft Edge participation in the ESR offering.</span></span>

<span data-ttu-id="3dbf4-119">ESR は、Windows デバイスのデータの処理方法が約束された、Windows 製品サービスとして構築されていますが、Microsoft Edge の同期は Windows デバイスの枠を越えて実行されます。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-119">ESR is framed as a Windows product offering with promises about how data from Windows devices is handled, but Microsoft Edge sync will extend beyond Windows devices.</span></span> <span data-ttu-id="3dbf4-120">また、これらのデバイス間でデータがローミングされる場合、ESR のコンテキストで Microsoft Edge の動機サービスを定義するのは困難です。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-120">And, as the data roams across these devices, it makes it difficult to define the Microsoft Edge sync offering in the context of ESR.</span></span> <span data-ttu-id="3dbf4-121">同期の動作と管理方法を簡素化するため、および強調されている変更に対応するために、ESR サービスから Microsoft Edge を切り離すことを決定しました。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-121">To simplify how sync works and is managed, and to accommodate the changes that are highlighted, a decision was made to pull Microsoft Edge out of the ESR offering.</span></span>

## <span data-ttu-id="3dbf4-122">これにより、企業は、ESR の一部としての機能を失うことになるのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-122">Does this mean Enterprises will lose the abilities they had as part of ESR?</span></span>

<span data-ttu-id="3dbf4-123">いいえ、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-123">No.</span></span> <span data-ttu-id="3dbf4-124">Microsoft Edge は、ESR サービスで提供されるほとんどの機能を引き続きサポートします。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-124">Microsoft Edge will continue to support most of the abilities provided in the ESR offering.</span></span>

### <span data-ttu-id="3dbf4-125">デバイス間での統一されたエクスペリエンスと新しいデバイスの構成時間</span><span class="sxs-lookup"><span data-stu-id="3dbf4-125">Unified experience across devices and new device configuration time</span></span>

<span data-ttu-id="3dbf4-126">ユーザーが Azure Active Directory (Azure AD アカウント) を使用して Windows デバイスにサインインすると、Microsoft Edge は新しいブラウザーの初回起動時にその ID を暗黙的に継承します。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-126">When a user is signed into their windows device with an Azure Active Directory (Azure AD account), Microsoft Edge will implicitly inherit that Identity on first launch of the new browser.</span></span>

<span data-ttu-id="3dbf4-127">ユーザーが新しい Microsoft Edge で同期を有効にすることに明示的に同意すると、ブラウザーによって、お気に入り、パスワード、履歴などのすべてのブラウザー データが同期されます。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-127">After a user has explicitly consented to turning on sync in the new Microsoft Edge, the browser will sync all the browser data, such as favorites, passwords, and history.</span></span> <span data-ttu-id="3dbf4-128">これにより、デバイス間で統一されたエクスペリエンスが実現され、ブラウザーのパーソナル設定を行うために必要な時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-128">This ensures a unified experience across devices and reduces the time needed to personalize the browser.</span></span>

### <span data-ttu-id="3dbf4-129">企業データとコンシューマー データの分離</span><span class="sxs-lookup"><span data-stu-id="3dbf4-129">Separation of corporate and consumer data</span></span>

<span data-ttu-id="3dbf4-130">組織は組織のデータを管理することができ、企業データがコンシューマー クラウド アカウントに混在したり、コンシューマー データが企業のクラウド アカウントに混在したりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-130">Organizations are in control of their data, and there is no mixing of corporate data in a consumer cloud account or consumer data in an enterprise cloud account.</span></span>

### <span data-ttu-id="3dbf4-131">強化されたセキュリティ</span><span class="sxs-lookup"><span data-stu-id="3dbf4-131">Enhanced security</span></span>

<span data-ttu-id="3dbf4-132">データは、Azure Information Protection を使用してユーザーの Windows 10 デバイスから送信される前に自動的に暗号化され、クラウドでも暗号化されたままです。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-132">Data is automatically encrypted before leaving the user’s Windows 10 device by using Azure Information Protection, and data stays encrypted at rest in the cloud.</span></span> <span data-ttu-id="3dbf4-133">設定名のような名前空間を除き、すべてのコンテンツが暗号化されたままクラウドに保存されます。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-133">All content stays encrypted at rest in the cloud, except for the namespaces, like settings names.</span></span>

### <span data-ttu-id="3dbf4-134">監視</span><span class="sxs-lookup"><span data-stu-id="3dbf4-134">Monitoring</span></span>

<span data-ttu-id="3dbf4-135">Azure AD ポータルとの統合によって、だれが、どのデバイスで、組織内で設定を同期するかを制御し、可視化できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-135">We will provide control and visibility over who syncs settings in your organization and on which devices through integration with the Azure AD portal.</span></span> <span data-ttu-id="3dbf4-136">この機能は、今後のリリースで実現されます。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-136">This capability will be enabled in a future release.</span></span>

### <span data-ttu-id="3dbf4-137">管理</span><span class="sxs-lookup"><span data-stu-id="3dbf4-137">Management</span></span>

<span data-ttu-id="3dbf4-138">管理者は、組織内のどのメンバーが同期を有効にできるかを制御できます。「[Microsoft Edge の同期を構成する](microsoft-edge-enterprise-sync.md#configure-microsoft-edge-sync)」と「[同期グループ ポリシー](microsoft-edge-enterprise-sync.md#sync-group-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-138">Admins will be able to control which members in your organization can enable sync. See [Configure Microsoft Edge sync](microsoft-edge-enterprise-sync.md#configure-microsoft-edge-sync) and [Sync group policies](microsoft-edge-enterprise-sync.md#sync-group-policies).</span></span> <span data-ttu-id="3dbf4-139">さらに、ユーザーは、デバイスごとに同期をオン/オフにしたり、各データ属性の同期を個別に切り替えたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-139">Additionally, users can turn sync on/off for each of their devices as well as toggle each data attribute individually for sync.</span></span>

### <span data-ttu-id="3dbf4-140">キーの管理</span><span class="sxs-lookup"><span data-stu-id="3dbf4-140">Key management</span></span>

<span data-ttu-id="3dbf4-141">同期機能は Azure Information Protection (AIP) を使用して、ユーザーとエンタープライズ管理者についてのみ、同期されたデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-141">The synchronization feature leverages Azure Information Protection (AIP) to protect the synchronized data for only the user and the enterprise admins.</span></span> <span data-ttu-id="3dbf4-142">AIP では、クラウド キー管理用に、Microsoft が管理する (既定) のキーとユーザー独自のキーの両方をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-142">AIP supports both Microsoft managed (default) and bring your own key for cloud-key management.</span></span> <span data-ttu-id="3dbf4-143">組織が使用するクラウド キー管理戦略は Microsoft Edge に対して透過的であり、同期機能には影響しません。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-143">The cloud-key management strategy your organization uses is transparent to Microsoft Edge and has no impact on the synchronization feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3dbf4-144">[Hold Your Own Key (HYOK)](https://docs.microsoft.com/azure/information-protection/configure-adrms-restrictions) と Active Directory Rights Management サービスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-144">[Hold your own key (HYOK)](https://docs.microsoft.com/azure/information-protection/configure-adrms-restrictions) and the Active Directory Rights Management Service aren't supported.</span></span>

## <span data-ttu-id="3dbf4-145">同期属性の概要</span><span class="sxs-lookup"><span data-stu-id="3dbf4-145">Summary of sync attributes</span></span>

<span data-ttu-id="3dbf4-146">次のデータ属性が、初回起動時に Microsoft Edge の新しいバージョンで同期されます。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-146">The following data attributes will sync in the new version of Microsoft Edge at first launch:</span></span>

- <span data-ttu-id="3dbf4-147">お気に入り</span><span class="sxs-lookup"><span data-stu-id="3dbf4-147">Favorites</span></span>
- <span data-ttu-id="3dbf4-148">パスワード</span><span class="sxs-lookup"><span data-stu-id="3dbf4-148">Passwords</span></span>
- <span data-ttu-id="3dbf4-149">フォームの入力情報</span><span class="sxs-lookup"><span data-stu-id="3dbf4-149">Form-fill</span></span>
- <span data-ttu-id="3dbf4-150">履歴</span><span class="sxs-lookup"><span data-stu-id="3dbf4-150">History</span></span>
- <span data-ttu-id="3dbf4-151">開いているタブ (セッション)</span><span class="sxs-lookup"><span data-stu-id="3dbf4-151">Open tabs (sessions)</span></span>
- <span data-ttu-id="3dbf4-152">設定 (基本設定)</span><span class="sxs-lookup"><span data-stu-id="3dbf4-152">Settings (preferences)</span></span>
- <span data-ttu-id="3dbf4-153">拡張機能</span><span class="sxs-lookup"><span data-stu-id="3dbf4-153">Extensions</span></span>

<span data-ttu-id="3dbf4-154">前の属性の一覧は、従来の Microsoft Edge で同期できる属性とは異なります </span><span class="sxs-lookup"><span data-stu-id="3dbf4-154">The preceding list of attributes is different than the attributes that could be synced in Microsoft Edge Legacy.</span></span> <span data-ttu-id="3dbf4-155">(従来の Microsoft Edge の設定の詳細については、[Windows 10 ローミング設定](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-windows-settings-reference)に関するトピックを参照してください)。ユーザーは、Microsoft Edge の設定を使用して、これらの属性を選択的に有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-155">(For details about Microsoft Edge Legacy settings, see [Windows 10 roaming settings](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-windows-settings-reference).) Users can selectively enable/disable these attributes using Microsoft Edge settings.</span></span> <span data-ttu-id="3dbf4-156">2つのバージョン間での属性の違い (履歴など) によって、ユーザーはもう一度同期に関する同意を求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-156">Given the difference in attributes between the two versions (for example, history), users might be asked to give sync consent again.</span></span>

> [!NOTE]
> <span data-ttu-id="3dbf4-157">従来の Microsoft Edge とは異なり、新しい Microsoft Edge はパスワードの管理に Windows 資格情報マネージャーを使用しないため、Windows 資格情報マネージャーを使用する Internet Explorer やその他のアプリとパスワードを同期しません。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-157">Unlike Microsoft Edge Legacy, the new Microsoft Edge doesn't use Windows credential Manager for passwords and as a result, won't sync passwords with Internet Explorer or other apps that use Windows Credential manager.</span></span>

## <span data-ttu-id="3dbf4-158">サービス条件</span><span class="sxs-lookup"><span data-stu-id="3dbf4-158">Terms of service</span></span>

<span data-ttu-id="3dbf4-159">Microsoft Edge 同期のサービス条件は、Microsoft Edge で *edge://terms* にアクセスすると表示される Microsoft ソフトウェア ライセンスに従います。</span><span class="sxs-lookup"><span data-stu-id="3dbf4-159">Terms of service for Microsoft Edge sync falls under the Microsoft software license viewable in Microsoft Edge at *edge://terms*.</span></span>

## <span data-ttu-id="3dbf4-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="3dbf4-160">See also</span></span>

- [<span data-ttu-id="3dbf4-161">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="3dbf4-161">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="3dbf4-162">Microsoft Edge の同期</span><span class="sxs-lookup"><span data-stu-id="3dbf4-162">Microsoft Edge Sync</span></span>](microsoft-edge-enterprise-sync.md)