---
title: Microsoft Edge のエンタープライズ向けの同期に関するよく寄せられる質問 (FAQ)
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge のエンタープライズ向けの同期に関してよく寄せられる質問。
ms.openlocfilehash: a13e1f02f6e871004d45f81159d5cf0a3397b6ad
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "11980287"
---
# <a name="microsoft-edge-enterprise-sync-faq"></a>Microsoft Edge のエンタープライズ向けの同期に関するよく寄せられる質問 (FAQ)

この記事では、Microsoft Edge バージョン 77 以降のエンタープライズ向けの同期に関するよく寄せられる質問に回答します。

## <a name="security-and-serverdata-compliance"></a>セキュリティとサーバー/データのコンプライアンス

### <a name="is-the-synced-data-encrypted"></a>同期したデータは暗号化されていますか?

データは TLS 1.2 以上を使用してトランスポートで暗号化されます。 すべてのデータ型は、AES128 を使用して Microsoft のサービスで保存中にさらに暗号化されます。 オープン タブと履歴の同期に使用されるデータ型を除くすべてのデータ型は、[Azure Information Protection](./microsoft-edge-policies.md#restrictsignintopattern)ポリシーで管理されているキーを使ってユーザーのデバイスを離れる前に、さらに暗号化されます。

### <a name="why-dont-open-tab-and-history-data-have-more-client-side-encryption"></a>オープンタブと履歴データにクライアント側の暗号化を追加しない理由はなぜでしょうか?

エンド ユーザー のデバイスでのリソース使用率を削減するために、オープン タブ ローミング データに基づいてサーバー側で履歴データが生成されます。 このプロセスは、このデータのクライアント側の暗号化では実行できない可能性があります。 オープン タブと履歴の同期を無効にするには [SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled) または [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) ポリシーを適用します。

### <a name="can-tenant-admins-bring-their-own-key"></a>テナント管理者が独自のキーを使用することはできますか?

はい [、Azure Information Protection を経由して可能です](https://azure.microsoft.com/services/information-protection/)。

### <a name="where-is-microsoft-edge-sync-data-stored"></a>Microsoft Edge の同期データはどこに保存されますか?

Azure AD アカウントの同期されたデータは、テナント ID に従って、セキュリティで保護されたサーバーに保存されます。 たとえば、米国に登録されているテナントのデータは地理的にその地域にあるサーバーに保存され、Office アプリケーションで使用されるストレージ ソリューションと同じソリューションが使用されます。

### <a name="does-the-data-ever-leave-microsofts-cloud-aside-from-syncing-to-microsoft-edge"></a>Microsoft Edge との同期以外に、データが Microsoft のクラウドから移動することはありますか?

いいえ、そうではありません。

### <a name="what-terms-of-service-does-enterprise-sync-fall-under"></a>エンタープライズ向けの同期には、どのサービス使用条件が適用されますか?

Microsoft Edge 同期のサービス条件は、Microsoft ソフトウェア ライセンスに含まれており、 *edge://terms*の「Microsoft Edge」で確認が可能です。 Azure ADサブスクリプションとサービス条件は、最終的には Microsoft の[オンライン サービス規約](https://www.microsoft.com/licensing/product-licensing/products)を適用します。 

### <a name="does-microsoft-edge-support-government-community-cloud-gcc-high-compliance"></a>Microsoft Edge は、Government Community Cloud (GCC) の高コンプライアンスをサポートしていますか?

現時点ではサポートしていません。 GCC High クラウドのユーザーの場合、Microsoft Edge の同期は無効になります。

## <a name="applying-sync"></a>同期の適用

### <a name="why-isnt-microsoft-edge-sync-supported-in-all-m365-subscriptions"></a>Microsoft Edge の同期がすべての M365 サブスクリプションでサポートされていないのはなぜですか?

エンタープライズ同期は、すべての M365 サブスクリプションで利用できない [Azure Information Protection](https://azure.microsoft.com/services/information-protection/) に依存しています。

### <a name="is-microsoft-edge-sync-based-on-enterprise-state-roaming"></a>Microsoft Edge の同期は Enterprise State Roaming に依存していますか?

いいえ、そうではありません。 ESR を使用して同期を有効にすることはできますが、Microsoft Edge の同期は ESR の一部ではありません。 詳細については、「[Microsoft Edge の同期](/DeployEdge/microsoft-edge-enterprise-sync)」と「[Microsoft Edge と Enterprise State Roaming](/DeployEdge/microsoft-edge-enterprise-state-roaming)」を参照してください。

### <a name="will-microsoft-edge-ever-support-syncing-between-microsoft-edge-and-ie"></a>Microsoft Edge では、将来 Microsoft Edge と IE との同期はサポートされますか?

その同期をサポートする計画はありません。 ご自分の環境で従来のアプリをサポートするために IE を使用する必要がある場合、[新しい IE モード](./edge-ie-mode.md)を検討してください。

### <a name="will-microsoft-edge-sync-with-microsoft-edge-legacy"></a>Microsoft Edge は Microsoft Edge レガシと同期しますか?

いいえ、同期されません。 これら 2 つのエコシステムを接続すると、Microsoft Edge の同期の信頼性が損なわれると考えています。 既存のデータが Microsoft Edge に移行されることを確認します。 ユーザーは選択したブラウザーからデータをインポートすることもできます。つまり、Microsoft Edge には IE と同期する方法が用意されていないということです。

## <a name="managing-sync"></a>同期の管理

### <a name="is-it-possible-to-stop-my-users-from-syncing-with-a-personal-tenant"></a>ユーザーに個人用テナントと同期させないようにすることはできますか?

直接はできませんが、[RestrictSigninToPattern](./microsoft-edge-policies.md#restrictsignintopattern) ポリシーを使用して、Microsoft Edge にサインオンできるプロファイルを定義することはできます。

## <a name="see-also"></a>関連項目

- [Microsoft Edge エンタープライズの同期](microsoft-edge-enterprise-sync.md)
- [Microsoft Edge と Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)