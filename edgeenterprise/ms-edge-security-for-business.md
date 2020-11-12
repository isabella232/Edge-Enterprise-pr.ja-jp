---
title: Microsoft Edge ビジネス向けのセキュリティ
ms.author: seanlynd
author: seanongit
manager: chuckf
ms.date: 11/11/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge ビジネス向けのセキュリティ
ms.openlocfilehash: e2f45d49d8f4960f3f2263098ff2eb7d0103b6ea
ms.sourcegitcommit: 5efa7f6196804da205c3deff4ba7917a94ffcf4f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2020
ms.locfileid: "11165943"
---
# Microsoft Edge ビジネス向けのセキュリティ

Microsoft Edge は、Google Chrome の中核と同じプロジェクトである、Chromium オープン ソース プロジェクト上に構築されます。これは、その基盤に、技術的に優れ、十分なテストを経た同じセキュリティ アーキテクチャと設計を共有していることを意味しています。 Microsoft Edge のセキュリティの話はそれだけではありません。 実際、**お客様のビジネスにとって Windows 10 上の Microsoft Edge は Google Chrome よりも安全です**。 Microsoft Edge にはフィッシングや悪意のあるソフトウェアに対する強力な防御策が組み込まれ、Windows 10 でハードウェア分離をネイティブにサポートします。この安全なベースラインを実現するのに追加のソフトウェアは必要ありません。 さらに、Microsoft 365 セキュリティとコンプライアンス サービスと組み合わせて使用すると、Microsoft Edge は強力なセキュリティ機能をさらに実現し、データを損失から保護することでより多くのメリットをもたらすのに役立ちます。

まず**外部の脅威**について、次に**内部リスクと情報保護**について、詳細を説明します。

## 外部の脅威からの保護

### フィッシングと悪意のあるソフトウェアに対する最も評価が高い保護

Microsoft Edge に組み込まれた SmartScreen は、NSS Lab の独立した調査によると、Google Chrome の Safe Browsing よりも多くの [フィッシング](https://edgeconsumerproduction.blob.core.windows.net/hostingdocs/NSS_Labs_Browser_Phishing_Report_Q2_2020.pdf) と [マルウェア](https://edgeconsumerproduction.blob.core.windows.net/hostingdocs/NSS_Labs_Browser_Malware_Report_Q2_2020.pdf) の試みをブロックします。 SmartScreen はユーザーがオンラインで作業している間、サイトやダウンロードのリアルタイムの評判チェックを提供します。また、SmartScreen は [Microsoft インテリジェント セキュリティ グラフ](https://www.microsoft.com/microsoft-365/windows/intelligent-security)の一部です。これは、Microsoft のグローバルなアセット、研究者、パートナーによって生成された信号や分析情報を引き出します。 危険なサイトやダウンロードのクラウド ベースの動的リストに対してチェックを実行することで、Microsoft Edge はすぐに消える一時的な脅威さえも検出してブロックするのに役立ちます。  

[SmartScreen が組み込まれている Microsoft Edge](https://docs.microsoft.com//DeployEdge/microsoft-edge-security-smartscreen) は [NSS Labs によるテスト](https://www.nsslabs.com/tested-technologies/web-browser-security-wbs/)の間、フィッシング試行を 95.5%、悪意のあるソフトウェアによる試行を 98.5% ブロックしました。一方、Chrome のセーフ ブラウジングの比率はそれぞれ 86.9% と 86.0% でした。

### Windows 10 でハードウェア分離をネイティブでサポートする唯一のブラウザー

Microsoft Edge は、Windows 10 でハードウェア分離の機能をネイティブでサポートする唯一のブラウザーです。 Windows 10 Pro または Enterprise の一部である Microsoft Defender Application Guard (Application Guard) は、信頼されていないサイトをローカル デバイスと内部ネットワークから分離されているカーネルで実行します。 信頼されていないサイトは "コンテナー" の中で実行されるため、攻撃が発生すると企業ネットワークの残りの部分からサンドボックス化されます。 詳細については、「[Application Guard の Microsoft Edge サポート](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-defender-application-guard)」を参照してください。

Chrome では、Windows 10 のハードウェア分離を利用するための拡張機能 (MDAG 拡張機能) を使用できます。 この拡張機能を使用すると、Application Guard のカーネル レベルの分離を利用するために Microsoft Edge を起動します。 さらに、Chrome のみを利用したソリューションの場合、同様のカーネル レベルの分離を実現するにはサード パーティの分離ソフトウェアが必要です。

> [!NOTE]
> Application Guard は Windows 10 (バージョン 1809 以降) で利用できます。 Application Guard は Windows 10 Home エディションでは利用できません。

## 内部リスクと情報保護

### 追加のソフトウェアなしで Microsoft 365 セキュリティをネイティブでサポート

IT 管理者は、外部の脅威以外にも、内部リスクに対して保護する必要があります。 企業の機密データを規模に応じて確実に保護することは、特に従業員が分散している今、IT 管理者にとっての最優先事項です。 Microsoft Edge は、Azure AD の条件付きアクセス、Windows 情報保護、新しい Microsoft エンドポイントのデータ損失防止 (DLP) を追加のソフトウェアなしでネイティブでサポートする唯一のブラウザーです。

**Microsoft Edge は、条件付きアクセスをネイティブにサポートする唯一のブラウザーです**。 [Microsoft Edge による条件付きアクセスのサポート](ms-edge-security-conditional-access.md)により、組織は ID シグナルをアクセス制御に関する決定事項の一部として簡単に活用できます。 [条件付きアクセス](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)は、Azure Active Directory がシグナルをまとめ、決定を行い、組織のポリシーを強制するのに使用するツールです。 条件付きアクセスは、新しい ID を活用したコントロール プレーンの中核をなしています。 Chrome で条件付きアクセスがサポートされるようにするには、追加のプラグインが必要です。

> [!NOTE]
> Azure AD の条件付きアクセスには、Microsoft 365 E3 以降のサブスクリプションが必要です。

**Microsoft Edge は、Windows 情報保護 (WIP) をネイティブでサポートする唯一のブラウザーです。** これは、企業データを保護し、Windows 10 デバイスでユーザーによる偶発的な漏洩を防ぐのに役立ちます。 [Microsoft Edge による WIP のサポート](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-information-protection)は、企業データへのアクセスを IT 管理者が義務付けたアプリだけに許可するように構成できます。 また、シームレスなユーザー エクスペリエンスと共に、クリップボード保護、ダウンロード時のファイルの暗号化、承認されていないネットワーク共有やクラウド上の場所へのファイルのアップロード防止などの漏洩制御も提供します。 WIP は、境界ベースの構成で動作します。この構成では、IT 管理者が企業の境界を定義し、境界内のすべてのデータが企業データと見なされます。 Chrome の場合、漏洩制御を含む WIP には対応していません。

> [!NOTE]
> Windows 情報保護 (WIP) の構成には、Microsoft Intune または Microsoft Endpoint Configuration Manager のライセンスが必要です。もしくは、サード パーティのモバイル デバイス管理 (MDM) ソリューションを使用できますが、これには追加のライセンス要件がある場合があります。

**Microsoft ENDPOINT DLP は、Microsoft Edge でネイティブでのみサポートされます**。 Microsoft エンドポイントのデータ損失防止 (DLP) は Microsoft セキュリティ センターと統合し、情報保護を Microsoft Edge に拡張することで、非対応のアクティビティについてユーザーに警告し、ユーザーがオンラインで作業している間にデータの損失を防ぐのに役立ちます。 クレジット カード番号や行政上の ID (社会保障番号など)、財務情報を含むファイルなど、管理者が定義した基準と一致する企業内の機密データを検出し、ラベルを付けます。Microsoft の情報保護ポリシーは、機密情報の識別子や IT 管理者が既にカスタマイズしたポリシーも含め、Microsoft エンドポイント データ損失防止に追加の再構成なしで展開できます。 これは IT 管理者にとって、情報保護のシームレスな展開です。

> [!NOTE]
> Microsoft エンドポイントのデータ損失防止には、Microsoft 365 E5 または Microsoft 365 E5 Compliance のサブスクリプションが必要です。

## 関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
