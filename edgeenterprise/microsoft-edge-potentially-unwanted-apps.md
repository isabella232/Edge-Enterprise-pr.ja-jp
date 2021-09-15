---
title: Microsoft Edge を使用して、望ましくない可能性のあるアプリケーションから保護する
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge を使用して、望ましくない可能性のあるアプリケーションから保護する
ms.openlocfilehash: 68cd87e85408933212c4b25baa01a9ff8d994089
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "11980437"
---
# <a name="protect-against-potentially-unwanted-applications-puas"></a>望ましくない可能性のあるアプリケーションから保護する (PUA)

この記事では、Microsoft Edge または Windows Defender ウイルス対策を使用して、望ましくない可能性のあるアプリケーション (PUA) から保護する方法について説明します。

> [!NOTE]
> この記事は Microsoft Edge version 80 以降に適用されます。

## <a name="overview"></a>概要

望ましくない可能性のあるアプリケーションはウイルスやマルウェアとは見なされませんが、これらのアプリはエンドポイントのパフォーマンスに悪影響を及ぼす可能性があるエンドポイントの操作を実行します。 たとえば、*Evasion ソフトウェア*は、セキュリティ製品による検出を積極的に回避しようとします。 この種のソフトウェアは、ネットワークが実際のマルウェアに感染するリスクを高める可能性があります。 PUA は、評判がよくないと見なされるアプリケーションを指すこともあります。

PUA としてソフトウェアを分類するために使用される基準については、「[望ましくない可能性のあるアプリケーション](/windows/security/threat-protection/intelligence/criteria#potentially-unwanted-application-pua)」を参照してください。

## <a name="protect-against-pua-with-microsoft-edge"></a>Microsoft Edge を使用して PUA を防止する

Microsoft Edge (バージョン 80.0.361.50 以降) では、PUA のダウンロードと関連付けられたリソース URL がブロックされます。

Microsoft Edge では、**望ましくない可能性のあるアプリのブロック**機能を有効にして、保護を設定できます。

> [!NOTE]
> [Microsoft Edge Team のブログ投稿](https://blogs.windows.com/msedgedev/2020/02/27/protecting-users-potentially-unwanted-apps/)では、この新機能について説明し、誤ってラベル付けされたアプリを処理する方法、またはアプリを望ましくないとして報告する方法について説明しています。

### <a name="to-enable-pua-protection"></a>PUA 保護を有効にするには:

1. ブラウザーで [**設定**] を開きます。
2. [**プライバシーとサービス**] を選択します。
3. [**サービス**] セクションで、[**Microsoft Defender SmartScreen**] がオンになっていることを確認します。 オンになっていない場合は、[Microsoft Defender SmartScreen] をオンに切り替えてください。 次のスクリーンショットの例では、ブラウザーが組織によって管理されており、Microsoft Defender SmartScreen がオンになっています。

   ![設定で Microsoft Edge PUA をオンにする](./media/microsoft-edge-potentially-unwanted-apps/security-pua-setup.png)

4. [**サービス**] セクションで、前述のスクリーンショットのトグルを使用して、[**望ましくない可能性があるアプリをブロックする**] をオンに切り替えます。

   > [!TIP]
   > Windows Defender SmartScreen [デモページ](https://demo.smartscreen.msft.net/)のいずれかでテストすることにより、PUA 保護の URL ブロック機能を安全に確認できます。

Microsoft Edge が PUA を検出すると、次のスクリーンショットのようなメッセージが表示されます。

   ![Microsoft Edge の PUA の警告メッセージ](./media/microsoft-edge-potentially-unwanted-apps/security-pua-msg.png)

### <a name="to-block-against-pua-associated-urls"></a>PUA に関連付けられている URL をブロックするには

Microsoft Edge で PUA 保護を有効にすると、Windows Defender SmartScreen は、PUA に関連付けられた URL からユーザーを保護します。

管理者が Microsoft Edge と Windows Defender SmartScreen が連携して PUA に関連付けられた URL からユーザーを保護する方法を構成する方法はいくつかあります。 詳細については、以下を参照してください。

- [Windows で Microsoft Edge ポリシー設定を構成する](./configure-microsoft-edge.md)
- [SmartScreen の設定](./microsoft-edge-policies.md#smartscreen-settings)
- [SmartScreenPuaEnabled ポリシー](./microsoft-edge-policies.md#smartscreenpuaenabled)
- [Windows Defender SmartScreen を構成する](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen)

管理者は、Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) ブロック リストをカスタマイズすることもできます。 Microsoft Defender ATP ポータルを使用して、[IP および URL のインジケーターを作成および管理できます](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators#create-indicators-for-ips-and-urlsdomains-preview)。

## <a name="protect-against-pua-with-windows-defender-antivirus"></a>Windows Defender ウイルス対策を使用して PUA を防止する

「[望ましくない可能性のあるアプリケーションを検出およびブロックする](/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#windows-defender-antivirus)」の記事では、 PUA 保護を有効にするために Windows Defender ウイルス対策を構成する方法についても説明しています。 次のオプションのいずれかを使用して保護を構成できます。

- [Microsoft Intune](/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-intune-to-configure-pua-protection)
- [Microsoft Endpoint Configuration Manager](/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-configuration-manager-to-configure-pua-protection)
- [グループ ポリシー](/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-group-policy-to-configure-pua-protection)
- [PowerShell コマンドレット](/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-powershell-cmdlets-to-configure-pua-protection)

Windows Defender は、エンドポイントで PUA ファイルを検出すると、ファイルを検疫し、通常の脅威検出 ("PUA:"で始まる) と同じ形式で ([通知が無効になっていない限り](/windows/security/threat-protection/windows-defender-antivirus/configure-notifications-windows-defender-antivirus))、ユーザーに通知します。 検出された脅威は、[Windows セキュリティ アプリの検疫リスト](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-security-center-antivirus#detection-history)にも表示されます。

### <a name="pua-notifications-and-events"></a>PUA の通知とイベント

管理者が PUA イベントを表示する方法は、次のようにいくつかあります。

- Windows イベントビューアー (Microsoft Endpoint Configuration Manager または Intune ではありません)。
- 電子メール (PUA 検出の電子メール通知がオンになっている場合)。
- [Windows Defender ウイルス対策](/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus)イベント ログ ( PUA イベントは、「マルウェア対策プラットフォームがマルウェアまたはその他の望ましくない可能性のあるソフトウェアを検出しました」というメッセージとともにイベント ID 1116 で記録されます)。

> [!NOTE]
> ユーザーには、「*.exe が Microsoft Defender SmartScreen によって望ましくない可能性のあるアプリとしてブロックされました」と表示されます。

### <a name="allow-list-an-app"></a>アプリのリストを許可する

Microsoft Edge と同様に、Windows Defender ウイルス対策は、誤ってブロックされたファイルやタスクを完了するために必要なファイルを許可する方法を提供します。 この場合、ファイルのリストを許可することができます。 詳細については、「[構成マネージャーでエンドポイント保護を構成する方法](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#to-exclude-specific-files-or-folders)」を参照して、特定のファイルまたはフォルダーを除外する方法を確認してください。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [脅威の防止](/windows/security/threat-protection/index)
- [動作に基づくヒューリスティックなリアルタイム保護の構成](/windows/security/threat-protection/windows-defender-antivirus/configure-protection-features-windows-defender-antivirus)
- [次世代の保護](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)
- [Chromium ベースの Microsoft Edge バージョン 79 のセキュリティベースライン](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/security-baseline-final-for-chromium-based-microsoft-edge/ba-p/1111863)