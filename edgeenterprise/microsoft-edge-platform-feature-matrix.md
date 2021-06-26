---
title: Microsoft Edge 機能向けのプラットフォームのサポート
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 03/25/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 機能向けのプラットフォーム サポートの概要
ms.openlocfilehash: 3fb4fc0bc2671bdee5055fa650f191c5d3821963
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617727"
---
# <a name="platform-support-for-microsoft-edge-features"></a>Microsoft Edge 機能向けのプラットフォームのサポート

この記事では、Microsoft Edge 機能向けのプラットフォームのサポートの概要を示します。

> [!NOTE]
> この記事は Microsoft Edge バージョン 77 以降に適用されます。

## <a name="feature-matrix-for-platforms"></a>プラットフォーム用の機能マトリックス

次の表は、Windows および macOS プラットフォームでの機能のサポートをまとめた一覧です。

> [!NOTE]
> 現在、Android と iOS はサポートの表に表示されていませんが、引き続き情報を収集しており、適宜更新されます。

| セキュリティ機能 |Win 10|Win 8.1|Win 7|macOS|URL|
|--------|-------|--------|-----|-------|---|
|Azure Active Directory (Azure AD) 条件付きアクセス|はい|あり|あり|はい|[Azure AD 条件付きアクセス](/deployedge/ms-edge-security-conditional-access#accessing-conditional-access-protected-resources-in-microsoft-edge)|
|Microsoft Defender Application Guard|はい (1890+)|なし|なし|なし|[Microsoft Defender Application Guard](/deployedge/microsoft-edge-security-windows-defender-application-guard) |
|Microsoft Defender SmartScreen|はい|あり|あり|はい|[Microsoft Defender SmartScreen](/deployedge/microsoft-edge-security-smartscreen) |
|Microsoft エンドポイント DLP|はい|なし|なし|なし|[Microsoft エンドポイント DLP](/deployedge/microsoft-edge-security-dlp#microsoft-endpoint-data-loss-prevention-endpoint-dlp)|
|パスワード モニター|はい|あり|あり|はい|[パスワード モニター](https://blogs.windows.com/msedgedev/2021/01/21/edge-88-privacy/)|
|パスワード ジェネレーター|はい|あり|あり|はい|[パスワード ジェネレーター](https://blogs.windows.com/msedgedev/2021/01/21/edge-88-privacy/)|
|Windows 情報保護 (WIP)|はい (1607+)|なし|なし|なし|[WIP](/deployedge/microsoft-edge-security-windows-information-protection#system-requirements)|

|ID 機能| Win 10 | Win 8.1 | Win 7 | macOS | URL |
|--|--|--|--|--|--|
|自動サインイン (hybrid/AAD-J)|はい|あり|あり|なし|[hybrid/AAD-J](/deployedge/microsoft-edge-security-identity#automatic-sign-in)|
|自動サインイン (ドメインに参加している場合)|はい|あり|あり|なし|[ドメインに参加している場合](/deployedge/microsoft-edge-security-identity#automatic-sign-in)|
|自動サインイン (OS の既定のアカウントは MSA)|はい (1709+)|なし|なし|なし|[MSA](/deployedge/microsoft-edge-security-identity#automatic-sign-in)|
|ブラウザーから Web シングル サインオン (SSO)|はい|あり|あり|はい|[ブラウザー - Web SSO](https://www.microsoft.com/microsoft-365/roadmap?featureid=66332)|
|ガイド付きスイッチ/"プロファイルの自動切り替え"|はい|あり|あり|はい|[職場や自宅で複数のプロファイルを使用する](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/) |
|複数のプロファイル|はい|あり|あり|はい|[職場や自宅で複数のプロファイルを使用する](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/) |
|Active Directory ユーザー用のオンプレミス同期 (AD)|はい|あり|あり|なし|[Active Directory (AD) ユーザー用のオンプレミス同期](/deployedge/microsoft-edge-on-premises-sync) |
|シームレス SSO|はい (1709+)|はい|あり|あり|[シームレス SSO](/deployedge/microsoft-edge-security-identity#seamless-sso)|
|プライマリ更新トークン (PRT) による SSO|はい (1709+)|はい|あり|なし|[PRT を使用した SSO](/deployedge/microsoft-edge-security-identity#sso-with-primary-refresh-token-prt)|
|Windows 統合認証 (WIA)|はい|あり|はい|あり* (ポリシーが必要)|[WIA](/deployedge/microsoft-edge-security-identity#windows-integrated-authentication-wia)|

|追加機能|Win 10|Win 8.1|Win 7|macOS|URL|
|--------|-------|--------|-----|-------|---|
|コレクション|はい|あり|あり|はい|[コレクション](https://blogs.windows.com/msedgedev/2019/12/09/improvements-collections-sync-microsoft-edge/) |
|Enterprise [新しいタブ] ページ|はい|あり|あり|はい|[新しいタブ ページ](https://blogs.windows.com/msedgedev/2020/10/29/enterprise-new-tab-page-my-feed/) |
|IE モード|はい|あり|あり|なし|[IE モード](/deployedge/edge-ie-mode#prerequisites)|
|キオスク モード|はい|なし|なし|なし|[キオスク モード](/deployedge/microsoft-edge-configure-kiosk-mode)|
|Bing の Microsoft Search|はい|あり|あり|はい|[Bing のインテリジェント検索](https://www.microsoft.com/edge/business/intelligent-search-with-bing) |
|PDF リーダー|はい|あり|あり|はい|[PDF リーダー](/deployedge/microsoft-edge-pdf) |
|ショッピング|はい|あり|あり|はい|[ショッピング](https://techcommunity.microsoft.com/t5/articles/introducing-shopping-with-microsoft-edge/m-p/1870080) |
|スリーピング タブ|はい|あり|あり|はい|[機能の概要](/deployedge/microsoft-edge-relnote-stable-channel)<br>[最新のブログ投稿](https://blogs.windows.com/msedgedev/2021/03/04/edge-89-performance/)<br>[グループ ポリシー](/deployedge/microsoft-edge-policies#sleeping-tabs-settings)|
|同期|あり|あり|あり|はい| [エンタープライズ同期](/deployedge/microsoft-edge-enterprise-sync) |
|バージョン ロールバック|はい|あり|あり|なし|[バージョン ロールバック](/deployedge/edge-learnmore-rollback) |
|縦方向のタブ|はい|あり|あり|はい| |

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)