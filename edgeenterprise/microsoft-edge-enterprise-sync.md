---
title: Microsoft Edge エンタープライズの同期を構成する
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 06/28/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: お気に入り、パスワード、およびその他のブラウザー データを同期するように Microsoft Edge を構成するための管理者およびユーザー オプション。
ms.openlocfilehash: 5e3813664d3942e84d38e4ae1b4fd17e41049cda
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642823"
---
# <a name="configure-microsoft-edge-enterprise-sync"></a>Microsoft Edge エンタープライズの同期を構成する

この記事では、管理者が Microsoft Edge を構成して、サインインしているすべてのデバイス間でユーザーのお気に入り、パスワード、その他のブラウザー データを同期する方法について説明します。管理者でない場合は、サインインしてデバイス間で Microsoft Edge を同期する方法についてこの記事にアクセスしてください。 [サインインして、デバイス間で Microsoft Edge を同期します](https://support.microsoft.com/microsoft-edge/sign-in-to-sync-microsoft-edge-across-devices-e6ffa79b-ed52-aa32-47e2-5d5597fe4674)。

> [!NOTE]
> この記事は、特に指定されない限り、Microsoft Edge バージョン 77 以降に適用されます。

## <a name="overview"></a>概要

Microsoft Edge の同期を使用すると、ユーザーは、サインインしているすべてのデバイスで閲覧データにアクセスできます。 同期でサポートされるデータは次のとおりです。

- お気に入り
- パスワード
- 住所など (フォームの入力情報)
- コレクション
- 設定
- 拡張機能
- タブを開く (Microsoft Edge バージョン 88 で利用可能)
- 履歴 (Microsoft Edge バージョン 88 で利用可能)

同期機能はユーザーの同意によって有効になり、ユーザーは上記の各データ タイプについて同期をオンまたはオフにすることができます。 ユーザーに同期に関する問題が発生している場合は、**[設定]** > **[プロファイル]** > **[同期のリセット]** の順に移動して同期をリセットする必要がある場合があります。

> [!NOTE]
> 同期機能をサポートするために、デバイスの接続および構成データ (デバイス名、製造元、モデルなど) がアップロードされます。

## <a name="prerequisites"></a>前提条件

Azure Active Directory (Azure AD) アカウントでの Microsoft Edge の同期は、次のサブスクリプションのいずれかで使用できます。

- Azure AD Premium (P1 または P2)
- Microsoft 365 Business Premium
- Office 365 E1 以上
- Azure Information Protection (AIP) (P1 または P2)
- すべての EDU サブスクリプション (学生または教職員向けの Microsoft Apps、学生または教職員向けの Exchange Online、O365 A1 以上、M365 A1 以上、学生または教職員向けの Azure Information Protection P1 または P2)

## <a name="sync-group-policies"></a>同期グループ ポリシー

管理者は、Microsoft Edge の同期を構成および管理するために、次のグループ ポリシーを使用できます。

- [SyncDisabled](./microsoft-edge-policies.md#syncdisabled): 同期を完全に無効にします。
- [SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled): 閲覧の履歴と同期の保存を無効にします。このポリシーにより、オープン タブの同期も無効になります。
- [AllowDeletingBrowserHistory](./microsoft-edge-policies.md#allowdeletingbrowserhistory): このポリシーを無効に設定すると、履歴の同期も無効になります。
- [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled): 同期から除外されるタイプの一覧を構成します。
- [RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled): Active Directory (AD) プロファイルがオンプレミスの記憶域を使用できるようにします。 詳細については、「[Active Directory (AD) ユーザー用のオンプレミス同期](./microsoft-edge-on-premises-sync.md)」を参照してください。
- [ForceSync](/deployedge/microsoft-edge-policies#forcesync): 既定で同期をオンにします。同期にはユーザーの同意を必要としません。  

## <a name="configure-microsoft-edge-sync"></a>Microsoft Edge を構成する

Microsoft Edge の同期の構成オプションは、Azure Information Protection (AIP) サービスを介して利用できます。 テナントの AIP が有効になっている場合、ライセンスに関係なくすべてのユーザーが Microsoft Edge のデータを同期できます。 AIP を有効にする方法は、[ここ](/azure/information-protection/activate-office365)で説明されています。

特定のユーザー セットに対して同期を制限するために、これらのユーザーに対して [AIP のオンボード制御ポリシー](/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?preserve-view=true&view=azureipps) を有効にすることができます。 必要なユーザーがすべてオンボードされた後でも同期ができない場合には、[Get-AIPServiceIPCv3](/powershell/module/aipservice/get-aipserviceipcv3?preserve-view=true&view=azureipps) PowerShell コマンドレット を使用して IPCv3Service が有効になっていることをご確認ください。

> [!CAUTION]
> Azure Information Protection を有効にすると、AIP を使用してコンテンツを保護するために Microsoft Word や Microsoft Outlook などの他のアプリケーションも許可されます。 また、Microsoft Edge 同期を制限するために使用されるオンボード制御ポリシーは、他のアプリケーションが AIP を使用してコンテンツを保護することも制限します。

## <a name="microsoft-edge-and-enterprise-state-roaming-esr"></a>Microsoft Edge と Enterprise State Roaming (ESR)

新しい Microsoft Edge は、ユーザー データの同期の範囲をすべてのデバイスに拡張したクロスプラットフォーム アプリケーションであり、Azure AD Enterprise State Roaming の一部ではなくなりました。 ただし、Microsoft Edge では、独自のキーを取り込む機能など、ESR のデータ保護の約束を満たしています。 詳細については、「[Microsoft Edge と Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [Microsoft Edge エンタープライズの同期](microsoft-edge-enterprise-sync.md)
- [Microsoft Edge の同期の問題を診断して修正する](microsoft-edge-troubleshoot-enterprise-sync.md)
- [Microsoft Edge と Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)