---
title: Microsoft Edge エンタープライズの同期
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 09/30/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge エンタープライズの同期
ms.openlocfilehash: d5868fb496c036d750925bb5ae6dfa3de0293fd2
ms.sourcegitcommit: 8a4479a1b034c3c13ea03ee3a2374a1af332cb38
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "11091949"
---
# Microsoft Edge エンタープライズの同期

この記事では、Microsoft Edge を使用して、サインインしているすべてのデバイスでお気に入り、パスワード、その他のブラウザー データを同期する方法について説明します。

> [!NOTE]
> この記事は Microsoft Edge version 77 以降に適用されます。

## 概要

Microsoft Edge の同期を使用すると、ユーザーは、サインインしているすべてのデバイスで閲覧データにアクセスできます。 同期でサポートされるデータは次のとおりです。

- お気に入り
- パスワード
- 住所など (フォームの入力情報)
- コレクション
- 設定

同期機能はユーザーの同意によって有効になり、ユーザーは上記の各データ タイプについて同期をオンまたはオフにすることができます。

> [!NOTE]
> 同期機能をサポートするために、デバイスの接続および構成データ (デバイス名、製造元、モデルなど) がアップロードされます。

## 前提条件

Azure Active Directory (Azure AD) アカウントでの Microsoft Edge の同期は、次のサブスクリプションのいずれかで使用できます。

- Azure AD Premium (P1 および P2)
- Microsoft 365 Business Premium
- Office 365 E3 以上
- Azure Information Protection (AIP) (P1& P2)
- すべての EDU サブスクリプション (学生または教職員向けの Microsoft Apps、学生または教職員向けの Exchange Online、O365 A1 以上、M365 A1 以上、学生または教職員向けの Azure Information Protection P1 または P2)

## Microsoft Edge の同期の構成

Microsoft Edge の同期の構成オプションは、Azure Information Protection (AIP) サービスを介して利用できます。 テナントの AIP が有効になっている場合、ライセンスに関係なくすべてのユーザーが Microsoft Edge のデータを同期できます。 AIP を有効にする方法は、[ここ](https://docs.microsoft.com/azure/information-protection/activate-office365)で説明されています。

特定のユーザー セットに対して同期を制限するために、これらのユーザーに対して [AIP のオンボード制御ポリシー](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps) を有効にすることができます。 必要なユーザーがすべてオンボードされた後でも同期ができない場合には、[Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps) PowerShell コマンドレット を使用して IPCv3Service が有効になっていることをご確認ください。

> [!CAUTION]
> Azure Information Protection を有効にすると、AIP を使用してコンテンツを保護するために Microsoft Word や Microsoft Outlook などの他のアプリケーションも許可されます。 また、エッジ同期を制限するために使用されるオンボード制御ポリシーは、他のアプリケーションが AIP を使用してコンテンツを保護することも制限します。

## Microsoft Edge と Enterprise State Roaming

新しい Microsoft Edge は、ユーザー データの同期の範囲をすべてのデバイスに拡張したクロスプラットフォーム アプリケーションであり、Azure AD Enterprise State Roaming の一部ではなくなりました。 ただし、新しい Microsoft Edge では、独自のキーを取り込む機能など、ESR のデータ保護の約束を満たしています。 詳細については、「[Microsoft Edge と Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)」を参照してください。

## 同期グループ ポリシー

次のグループ ポリシーは、Microsoft Edge の同期に影響を及ぼします。

- [SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): 同期を完全に無効にします。
- [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): 閲覧の履歴の保存と同期を無効にします。このポリシーにより、開いているタブの同期も無効になります。
- [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): 同期から除外される種類の一覧を構成します。
- [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): Active Directory (AD) プロファイルがオンプレミスの記憶域を使用できるようにします。 詳細については、「[Active Directory (AD) ユーザー用のオンプレミス同期](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync)」を参照してください。
- [ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): 既定で同期をオンにします。同期にはユーザーの同意を必要としません。  

## よく寄せられる質問

### セキュリティとサーバー/データのコンプライアンス

#### 同期したデータは暗号化されていますか? 

データは TLS 1.2 以上を使用してトランスポートで暗号化されます。 ほとんどのデータ型は、さらに AES256 を使用する Microsoft のサービスで保存時に暗号化されています。 

#### Microsoft Edge の同期データはどこに保存されますか?

Azure AD アカウントの同期されたデータは、テナント ID に従って、セキュリティで保護されたサーバーに保存されます。 たとえば、米国に登録されているテナントのデータは地理的にその地域にあるサーバーに保存され、Office アプリケーションで使用されるストレージ ソリューションと同じソリューションが使用されます。

#### Microsoft Edge との同期以外に、データが Microsoft のクラウドから移動することはありますか?

いいえ、そうではありません。

#### テナント管理者が独自のキーを使用することはできますか?

はい、[Azure Information Protection](https://azure.microsoft.com/services/information-protection/) から使用することができます。

#### エンタープライズ向けの同期には、どのサービス使用条件が適用されますか?

サービス使用条件は、ご利用の Azure AD サブスクリプションの条件と同じです。 すべての Azure AD のサービス使用条件には、最終的には Microsoft の[オンライン サービス条件](https://www.microsoft.com/licensing/product-licensing/products)が適用されます。

#### Microsoft Edge は、Government Community Cloud (GCC) High のコンプライアンスをサポートしていますか?

現時点ではサポートしていません。 GCC High は Tier D ですが、Microsoft Edge は Tier C までをサポートしています。

### 同期の適用

#### 企業や教育機関のお客様が、従来の Microsoft Edge を引き続き使用することを決定した場合、どうなりますか。

現在のバージョンの Microsoft Edge ブラウザーは、引き続き ESR サービスの対象に含まれます。

#### 同期するには Azure AD Premium サブスクリプションが必要なのはなぜですか?

エンタープライズ向け同期は Azure Information Protection に依存していますが、これは Azure AD のすべての階層で利用できるわけではありません。

#### Microsoft Edge の同期は Enterprise State Roaming に依存していますか?

いいえ、そうではありません。 ESR を使用して同期を有効にすることはできますが、Microsoft Edge の同期は ESR の一部ではありません。 詳細については、「[Microsoft Edge の同期](microsoft-edge-enterprise-sync.md)」と「[Microsoft Edge と Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)」を参照してください。

#### Microsoft Edge では、将来 Microsoft Edge と IE との同期はサポートされますか?

その同期をサポートする計画はありません。 ご自分の環境で従来のアプリをサポートするために IE を使用する必要がある場合、[新しい IE モード](https://docs.microsoft.com/deployedge/edge-ie-mode)を検討してください。

#### 新しい Microsoft Edge ブラウザーは、Microsoft Edge 従来版と同期しますか?

いいえ、同期されません。 この 2 つのエコシステムを接続すると、新しい Microsoft Edge での同期の信頼性が低下します。 既存のデータが新しい Microsoft Edge に移行されるようにします。 ユーザーは、選択したブラウザーからデータをインポートすることもできます。 これは、新しい Microsoft Edge ブラウザーが IE と同期する方法を備えていないことも意味します。

### 同期の管理

#### ユーザーに個人用テナントと同期させないようにすることはできますか?

直接はできませんが、[RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) ポリシーを使用して、Microsoft Edge にサインオンできるプロファイルを定義することはできます。

## 関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge と Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
