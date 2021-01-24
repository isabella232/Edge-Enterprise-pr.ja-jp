---
title: Microsoft Edge 同期を構成およびトラブルシューティングする
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 01/22/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 同期を構成およびトラブルシューティングする
ms.openlocfilehash: 36912d2fd1c33a227ce1d4b7c912f6ef1dfdcc00
ms.sourcegitcommit: 8a88fd38bdb5e132e89bf17dd2b5fb72f5d1b4b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "11297459"
---
# Microsoft Edge 同期を構成およびトラブルシューティングする

この記事では、Microsoft Edge を使用して、サインインしているすべてのデバイスでお気に入り、パスワード、その他のブラウザー データを同期する方法について説明します。 この記事では、最も一般的に発生する同期の問題に対するトラブルシューティング手順も提供します。 また、トラブルシューティングに必要なログを収集するために推奨されるツールも含まれています。

> [!NOTE]
> この記事は、特に指定されない限り、Microsoft Edge バージョン 77 以降に適用されます。

## 概要

Microsoft Edge の同期を使用すると、ユーザーは、サインインしているすべてのデバイスで閲覧データにアクセスできます。 同期でサポートされるデータは次のとおりです。

- お気に入り
- パスワード
- 住所など (フォームの入力情報)
- コレクション
- 設定
- 拡張機能
- タブを開く (Microsoft Edge バージョン 88 で利用可能)
- 履歴 (Microsoft Edge バージョン 88 で利用可能)

同期機能はユーザーの同意によって有効になり、ユーザーは上記の各データ タイプについて同期をオンまたはオフにすることができます。

> [!NOTE]
> 同期機能をサポートするために、デバイスの接続および構成データ (デバイス名、製造元、モデルなど) がアップロードされます。

## 前提条件

Azure Active Directory (Azure AD) アカウントでの Microsoft Edge の同期は、次のサブスクリプションのいずれかで使用できます。

- Azure AD Premium (P1 または P2)
- Microsoft 365 Business Premium
- Office 365 E1 以上
- Azure Information Protection (AIP) (P1 または P2)
- すべての EDU サブスクリプション (学生または教職員向けの Microsoft Apps、学生または教職員向けの Exchange Online、O365 A1 以上、M365 A1 以上、学生または教職員向けの Azure Information Protection P1 または P2)

## 同期グループ ポリシー

Microsoft Edge の同期を構成および管理するには、次のグループ ポリシーを使用できます。

- [SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): 同期を完全に無効にします。
- [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): 閲覧の履歴と同期の保存を無効にします。このポリシーにより、オープン タブの同期も無効になります。
- [AllowDeletingBrowserHistory](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory): このポリシーを無効に設定すると、履歴の同期も無効になります。
- [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): 同期から除外されるタイプの一覧を構成します。
- [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): Active Directory (AD) プロファイルがオンプレミスの記憶域を使用できるようにします。 詳細については、「[Active Directory (AD) ユーザー用のオンプレミス同期](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync)」を参照してください。
- [ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): 既定で同期をオンにします。同期にはユーザーの同意を必要としません。  

## Microsoft Edge を構成する

Microsoft Edge の同期の構成オプションは、Azure Information Protection (AIP) サービスを介して利用できます。 テナントの AIP が有効になっている場合、ライセンスに関係なくすべてのユーザーが Microsoft Edge のデータを同期できます。 AIP を有効にする方法は、[ここ](https://docs.microsoft.com/azure/information-protection/activate-office365)で説明されています。

特定のユーザー セットに対して同期を制限するために、これらのユーザーに対して [AIP のオンボード制御ポリシー](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true) を有効にすることができます。 必要なユーザーがすべてオンボードされた後でも同期ができない場合には、[Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true) PowerShell コマンドレット を使用して IPCv3Service が有効になっていることをご確認ください。

> [!CAUTION]
> Azure Information Protection を有効にすると、AIP を使用してコンテンツを保護するために Microsoft Word や Microsoft Outlook などの他のアプリケーションも許可されます。 また、Microsoft Edge 同期を制限するために使用されるオンボード制御ポリシーは、他のアプリケーションが AIP を使用してコンテンツを保護することも制限します。

## Microsoft Edge と Enterprise State Roaming (ESR)

新しい Microsoft Edge は、ユーザー データの同期の範囲をすべてのデバイスに拡張したクロスプラットフォーム アプリケーションであり、Azure AD Enterprise State Roaming の一部ではなくなりました。 ただし、Microsoft Edge では、独自のキーを取り込む機能など、ESR のデータ保護の約束を満たしています。 詳細については、「[Microsoft Edge と Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)」を参照してください。

## 同期に関する問題のトラブルシューティングを行う

このセクションでは、最も頻繁に発生した同期に関する問題のトラブルシューティング手順を説明します。 また、トラブルシューティングに必要なログを収集するために推奨されるツールも含まれています。

### ID の問題と同期の問題

ブラウザーでユーザー ID を維持するための一般的な使用例は、同期をサポートすることです。このため、ID の問題は、多くの場合、同期の問題と混同されます。 同期のトラブルシューティングを開始する前に、ID と同期の問題の違いを理解してください。

問題を同期の問題として扱う前に、ユーザーが有効なアカウントでブラウザーにサインインしているかどうか確認します。

次のスクリーンショットは、ID エラーの例を示しています。 エラーは**資格情報**の下にある*edge://sync-internals*にある "**ラスト トークン エラー、 EDGE_AUTH_ERROR: 3, 54, 3ea**"です。

:::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-identity-issue.png" alt-text="ラスト トークン エラー EDGE_AUTH_ERROR: 3,54、3ea":::

### 同期に関する一般的な問題

#### 問題 : M365 または Azure Information Protection サブスクリプションにアクセスできない

以前 M365 または Azure Information Protection (AIP) サブスクリプションの期限が切れて、新しいサブスクリプションに置き換えたということはありませんか? その場合は、テナント ID が変更されているので、サービス データをリセットする必要があります。 **「Cryptographer (暗号作成者) エラーが発生した** 問題」で、データ リセットの手順を確認してください。

#### 問題 : "このアカウントでは同期できません。"

Azure Active Directory アカウントでこのエラーが発生した場合、または *edge://sync-internals*に DISABLED_BY_ADMIN が表示される場合は、問題が解決するまで、次の手順に従います。

> [!NOTE]
> このエラーのソースは通常、Azure Active Directory テナントの構成変更を必要とするので、これらのトラブルシューティング手順はテナント管理者だけが実行できます。エンドユーザーは実行できません。

1. エンタープライズ テナントにサポートされている M365 サブスクリプションがあるかどうか確認します。 利用可能なサブスクリプションの種類の最新の一覧は [ここに表示されています](https://docs.microsoft.com/azure/information-protection/activate-office365)。 テナントにサポートされているサブスクリプションが存在しない場合は、Azure Information Protection を個別に購入するか、サポートされているサブスクリプションにアップグレードすることが必要です。
2. サポートされているサブスクリプションが利用可能な場合は、テナントが Azure Information Protection (AIP) を使用できる構成にしているかどうかを確認します。 AIP の状態を確認し、必要に応じて、AIP をアクティブ化するための手順については、 [ここ](https://docs.microsoft.com/azure/information-protection/activate-office365)をご覧ください。
3. 手順 2 で AIP がアクティブであるのに同期が機能しない場合は、Enterprise State Roaming (ESR) をオンにします。 ESR を有効にする手順は [ここ](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)をご覧ください。 ESR を使用し続ける必要はない点に注意してください。 この手順で問題が解決した場合は、ESR をオフにします。
4. Azure Information Protection が登録ポリシーによって範囲を設定されていないか確認します。 [Get-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmonboardingcontrolpolicy?view=azureipps)  PowerShell アプレットを使用して、範囲が設定されているかどうかを確認できます。 次の 2 つの例では、範囲が設定されていない構成の例と、特定のセキュリティ グループを対象に範囲が設定されている構成の例を示します。

   ```powershell
    PS C:\Work\scripts\PowerShell> Get-AadrmOnboardingControlPolicy
 
    UseRmsUserLicense SecurityGroupObjectId                Scope
    ----------------- ---------------------                -----
                False 
   ```

   ```powershell

    PS C:\Work\scripts\PowerShell> Get-AadrmOnboardingControlPolicy
 
    UseRmsUserLicense SecurityGroupObjectId                Scope
    ----------------- ---------------------                -----
                False f1488a05-8196-40a6-9483-524948b90282   All
   ```


   範囲指定が有効な場合、影響を受けるユーザーを、範囲のセキュリティ グループに追加するか、または範囲を削除する必要があります。 次の例では、登録で AIP の範囲が指定されたセキュリティ グループに設定されています。[Set-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell アプレットを使用して範囲を削除する必要があります。

5. テナントで IIPCv3Service が有効になっていることを確認します。 [Get-AadrmConfiguration](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmconfiguration?view=azureipps)  PowerShell のアプレットがサービスの状態を表示します。

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-scoped-cfg-example.png" alt-text="IPCv3Service が有効になっているどうか確認します。":::

6. 問題が解決しない場合は、[Microsoft Edge のサポート](https://www.microsoftedgeinsider.com/support)にお問い合わせください。

#### 問題 : "同期の設定..." でスタックする。または "同期サーバーに接続できません。 再試行中…”

1. サインアウトし、もう一度サインインします。
2. 「*edge://sync-internals*」へ移動します。 次のエラーが "**情報入力**"セクションの下に表示される場合は、次の問題、**「発生した Cryptographer エラー」** に進みます。

   `"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered"`

3. サーバー エンドポイントに対して ping を実行してみてください。 クライアントのサーバー エンドポイントは、次の *「edge://sync-internals」* で使用できます。 次のスクリーンショットは、**環境情報**の下のエンドポイント情報を示します。

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-endpoint-info.png" alt-text="エンドポイント情報":::

4. サーバーのエンドポイントが空の場合、またはサーバーに対して ping を実行できない場合、またはファイアウォールが環境に存在する場合は、クライアント コンピューターが必要とするサービス エンドポイントを使用できるかどうかを確認します。

   - Microsoft Edge 同期サービス エンドポイント:
     - [https://edge-enterprise.activity.windows.com](https://edge-enterprise.activity.windows.com)
     - [https://edge.activity.windows.com](https://edge.activity.windows.com)
    - Azure Information Protection エンドポイント:
      - [https://api.aadrm.com](https://api.aadrm.com)(ほとんどのテナントの場合)
      - [https://api.aadrm.de](https://api.aadrm.de)(ドイツのテナントの場合)
      - [https://api.aadrm.cn](https://api.aadrm.cn)(中国のテナントの場合)
   - [Windows 通知サービス エンドポイント](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)。

5. それでも問題が解決しない場合は、[Microsoft Edge のサポート](https://www.microsoftedgeinsider.com/support)にお問い合わせください。

### 問題: Cryptographer エラーが発生する

このエラーは、*edge://sync-internals* の**種類情報** に表示され、ユーザーのサービス側のデータをリセットする必要があることを意味している可能性があります。 次の例は、暗号化のエラー メッセージを示しています。
<br>"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered"。

1. Microsoft Edge を再起動し、*「edge://sync-internals」* に移動し、**「AAD アカウントキーの状態」** セクションを確認します。
   - "最終 MIP 結果" での "成功": Cryptographer エラーは、サーバー データが失われたキーで暗号化されている可能性を意味します。 同期を再開するには、データのリセットが必要です。
   - "最後の MIP 結果" に "アクセス許可なし": Azure AD の変更またはテナントのサブスクリプションの変更が原因である可能性があります。 同期を再開するには、データのリセットが必要です。
   - その他のエラーは、サーバー構成の問題を意味する可能性があります。
2. データのリセットが必要な場合は、[「 クラウドのMicrosoft Edge データをリセットする」](edge-learnmore-reset-data-in-cloud.md)を参照してください。

#### 問題: "同期は管理者によってオフにされています。"

[SyncDisabled ポリシー](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled)が設定されていないことを確認します。

## よく寄せられる質問

### セキュリティとサーバー/データのコンプライアンス

#### 同期したデータは暗号化されていますか?

データは TLS 1.2 以上を使用してトランスポートで暗号化されます。 すべてのデータ型は、AES128 を使用して Microsoft のサービスで保存中にさらに暗号化されます。 オープン タブと履歴の同期に使用されるデータ型を除くすべてのデータ型は、[Azure Information Protection](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern)ポリシーで管理されているキーを使ってユーザーのデバイスを離れる前に、さらに暗号化されます。

#### オープンタブと履歴データにクライアント側の暗号化を追加しない理由はなぜでしょうか?

エンド ユーザー のデバイスでのリソース使用率を削減するために、オープン タブ ローミング データに基づいてサーバー側で履歴データが生成されます。 このプロセスは、このデータのクライアント側の暗号化では実行できない可能性があります。 オープン タブと履歴の同期を無効にするには [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled) または [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) ポリシーを適用します。

#### テナント管理者が独自のキーを使用することはできますか?

はい [、Azure Information Protection を経由して可能です](https://azure.microsoft.com/services/information-protection/)。

#### Microsoft Edge の同期データはどこに保存されますか?

Azure AD アカウントの同期されたデータは、テナント ID に従って、セキュリティで保護されたサーバーに保存されます。 たとえば、米国に登録されているテナントのデータは地理的にその地域にあるサーバーに保存され、Office アプリケーションで使用されるストレージ ソリューションと同じソリューションが使用されます。

#### Microsoft Edge との同期以外に、データが Microsoft のクラウドから移動することはありますか?

いいえ、そうではありません。

#### エンタープライズ向けの同期には、どのサービス使用条件が適用されますか?

Microsoft Edge 同期のサービス条件は、Microsoft ソフトウェア ライセンスに含まれており、 *edge://terms*の「Microsoft Edge」で確認が可能です。 Azure ADサブスクリプションとサービス条件は、最終的には Microsoft の[オンライン サービス規約](https://www.microsoft.com/licensing/product-licensing/products)を適用します。 

#### Microsoft Edge は、Government Community Cloud (GCC) の高コンプライアンスをサポートしていますか?

現時点ではサポートしていません。 GCC High クラウドのユーザーの場合、Microsoft Edge の同期は無効になります。

### 同期の適用

#### Microsoft Edge の同期がすべての M365 サブスクリプションでサポートされていないのはなぜですか?

エンタープライズ同期は、すべての M365 サブスクリプションで利用できない [Azure Information Protection](https://azure.microsoft.com/services/information-protection/) に依存しています。

#### Microsoft Edge の同期は Enterprise State Roaming に依存していますか?

いいえ、そうではありません。 ESR を使用して同期を有効にすることはできますが、Microsoft Edge の同期は ESR の一部ではありません。 詳細については、「[Microsoft Edge の同期](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-sync)」と「[Microsoft Edge と Enterprise State Roaming](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-state-roaming)」を参照してください。

#### Microsoft Edge では、将来 Microsoft Edge と IE との同期はサポートされますか?

その同期をサポートする計画はありません。 ご自分の環境で従来のアプリをサポートするために IE を使用する必要がある場合、[新しい IE モード](https://docs.microsoft.com/deployedge/edge-ie-mode)を検討してください。

#### Microsoft Edge は Microsoft Edge レガシと同期しますか?

いいえ、同期されません。 これら 2 つのエコシステムを接続すると、Microsoft Edge の同期の信頼性が損なわれると考えています。 既存のデータが Microsoft Edge に移行されることを確認します。 ユーザーは選択したブラウザーからデータをインポートすることもできます。つまり、Microsoft Edge には IE と同期する方法が用意されていないということです。

### 同期の管理

#### ユーザーに個人用テナントと同期させないようにすることはできますか?

直接はできませんが、[RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) ポリシーを使用して、Microsoft Edge にサインオンできるプロファイルを定義することはできます。

## 関連項目

- [Microsoft Edge エンタープライズの同期](microsoft-edge-enterprise-sync.md)
- [Microsoft Edge と Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
