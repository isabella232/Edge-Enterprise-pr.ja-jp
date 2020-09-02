---
title: Microsoft Edge を使用して、望ましくない可能性のあるアプリケーションから保護する
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 03/04/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge を使用して、望ましくない可能性のあるアプリケーションから保護する
ms.openlocfilehash: 615442acc0e9ed58da37aa0ef8b3747e916a8024
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980355"
---
# <span data-ttu-id="64783-103">望ましくない可能性のあるアプリケーションから保護する (PUA)</span><span class="sxs-lookup"><span data-stu-id="64783-103">Protect against potentially unwanted applications (PUAs)</span></span>

<span data-ttu-id="64783-104">この記事では、Microsoft Edge または Windows Defender ウイルス対策を使用して、望ましくない可能性のあるアプリケーション (PUA) から保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="64783-104">This article explains how you can protect against potentially unwanted applications (PUAs) using Microsoft Edge or by using Windows Defender Antivirus.</span></span>

> [!NOTE]
> <span data-ttu-id="64783-105">この記事は Microsoft Edge version 80 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="64783-105">This article applies to Microsoft Edge version 80 or later.</span></span>

## <span data-ttu-id="64783-106">概要</span><span class="sxs-lookup"><span data-stu-id="64783-106">Overview</span></span>

<span data-ttu-id="64783-107">望ましくない可能性のあるアプリケーションはウイルスやマルウェアとは見なされませんが、これらのアプリはエンドポイントのパフォーマンスに悪影響を及ぼす可能性があるエンドポイントの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="64783-107">Potentially unwanted applications aren't considered to be viruses or malware, but these apps might perform actions on endpoints that adversely affect endpoint performance or use.</span></span> <span data-ttu-id="64783-108">たとえば、*Evasion ソフトウェア*は、セキュリティ製品による検出を積極的に回避しようとします。</span><span class="sxs-lookup"><span data-stu-id="64783-108">For example, *Evasion software* actively tries to evade detection by security products.</span></span> <span data-ttu-id="64783-109">この種のソフトウェアは、ネットワークが実際のマルウェアに感染するリスクを高める可能性があります。</span><span class="sxs-lookup"><span data-stu-id="64783-109">This kind of software can increase the risk of your network being infected with actual malware.</span></span> <span data-ttu-id="64783-110">PUA は、評判がよくないと見なされるアプリケーションを指すこともあります。</span><span class="sxs-lookup"><span data-stu-id="64783-110">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="64783-111">PUA としてソフトウェアを分類するために使用される基準については、「[望ましくない可能性のあるアプリケーション](https://docs.microsoft.com/windows/security/threat-protection/intelligence/criteria#potentially-unwanted-application-pua)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64783-111">For a description of the criteria used to classify software as a PUA, see [Potentially unwanted application](https://docs.microsoft.com/windows/security/threat-protection/intelligence/criteria#potentially-unwanted-application-pua).</span></span>

## <span data-ttu-id="64783-112">Microsoft Edge を使用して PUA を防止する</span><span class="sxs-lookup"><span data-stu-id="64783-112">Protect against PUA with Microsoft Edge</span></span>

<span data-ttu-id="64783-113">Microsoft Edge (バージョン 80.0.361.50 以降) では、PUA のダウンロードと関連付けられたリソース URL がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="64783-113">Microsoft Edge (version 80.0.361.50 or later) blocks PUA downloads and associated resource URLs.</span></span>

<span data-ttu-id="64783-114">Microsoft Edge では、**望ましくない可能性のあるアプリのブロック**機能を有効にして、保護を設定できます。</span><span class="sxs-lookup"><span data-stu-id="64783-114">You can set up protection by enabling the **Block potentially unwanted apps** feature in Microsoft Edge.</span></span>

> [!NOTE]
> <span data-ttu-id="64783-115">[Microsoft Edge Team のブログ投稿](https://blogs.windows.com/msedgedev/2020/02/27/protecting-users-potentially-unwanted-apps/)では、この新機能について説明し、誤ってラベル付けされたアプリを処理する方法、またはアプリを望ましくないとして報告する方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="64783-115">The [Microsoft Edge Team blog post](https://blogs.windows.com/msedgedev/2020/02/27/protecting-users-potentially-unwanted-apps/) describes this new feature and explains how to handle a mislabeled app or report an app as unwanted.</span></span>

### <span data-ttu-id="64783-116">PUA 保護を有効にするには:</span><span class="sxs-lookup"><span data-stu-id="64783-116">To enable PUA protection:</span></span>

1. <span data-ttu-id="64783-117">ブラウザーで [**設定**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="64783-117">Open **Settings** in the browser.</span></span>
2. <span data-ttu-id="64783-118">[**プライバシーとサービス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="64783-118">Select **Privacy and services**.</span></span>
3. <span data-ttu-id="64783-119">[**サービス**] セクションで、[**Microsoft Defender SmartScreen**] がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="64783-119">In the **Services** section, check to see that **Microsoft Defender SmartScreen** is turned on.</span></span> <span data-ttu-id="64783-120">オンになっていない場合は、[Microsoft Defender SmartScreen] をオンに切り替えてください。</span><span class="sxs-lookup"><span data-stu-id="64783-120">If not, then turn on Microsoft Defender SmartScreen.</span></span> <span data-ttu-id="64783-121">次のスクリーンショットの例では、ブラウザーが組織によって管理されており、Microsoft Defender SmartScreen がオンになっています。</span><span class="sxs-lookup"><span data-stu-id="64783-121">The example in the following screenshot shows the browser is managed by the organization and that Microsoft Defender SmartScreen is turned on.</span></span>

   ![設定で Microsoft Edge PUA をオンにする](./media/microsoft-edge-potentially-unwanted-apps/security-pua-setup.png)

4. <span data-ttu-id="64783-123">[**サービス**] セクションで、前述のスクリーンショットのトグルを使用して、[**望ましくない可能性があるアプリをブロックする**] をオンに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="64783-123">In the **Services** section, use the toggle shown in the preceding screenshot to turn on **Block potentially unwanted apps**.</span></span>

   > [!TIP]
   > <span data-ttu-id="64783-124">Windows Defender SmartScreen [デモページ](https://demo.smartscreen.msft.net/)のいずれかでテストすることにより、PUA 保護の URL ブロック機能を安全に確認できます。</span><span class="sxs-lookup"><span data-stu-id="64783-124">You can safely explore the URL-blocking feature of PUA protection by testing it out on one of our Windows Defender SmartScreen [demo pages](https://demo.smartscreen.msft.net/).</span></span>

<span data-ttu-id="64783-125">Microsoft Edge が PUA を検出すると、次のスクリーンショットのようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="64783-125">When Microsoft Edge detects a PUA, you will see a message like the one in the next screenshot.</span></span>

   ![Microsoft Edge の PUA の警告メッセージ](./media/microsoft-edge-potentially-unwanted-apps/security-pua-msg.png)

### <span data-ttu-id="64783-127">PUA に関連付けられている URL をブロックするには</span><span class="sxs-lookup"><span data-stu-id="64783-127">To block against PUA-associated URLs</span></span>

<span data-ttu-id="64783-128">Microsoft Edge で PUA 保護を有効にすると、Windows Defender SmartScreen は、PUA に関連付けられた URL からユーザーを保護します。</span><span class="sxs-lookup"><span data-stu-id="64783-128">After you turn on PUA protection in Microsoft Edge, Windows Defender SmartScreen will protect you from PUA-associated URLs.</span></span>

<span data-ttu-id="64783-129">管理者が Microsoft Edge と Windows Defender SmartScreen が連携して PUA に関連付けられた URL からユーザーを保護する方法を構成する方法はいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="64783-129">There are several ways admins can configure how Microsoft Edge and Windows Defender SmartScreen work together to protect users from PUA-associated URLs.</span></span> <span data-ttu-id="64783-130">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64783-130">For more information, see:</span></span>

- [<span data-ttu-id="64783-131">Windows で Microsoft Edge ポリシー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="64783-131">Configure Microsoft Edge policy settings on Windows</span></span>](https://docs.microsoft.com/DeployEdge/configure-microsoft-edge)
- [<span data-ttu-id="64783-132">SmartScreen の設定</span><span class="sxs-lookup"><span data-stu-id="64783-132">SmartScreen settings</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreen-settings)
- [<span data-ttu-id="64783-133">SmartScreenPuaEnabled ポリシー</span><span class="sxs-lookup"><span data-stu-id="64783-133">SmartScreenPuaEnabled policy</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)
- [<span data-ttu-id="64783-134">Windows Defender SmartScreen を構成する</span><span class="sxs-lookup"><span data-stu-id="64783-134">Configure Windows Defender SmartScreen</span></span>](https://docs.microsoft.com/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen)

<span data-ttu-id="64783-135">管理者は、Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) ブロック リストをカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="64783-135">Admins can also customize the Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) block list.</span></span> <span data-ttu-id="64783-136">Microsoft Defender ATP ポータルを使用して、[IP および URL のインジケーターを作成および管理できます](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators#create-indicators-for-ips-and-urlsdomains-preview)。</span><span class="sxs-lookup"><span data-stu-id="64783-136">They can use the Microsoft Defender ATP portal to [create and manage indicators for IPs and URLs](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators#create-indicators-for-ips-and-urlsdomains-preview).</span></span>

## <span data-ttu-id="64783-137">Windows Defender ウイルス対策を使用して PUA を防止する</span><span class="sxs-lookup"><span data-stu-id="64783-137">Protect against PUA with Windows Defender Antivirus</span></span>

<span data-ttu-id="64783-138">「[望ましくない可能性のあるアプリケーションを検出およびブロックする](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#windows-defender-antivirus)」の記事では、 PUA 保護を有効にするために Windows Defender ウイルス対策を構成する方法についても説明しています。</span><span class="sxs-lookup"><span data-stu-id="64783-138">The [Detect and block potentially unwanted applications](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#windows-defender-antivirus) article also describes how you can configure Windows Defender Antivirus to enable PUA protection.</span></span> <span data-ttu-id="64783-139">次のオプションのいずれかを使用して保護を構成できます。</span><span class="sxs-lookup"><span data-stu-id="64783-139">You can configure protection using any of the following options:</span></span>

- [<span data-ttu-id="64783-140">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="64783-140">Microsoft Intune</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-intune-to-configure-pua-protection)
- [<span data-ttu-id="64783-141">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="64783-141">Microsoft Endpoint Configuration Manager</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-configuration-manager-to-configure-pua-protection)
- [<span data-ttu-id="64783-142">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="64783-142">Group Policy</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-group-policy-to-configure-pua-protection)
- [<span data-ttu-id="64783-143">PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="64783-143">PowerShell cmdlets</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-powershell-cmdlets-to-configure-pua-protection)

<span data-ttu-id="64783-144">Windows Defender は、エンドポイントで PUA ファイルを検出すると、ファイルを検疫し、通常の脅威検出 ("PUA:"で始まる) と同じ形式で ([通知が無効になっていない限り](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-notifications-windows-defender-antivirus))、ユーザーに通知します。 検出された脅威は、[Windows セキュリティ アプリの検疫リスト](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-security-center-antivirus#detection-history)にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="64783-144">When Windows Defender detects a PUA file on an endpoint it quarantines the file and notifies the user ([unless notifications are disabled](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-notifications-windows-defender-antivirus)) in the same format as a normal threat detection (prefaced with "PUA:".) Detected threats also appear in the [quarantine list in the Windows Security app](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-security-center-antivirus#detection-history).</span></span>

### <span data-ttu-id="64783-145">PUA の通知とイベント</span><span class="sxs-lookup"><span data-stu-id="64783-145">PUA notifications and events</span></span>

<span data-ttu-id="64783-146">管理者が PUA イベントを表示する方法は、次のようにいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="64783-146">There are several ways an admin can see PUA events:</span></span>

- <span data-ttu-id="64783-147">Windows イベントビューアー (Microsoft Endpoint Configuration Manager または Intune ではありません)。</span><span class="sxs-lookup"><span data-stu-id="64783-147">In the Windows Event Viewer, but not in Microsoft Endpoint Configuration Manager or Intune.</span></span>
- <span data-ttu-id="64783-148">電子メール (PUA 検出の電子メール通知がオンになっている場合)。</span><span class="sxs-lookup"><span data-stu-id="64783-148">In an email if email notifications for PUA detections is turned on.</span></span>
- <span data-ttu-id="64783-149">[Windows Defender ウイルス対策](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus)イベント ログ ( PUA イベントは、「マルウェア対策プラットフォームがマルウェアまたはその他の望ましくない可能性のあるソフトウェアを検出しました」というメッセージとともにイベント ID 1116 で記録されます)。</span><span class="sxs-lookup"><span data-stu-id="64783-149">In [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus) event logs, where a PUA event is recorded under event ID 1116 with the message: "The antimalware platform detected malware or other potentially unwanted software."</span></span>

> [!NOTE]
> <span data-ttu-id="64783-150">ユーザーには、「\*.exe が Microsoft Defender SmartScreen によって望ましくない可能性のあるアプリとしてブロックされました」と表示されます。</span><span class="sxs-lookup"><span data-stu-id="64783-150">Users will see "\*.exe has been blocked as a potentially unwanted app by Microsoft Defender SmartScreen".</span></span>

### <span data-ttu-id="64783-151">アプリのリストを許可する</span><span class="sxs-lookup"><span data-stu-id="64783-151">Allow-list an app</span></span>

<span data-ttu-id="64783-152">Microsoft Edge と同様に、Windows Defender ウイルス対策は、誤ってブロックされたファイルやタスクを完了するために必要なファイルを許可する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="64783-152">Like Microsoft Edge, Windows Defender Antivirus provides a way to allow files that are blocked by mistake or needed to complete a task.</span></span> <span data-ttu-id="64783-153">この場合、ファイルのリストを許可することができます。</span><span class="sxs-lookup"><span data-stu-id="64783-153">If this happens you can allow-list a file.</span></span> <span data-ttu-id="64783-154">詳細については、「[構成マネージャーでエンドポイント保護を構成する方法](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#to-exclude-specific-files-or-folders)」を参照して、特定のファイルまたはフォルダーを除外する方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="64783-154">For more information, see [How to Configure Endpoint Protection in Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#to-exclude-specific-files-or-folders) to learn how to exclude specific files or folders.</span></span>

## <span data-ttu-id="64783-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="64783-155">See also</span></span>

- [<span data-ttu-id="64783-156">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="64783-156">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="64783-157">脅威の防止</span><span class="sxs-lookup"><span data-stu-id="64783-157">Threat protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/index)
- [<span data-ttu-id="64783-158">動作に基づくヒューリスティックなリアルタイム保護の構成</span><span class="sxs-lookup"><span data-stu-id="64783-158">Configure behavioral, heuristic, and real-time protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-protection-features-windows-defender-antivirus)
- [<span data-ttu-id="64783-159">次世代の保護</span><span class="sxs-lookup"><span data-stu-id="64783-159">Next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)
- [<span data-ttu-id="64783-160">Chromium ベースの Microsoft Edge バージョン 79 のセキュリティベースライン</span><span class="sxs-lookup"><span data-stu-id="64783-160">Security baseline for Chromium-based Microsoft Edge, version 79</span></span>](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/security-baseline-final-for-chromium-based-microsoft-edge/ba-p/1111863)
