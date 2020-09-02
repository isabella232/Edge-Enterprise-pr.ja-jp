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
# 望ましくない可能性のあるアプリケーションから保護する (PUA)

この記事では、Microsoft Edge または Windows Defender ウイルス対策を使用して、望ましくない可能性のあるアプリケーション (PUA) から保護する方法について説明します。

> [!NOTE]
> この記事は Microsoft Edge version 80 以降に適用されます。

## 概要

望ましくない可能性のあるアプリケーションはウイルスやマルウェアとは見なされませんが、これらのアプリはエンドポイントのパフォーマンスに悪影響を及ぼす可能性があるエンドポイントの操作を実行します。 たとえば、*Evasion ソフトウェア*は、セキュリティ製品による検出を積極的に回避しようとします。 この種のソフトウェアは、ネットワークが実際のマルウェアに感染するリスクを高める可能性があります。 PUA は、評判がよくないと見なされるアプリケーションを指すこともあります。

PUA としてソフトウェアを分類するために使用される基準については、「[望ましくない可能性のあるアプリケーション](https://docs.microsoft.com/windows/security/threat-protection/intelligence/criteria#potentially-unwanted-application-pua)」を参照してください。

## Microsoft Edge を使用して PUA を防止する

Microsoft Edge (バージョン 80.0.361.50 以降) では、PUA のダウンロードと関連付けられたリソース URL がブロックされます。

Microsoft Edge では、**望ましくない可能性のあるアプリのブロック**機能を有効にして、保護を設定できます。

> [!NOTE]
> [Microsoft Edge Team のブログ投稿](https://blogs.windows.com/msedgedev/2020/02/27/protecting-users-potentially-unwanted-apps/)では、この新機能について説明し、誤ってラベル付けされたアプリを処理する方法、またはアプリを望ましくないとして報告する方法について説明しています。

### PUA 保護を有効にするには:

1. ブラウザーで [**設定**] を開きます。
2. [**プライバシーとサービス**] を選択します。
3. [**サービス**] セクションで、[**Microsoft Defender SmartScreen**] がオンになっていることを確認します。 オンになっていない場合は、[Microsoft Defender SmartScreen] をオンに切り替えてください。 次のスクリーンショットの例では、ブラウザーが組織によって管理されており、Microsoft Defender SmartScreen がオンになっています。

   ![設定で Microsoft Edge PUA をオンにする](./media/microsoft-edge-potentially-unwanted-apps/security-pua-setup.png)

4. [**サービス**] セクションで、前述のスクリーンショットのトグルを使用して、[**望ましくない可能性があるアプリをブロックする**] をオンに切り替えます。

   > [!TIP]
   > Windows Defender SmartScreen [デモページ](https://demo.smartscreen.msft.net/)のいずれかでテストすることにより、PUA 保護の URL ブロック機能を安全に確認できます。

Microsoft Edge が PUA を検出すると、次のスクリーンショットのようなメッセージが表示されます。

   ![Microsoft Edge の PUA の警告メッセージ](./media/microsoft-edge-potentially-unwanted-apps/security-pua-msg.png)

### PUA に関連付けられている URL をブロックするには

Microsoft Edge で PUA 保護を有効にすると、Windows Defender SmartScreen は、PUA に関連付けられた URL からユーザーを保護します。

管理者が Microsoft Edge と Windows Defender SmartScreen が連携して PUA に関連付けられた URL からユーザーを保護する方法を構成する方法はいくつかあります。 詳細については、以下を参照してください。

- [Windows で Microsoft Edge ポリシー設定を構成する](https://docs.microsoft.com/DeployEdge/configure-microsoft-edge)
- [SmartScreen の設定](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreen-settings)
- [SmartScreenPuaEnabled ポリシー](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)
- [Windows Defender SmartScreen を構成する](https://docs.microsoft.com/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen)

管理者は、Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) ブロック リストをカスタマイズすることもできます。 Microsoft Defender ATP ポータルを使用して、[IP および URL のインジケーターを作成および管理できます](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators#create-indicators-for-ips-and-urlsdomains-preview)。

## Windows Defender ウイルス対策を使用して PUA を防止する

「[望ましくない可能性のあるアプリケーションを検出およびブロックする](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#windows-defender-antivirus)」の記事では、 PUA 保護を有効にするために Windows Defender ウイルス対策を構成する方法についても説明しています。 次のオプションのいずれかを使用して保護を構成できます。

- [Microsoft Intune](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-intune-to-configure-pua-protection)
- [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-configuration-manager-to-configure-pua-protection)
- [グループ ポリシー](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-group-policy-to-configure-pua-protection)
- [PowerShell コマンドレット](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-powershell-cmdlets-to-configure-pua-protection)

Windows Defender は、エンドポイントで PUA ファイルを検出すると、ファイルを検疫し、通常の脅威検出 ("PUA:"で始まる) と同じ形式で ([通知が無効になっていない限り](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-notifications-windows-defender-antivirus))、ユーザーに通知します。 検出された脅威は、[Windows セキュリティ アプリの検疫リスト](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-security-center-antivirus#detection-history)にも表示されます。

### PUA の通知とイベント

管理者が PUA イベントを表示する方法は、次のようにいくつかあります。

- Windows イベントビューアー (Microsoft Endpoint Configuration Manager または Intune ではありません)。
- 電子メール (PUA 検出の電子メール通知がオンになっている場合)。
- [Windows Defender ウイルス対策](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus)イベント ログ ( PUA イベントは、「マルウェア対策プラットフォームがマルウェアまたはその他の望ましくない可能性のあるソフトウェアを検出しました」というメッセージとともにイベント ID 1116 で記録されます)。

> [!NOTE]
> ユーザーには、「*.exe が Microsoft Defender SmartScreen によって望ましくない可能性のあるアプリとしてブロックされました」と表示されます。

### アプリのリストを許可する

Microsoft Edge と同様に、Windows Defender ウイルス対策は、誤ってブロックされたファイルやタスクを完了するために必要なファイルを許可する方法を提供します。 この場合、ファイルのリストを許可することができます。 詳細については、「[構成マネージャーでエンドポイント保護を構成する方法](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#to-exclude-specific-files-or-folders)」を参照して、特定のファイルまたはフォルダーを除外する方法を確認してください。

## 関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [脅威の防止](https://docs.microsoft.com/windows/security/threat-protection/index)
- [動作に基づくヒューリスティックなリアルタイム保護の構成](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-protection-features-windows-defender-antivirus)
- [次世代の保護](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)
- [Chromium ベースの Microsoft Edge バージョン 79 のセキュリティベースライン](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/security-baseline-final-for-chromium-based-microsoft-edge/ba-p/1111863)
