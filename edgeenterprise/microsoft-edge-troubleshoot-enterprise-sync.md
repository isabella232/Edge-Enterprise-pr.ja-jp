---
title: Microsoft Edge の同期の問題を診断して修正する
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 03/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 管理者が一般的なエンタープライズ同期の問題のトラブルシューティングと修正に使用できるガイダンスとツール
ms.openlocfilehash: 767b26c74e91213b407e8264a8ed185f38dfc2e9
ms.sourcegitcommit: 86e0de9b27ad4297a6d5a57c866d7ef4fc7bb0cd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400199"
---
# <a name="diagnose-and-fix-microsoft-edge-sync-issues"></a>Microsoft Edge の同期の問題を診断して修正する

この記事では、Azure Active Directory (Azure AD) 環境で最も一般的に発生する同期の問題のトラブルシューティング ガイダンスを提供します。 また、同期の問題のトラブルシューティングに必要なログを収集するための推奨ツールも含まれています。

ユーザーがデバイス間でブラウザー データを同期する際に問題が発生した場合は、[同期のリセット](edge-learnmore-reset-data-in-cloud.md)を試すことができます。これが機能しない場合、管理者またはサポート スタッフは、次のガイダンスを使用して同期の問題を修正できます。

> [!NOTE]
> この記事は、特に指定されない限り、Microsoft Edge バージョン 77 以降に適用されます。

## <a name="identity-issues-versus-sync-issues"></a>ID の問題と同期の問題

始める前に、ID の問題と同期の問題の違いを理解することが重要です。 ブラウザーでユーザー ID を維持するための一般的な使用例は、同期をサポートすることです。このため、ID の問題は、多くの場合、同期の問題と混同されます。 同期のトラブルシューティングを開始する前に、ID と同期の問題の違いを理解してください。

問題を同期の問題として扱う前に、ユーザーが有効なアカウントでブラウザーにサインインしているかどうか確認します。

次のスクリーンショットは、ID エラーの例を示しています。 エラーは**資格情報**の下にある*edge://sync-internals*にある "**ラスト トークン エラー、 EDGE_AUTH_ERROR: 3, 54, 3ea**"です。

:::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-identity-issue.png" alt-text="ラスト トークン エラー EDGE_AUTH_ERROR: 3,54、3ea":::

## <a name="common-sync-issues"></a>同期に関する一般的な問題

### <a name="issue-cant-access-m365-or-azure-information-protection-subscription"></a>問題 : M365 または Azure Information Protection サブスクリプションにアクセスできない

以前 M365 または Azure Information Protection (AIP) サブスクリプションの期限が切れて、新しいサブスクリプションに置き換えたということはありませんか? その場合は、テナント ID が変更されているので、サービス データをリセットする必要があります。 **「Cryptographer (暗号作成者) エラーが発生した** 問題」で、データ リセットの手順を確認してください。

### <a name="issue-sync-is-not-available-for-this-account"></a>問題 : "このアカウントでは同期できません。"

Azure Active Directory アカウントでこのエラーが発生した場合、または *edge://sync-internals*に DISABLED_BY_ADMIN が表示される場合は、問題が解決するまで、次の手順に従います。

> [!NOTE]
> このエラーのソースは通常、Azure Active Directory テナントの構成変更を必要とするので、これらのトラブルシューティング手順はテナント管理者だけが実行できます。エンドユーザーは実行できません。

1. エンタープライズ テナントにサポートされている M365 サブスクリプションがあるかどうか確認します。 利用可能なサブスクリプションの種類の最新の一覧は [ここに表示されています](https://docs.microsoft.com/azure/information-protection/activate-office365)。 テナントにサポートされているサブスクリプションが存在しない場合は、Azure Information Protection を個別に購入するか、サポートされているサブスクリプションにアップグレードすることが必要です。
2. サポートされているサブスクリプションが利用可能な場合は、テナントが Azure Information Protection (AIP) を使用できる構成にしているかどうかを確認します。 AIP の状態を確認し、必要に応じて、AIP をアクティブ化するための手順については、 [ここ](https://docs.microsoft.com/azure/information-protection/activate-office365)をご覧ください。
3. 手順 2 で AIP がアクティブであるのに同期が機能しない場合は、Enterprise State Roaming (ESR) をオンにします。 ESR を有効にする手順は [ここ](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)をご覧ください。 ESR を使用し続ける必要はない点に注意してください。 この手順で問題が解決した場合は、ESR をオフにします。
4. Azure Information Protection が登録ポリシーによって範囲を設定されていないか確認します。 [Get-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell アプレットを使用して、範囲が設定されているかどうかを確認できます。 次の 2 つの例では、範囲が設定されていない構成の例と、特定のセキュリティ グループを対象に範囲が設定されている構成の例を示します。

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

### <a name="issue-stuck-at-setting-up-sync-or-couldnt-connect-to-the-sync-server-retrying"></a>問題 : "同期の設定..." でスタックする。または "同期サーバーに接続できません。 再試行中…”

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

### <a name="issue-cryptographer-error-encountered"></a>問題: Cryptographer エラーが発生する

このエラーは、*edge://sync-internals* の**種類情報** に表示され、ユーザーのサービス側のデータをリセットする必要があることを意味している可能性があります。 次の例は、暗号化のエラー メッセージを示しています。
<br>"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered"。

1. Microsoft Edge を再起動し、*「edge://sync-internals」* に移動し、**「AAD アカウントキーの状態」** セクションを確認します。
   - "最終 MIP 結果" での "成功": Cryptographer エラーは、サーバー データが失われたキーで暗号化されている可能性を意味します。 同期を再開するには、データのリセットが必要です。
   - "最後の MIP 結果" に "アクセス許可なし": Azure AD の変更またはテナントのサブスクリプションの変更が原因である可能性があります。 同期を再開するには、データのリセットが必要です。
   - その他のエラーは、サーバー構成の問題を意味する可能性があります。
2. データのリセットが必要な場合は、[「 クラウドのMicrosoft Edge データをリセットする」](edge-learnmore-reset-data-in-cloud.md)を参照してください。

### <a name="issue-sync-has-been-turned-off-by-your-administrator"></a>問題: "同期は管理者によってオフにされています。"

[SyncDisabled ポリシー](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled)が設定されていないことを確認します。

## <a name="see-also"></a>関連項目

- [Microsoft Edge エンタープライズの同期](microsoft-edge-enterprise-sync.md)
- [Microsoft Edge と Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
