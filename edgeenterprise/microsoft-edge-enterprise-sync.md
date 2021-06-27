---
title: Microsoft Edge エンタープライズの同期を構成する
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 03/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: お気に入り、パスワード、およびその他のブラウザー データを同期するように Microsoft Edge を構成するための管理者およびユーザー オプション。
ms.openlocfilehash: 99edc97bd5f4bab7bf421e0d15e512c5f6f76cc0
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617757"
---
# <a name="configure-microsoft-edge-enterprise-sync"></a><span data-ttu-id="7d458-103">Microsoft Edge エンタープライズの同期を構成する</span><span class="sxs-lookup"><span data-stu-id="7d458-103">Configure Microsoft Edge enterprise sync</span></span>

<span data-ttu-id="7d458-104">この記事では、管理者が Microsoft Edge を構成して、サインインしているすべてのデバイス間でユーザーのお気に入り、パスワード、その他のブラウザー データを同期する方法について説明します。管理者でない場合は、サインインしてデバイス間で Microsoft Edge を同期する方法についてこの記事にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="7d458-104">This article explains how admins can configure Microsoft Edge to sync user favorites, passwords, and other browser data across all signed-in devices.If you are not an admin, please visit this article for how to sign-in and sync Microsoft Edge across devices.</span></span> <span data-ttu-id="7d458-105">[サインインして、デバイス間で Microsoft Edge を同期します](https://support.microsoft.com/microsoft-edge/sign-in-to-sync-microsoft-edge-across-devices-e6ffa79b-ed52-aa32-47e2-5d5597fe4674)。</span><span class="sxs-lookup"><span data-stu-id="7d458-105">[Sign in to sync Microsoft Edge across devices](https://support.microsoft.com/microsoft-edge/sign-in-to-sync-microsoft-edge-across-devices-e6ffa79b-ed52-aa32-47e2-5d5597fe4674).</span></span>

> [!NOTE]
> <span data-ttu-id="7d458-106">この記事は、特に指定されない限り、Microsoft Edge バージョン 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7d458-106">Applies to Microsoft Edge version 77 or later unless otherwise noted.</span></span>

## <a name="overview"></a><span data-ttu-id="7d458-107">概要</span><span class="sxs-lookup"><span data-stu-id="7d458-107">Overview</span></span>

<span data-ttu-id="7d458-108">Microsoft Edge の同期を使用すると、ユーザーは、サインインしているすべてのデバイスで閲覧データにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7d458-108">Microsoft Edge sync enables users to access their browsing data across all their signed-in devices.</span></span> <span data-ttu-id="7d458-109">同期でサポートされるデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7d458-109">The data supported by sync includes:</span></span>

- <span data-ttu-id="7d458-110">お気に入り</span><span class="sxs-lookup"><span data-stu-id="7d458-110">Favorites</span></span>
- <span data-ttu-id="7d458-111">パスワード</span><span class="sxs-lookup"><span data-stu-id="7d458-111">Passwords</span></span>
- <span data-ttu-id="7d458-112">住所など (フォームの入力情報)</span><span class="sxs-lookup"><span data-stu-id="7d458-112">Addresses and more (form-fill)</span></span>
- <span data-ttu-id="7d458-113">コレクション</span><span class="sxs-lookup"><span data-stu-id="7d458-113">Collections</span></span>
- <span data-ttu-id="7d458-114">設定</span><span class="sxs-lookup"><span data-stu-id="7d458-114">Settings</span></span>
- <span data-ttu-id="7d458-115">拡張機能</span><span class="sxs-lookup"><span data-stu-id="7d458-115">Extension</span></span>
- <span data-ttu-id="7d458-116">タブを開く (Microsoft Edge バージョン 88 で利用可能)</span><span class="sxs-lookup"><span data-stu-id="7d458-116">Open tabs (available in Microsoft Edge version 88)</span></span>
- <span data-ttu-id="7d458-117">履歴 (Microsoft Edge バージョン 88 で利用可能)</span><span class="sxs-lookup"><span data-stu-id="7d458-117">History (available in Microsoft Edge version 88)</span></span>

<span data-ttu-id="7d458-118">同期機能はユーザーの同意によって有効になり、ユーザーは上記の各データ タイプについて同期をオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="7d458-118">Sync functionality is enabled via user consent and users can turn sync on or off for each of the data types listed above.</span></span> <span data-ttu-id="7d458-119">ユーザーに同期に関する問題が発生している場合は、**[設定]** > **[プロファイル]** > **[同期のリセット]** の順に移動して同期をリセットする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="7d458-119">If a user is experiencing a sync issue they might need to reset sync in **Settings** > **Profiles** > **Reset sync**.</span></span>

> [!NOTE]
> <span data-ttu-id="7d458-120">同期機能をサポートするために、デバイスの接続および構成データ (デバイス名、製造元、モデルなど) がアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="7d458-120">Additional device connectivity and configuration data (such as device name, make and model) is uploaded to support sync functionality.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7d458-121">前提条件</span><span class="sxs-lookup"><span data-stu-id="7d458-121">Prerequisites</span></span>

<span data-ttu-id="7d458-122">Azure Active Directory (Azure AD) アカウントでの Microsoft Edge の同期は、次のサブスクリプションのいずれかで使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d458-122">Microsoft Edge sync for Azure Active Directory (Azure AD) accounts is available for any of the following subscriptions:</span></span>

- <span data-ttu-id="7d458-123">Azure AD Premium (P1 または P2)</span><span class="sxs-lookup"><span data-stu-id="7d458-123">Azure AD Premium (P1 or P2)</span></span>
- <span data-ttu-id="7d458-124">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="7d458-124">M365 Business Premium</span></span>
- <span data-ttu-id="7d458-125">Office 365 E1 以上</span><span class="sxs-lookup"><span data-stu-id="7d458-125">Office 365 E1 and above</span></span>
- <span data-ttu-id="7d458-126">Azure Information Protection (AIP) (P1 または P2)</span><span class="sxs-lookup"><span data-stu-id="7d458-126">Azure Information Protection (AIP) (P1 or P2)</span></span>
- <span data-ttu-id="7d458-127">すべての EDU サブスクリプション (学生または教職員向けの Microsoft Apps、学生または教職員向けの Exchange Online、O365 A1 以上、M365 A1 以上、学生または教職員向けの Azure Information Protection P1 または P2)</span><span class="sxs-lookup"><span data-stu-id="7d458-127">All EDU subscriptions (Microsoft Apps for Students or Faculty, Exchange Online for Students or Faculty, O365 A1 or above, M365 A1 or above, or Azure Information Protection P1 or P2 for Students or Faculty)</span></span>

## <a name="sync-group-policies"></a><span data-ttu-id="7d458-128">同期グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="7d458-128">Sync group policies</span></span>

<span data-ttu-id="7d458-129">管理者は、Microsoft Edge の同期を構成および管理するために、次のグループ ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d458-129">Admins can use the following group policies to configure and manage Microsoft Edge sync:</span></span>

- <span data-ttu-id="7d458-130">[SyncDisabled](./microsoft-edge-policies.md#syncdisabled): 同期を完全に無効にします。</span><span class="sxs-lookup"><span data-stu-id="7d458-130">[SyncDisabled](./microsoft-edge-policies.md#syncdisabled): Disables sync completely.</span></span>
- <span data-ttu-id="7d458-131">[SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled): 閲覧の履歴と同期の保存を無効にします。このポリシーにより、オープン タブの同期も無効になります。</span><span class="sxs-lookup"><span data-stu-id="7d458-131">[SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled): Disables saving browsing history and sync. This policy also disables open-tabs sync.</span></span>
- <span data-ttu-id="7d458-132">[AllowDeletingBrowserHistory](./microsoft-edge-policies.md#allowdeletingbrowserhistory): このポリシーを無効に設定すると、履歴の同期も無効になります。</span><span class="sxs-lookup"><span data-stu-id="7d458-132">[AllowDeletingBrowserHistory](./microsoft-edge-policies.md#allowdeletingbrowserhistory): When this policy is set to disabled, history sync will also be disabled.</span></span>
- <span data-ttu-id="7d458-133">[SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled): 同期から除外されるタイプの一覧を構成します。</span><span class="sxs-lookup"><span data-stu-id="7d458-133">[SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled): Configure the list of types that are excluded from synchronization.</span></span>
- <span data-ttu-id="7d458-134">[RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled): Active Directory (AD) プロファイルがオンプレミスの記憶域を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="7d458-134">[RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled): Allow Active Directory (AD) profiles to use on-premises storage.</span></span> <span data-ttu-id="7d458-135">詳細については、「[Active Directory (AD) ユーザー用のオンプレミス同期](./microsoft-edge-on-premises-sync.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d458-135">For more information, see [On-premises sync for Active Directory (AD) users](./microsoft-edge-on-premises-sync.md).</span></span>
- <span data-ttu-id="7d458-136">[ForceSync](/deployedge/microsoft-edge-policies#forcesync): 既定で同期をオンにします。同期にはユーザーの同意を必要としません。</span><span class="sxs-lookup"><span data-stu-id="7d458-136">[ForceSync](/deployedge/microsoft-edge-policies#forcesync): Turn on sync by default and do not require user consent to sync.</span></span>  

## <a name="configure-microsoft-edge-sync"></a><span data-ttu-id="7d458-137">Microsoft Edge を構成する</span><span class="sxs-lookup"><span data-stu-id="7d458-137">Configure Microsoft Edge sync</span></span>

<span data-ttu-id="7d458-138">Microsoft Edge の同期の構成オプションは、Azure Information Protection (AIP) サービスを介して利用できます。</span><span class="sxs-lookup"><span data-stu-id="7d458-138">Configuration options for Microsoft Edge sync are available through the Azure Information Protection (AIP) service.</span></span> <span data-ttu-id="7d458-139">テナントの AIP が有効になっている場合、ライセンスに関係なくすべてのユーザーが Microsoft Edge のデータを同期できます。</span><span class="sxs-lookup"><span data-stu-id="7d458-139">When AIP is enabled for a tenant, all users can sync Microsoft Edge data, regardless of licensing.</span></span> <span data-ttu-id="7d458-140">AIP を有効にする方法は、[ここ](/azure/information-protection/activate-office365)で説明されています。</span><span class="sxs-lookup"><span data-stu-id="7d458-140">Instructions on how to enable AIP can be found [here](/azure/information-protection/activate-office365).</span></span>

<span data-ttu-id="7d458-141">特定のユーザー セットに対して同期を制限するために、これらのユーザーに対して [AIP のオンボード制御ポリシー](/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?preserve-view=true&view=azureipps) を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7d458-141">To restrict sync to certain set of users, you can enable the [AIP onboarding control policy](/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?preserve-view=true&view=azureipps) for those users.</span></span> <span data-ttu-id="7d458-142">必要なユーザーがすべてオンボードされた後でも同期ができない場合には、[Get-AIPServiceIPCv3](/powershell/module/aipservice/get-aipserviceipcv3?preserve-view=true&view=azureipps) PowerShell コマンドレット を使用して IPCv3Service が有効になっていることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="7d458-142">If sync is still not available after ensuring that all necessary users are onboarded, ensure that the IPCv3Service is enabled using the [Get-AIPServiceIPCv3](/powershell/module/aipservice/get-aipserviceipcv3?preserve-view=true&view=azureipps)  PowerShell cmdlet.</span></span>

> [!CAUTION]
> <span data-ttu-id="7d458-143">Azure Information Protection を有効にすると、AIP を使用してコンテンツを保護するために Microsoft Word や Microsoft Outlook などの他のアプリケーションも許可されます。</span><span class="sxs-lookup"><span data-stu-id="7d458-143">Activating Azure Information Protection will also allow other applications, such as Microsoft Word or Microsoft Outlook, to protect content with AIP.</span></span> <span data-ttu-id="7d458-144">また、Microsoft Edge 同期を制限するために使用されるオンボード制御ポリシーは、他のアプリケーションが AIP を使用してコンテンツを保護することも制限します。</span><span class="sxs-lookup"><span data-stu-id="7d458-144">In addition, any onboarding control policy used to restrict Edge sync will also restrict other applications from protecting content using AIP.</span></span>

## <a name="microsoft-edge-and-enterprise-state-roaming-esr"></a><span data-ttu-id="7d458-145">Microsoft Edge と Enterprise State Roaming (ESR)</span><span class="sxs-lookup"><span data-stu-id="7d458-145">Microsoft Edge and Enterprise State Roaming (ESR)</span></span>

<span data-ttu-id="7d458-146">新しい Microsoft Edge は、ユーザー データの同期の範囲をすべてのデバイスに拡張したクロスプラットフォーム アプリケーションであり、Azure AD Enterprise State Roaming の一部ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="7d458-146">Microsoft Edge is a cross-platform application with an expanded scope for syncing user data across all their devices and is no longer a part of Azure AD Enterprise State Roaming.</span></span> <span data-ttu-id="7d458-147">ただし、Microsoft Edge では、独自のキーを取り込む機能など、ESR のデータ保護の約束を満たしています。</span><span class="sxs-lookup"><span data-stu-id="7d458-147">However, the Microsoft Edge will fulfill the data protection promises of ESR, such as the ability to bring your own key.</span></span> <span data-ttu-id="7d458-148">詳細については、「[Microsoft Edge と Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d458-148">For more information, see [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7d458-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d458-149">See also</span></span>

- [<span data-ttu-id="7d458-150">Microsoft Edge エンタープライズの同期</span><span class="sxs-lookup"><span data-stu-id="7d458-150">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)
- [<span data-ttu-id="7d458-151">Microsoft Edge の同期の問題を診断して修正する</span><span class="sxs-lookup"><span data-stu-id="7d458-151">Diagnose and fix Microsoft Edge sync issues</span></span>](microsoft-edge-troubleshoot-enterprise-sync.md)
- [<span data-ttu-id="7d458-152">Microsoft Edge と Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="7d458-152">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="7d458-153">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="7d458-153">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)