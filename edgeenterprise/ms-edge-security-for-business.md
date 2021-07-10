---
title: Microsoft Edge ビジネス向けのセキュリティ
ms.author: collw
author: seanongit
manager: chuckf
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge ビジネス向けのセキュリティ
ms.openlocfilehash: d16b22b63212e3f5319b0bb7df1e457e45cd6208
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642303"
---
# <a name="microsoft-edge-security-for-your-business"></a>Microsoft Edge ビジネス向けのセキュリティ

Microsoft Edge は、Google Chrome の中核と同じプロジェクトである、Chromium オープン ソース プロジェクト上に構築されます。これは、その基盤に、技術的に優れ、十分なテストを経た同じセキュリティ アーキテクチャと設計を共有していることを意味しています。 Microsoft Edge のセキュリティの話はそれだけではありません。 実際、**お客様のビジネスにとって Windows 10 上の Microsoft Edge は Google Chrome よりも安全です**。 Microsoft Edge にはフィッシングや悪意のあるソフトウェアに対する強力な防御策が組み込まれ、Windows 10 でハードウェア分離をネイティブにサポートします。この安全なベースラインを実現するのに追加のソフトウェアは必要ありません。 さらに、Microsoft 365 セキュリティとコンプライアンス サービスと組み合わせて使用すると、Microsoft Edge は強力なセキュリティ機能をさらに実現し、データを損失から保護することでより多くのメリットをもたらすのに役立ちます。 詳細については、「[ビビデオ: Microsoft Edge のセキュリティ、互換性、管理の容易さ](microsoft-edge-video-security-compatibility-manageability.md)」を参照してください。

まず**外部の脅威**について、次に**内部リスクと情報保護**について、詳細を説明します。

## <a name="external-threat-protection"></a>外部の脅威からの保護

### <a name="highest-rated-protection-against-phishing-and-malware"></a>フィッシングと悪意のあるソフトウェアに対する最も評価が高い保護

Microsoft Edge に組み込まれた SmartScreen は、NSS Lab の独立した調査によると、Google Chrome の Safe Browsing よりも多くの [フィッシング](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWASN1) と [マルウェア](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWANMW) の試みをブロックします。 SmartScreen はユーザーがオンラインで作業している間、サイトやダウンロードのリアルタイムの評判チェックを提供します。また、SmartScreen は [Microsoft インテリジェント セキュリティ グラフ](https://www.microsoft.com/microsoft-365/windows/intelligent-security)の一部です。これは、Microsoft のグローバルなアセット、研究者、パートナーによって生成された信号や分析情報を引き出します。 危険なサイトやダウンロードのクラウド ベースの動的リストに対してチェックを実行することで、Microsoft Edge はすぐに消える一時的な脅威さえも検出してブロックするのに役立ちます。  

[Microsoft Edge SmartScreen](//DeployEdge/microsoft-edge-security-smartscreen)は、[NSS Labs のフィッシング保護](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWASN1)テスト中にフィッシング試行の 95.5% と[NSS Labsのマルウェア保護](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWANMW)テスト中にマルウェアの試行の 98.5% をブロックしました。Chrome の Safe Browsing の同レートは、それぞれ 86.9% と 86.0% です。

### <a name="the-only-browser-on-windows-10-that-natively-supports-hardware-isolation"></a>Windows 10 でハードウェア分離をネイティブでサポートする唯一のブラウザー

Microsoft Edge は、Windows 10 でハードウェア分離の機能をネイティブでサポートする唯一のブラウザーです。 Windows 10 Pro または Enterprise の一部である Microsoft Defender Application Guard (Application Guard) は、信頼されていないサイトをローカル デバイスと内部ネットワークから分離されているカーネルで実行します。 信頼されていないサイトは "コンテナー" の中で実行されるため、攻撃が発生すると企業ネットワークの残りの部分からサンドボックス化されます。 詳細については、「[Application Guard の Microsoft Edge サポート](./microsoft-edge-security-windows-defender-application-guard.md)」を参照してください。

Chrome では、Windows 10 のハードウェア分離を利用するための拡張機能 (MDAG 拡張機能) を使用できます。 この拡張機能を使用すると、Application Guard のカーネル レベルの分離を利用するために Microsoft Edge を起動します。 さらに、Chrome のみを利用したソリューションの場合、同様のカーネル レベルの分離を実現するにはサード パーティの分離ソフトウェアが必要です。

> [!NOTE]
> Application Guard は Windows 10 (バージョン 1809 以降) で利用できます。 Application Guard は Windows 10 Home エディションでは利用できません。

## <a name="internal-risks-and-information-protection"></a>内部リスクと情報保護

### <a name="native-support-for-microsoft-365-security-without-additional-software"></a>追加のソフトウェアなしで Microsoft 365 セキュリティをネイティブでサポート

IT 管理者は、外部の脅威以外にも、内部リスクに対して保護する必要があります。 企業の機密データを規模に応じて確実に保護することは、特に従業員が分散している今、IT 管理者にとっての最優先事項です。 Microsoft Edge は、Azure AD の条件付きアクセス、Windows 情報保護、新しい Microsoft エンドポイントのデータ損失防止 (DLP) を追加のソフトウェアなしでネイティブでサポートする唯一のブラウザーです。

**Microsoft Edge は、条件付きアクセスをネイティブにサポートする唯一のブラウザーです**。 [Microsoft Edge による条件付きアクセスのサポート](ms-edge-security-conditional-access.md)により、組織は ID シグナルをアクセス制御に関する決定事項の一部として簡単に活用できます。 [条件付きアクセス](/azure/active-directory/conditional-access/overview)は、Azure Active Directory がシグナルをまとめ、決定を行い、組織のポリシーを強制するのに使用するツールです。 条件付きアクセスは、新しい ID を活用したコントロール プレーンの中核をなしています。 Chrome で条件付きアクセスがサポートされるようにするには、追加のプラグインが必要です。

> [!NOTE]
> Azure AD の条件付きアクセスには、Microsoft 365 E3 以降のサブスクリプションが必要です。

**Microsoft Edge は、Windows 情報保護 (WIP) をネイティブでサポートする唯一のブラウザーです。** これは、企業データを保護し、Windows 10 デバイスでユーザーによる偶発的な漏洩を防ぐのに役立ちます。 [Microsoft Edge による WIP のサポート](./microsoft-edge-security-windows-information-protection.md)は、企業データへのアクセスを IT 管理者が義務付けたアプリだけに許可するように構成できます。 また、シームレスなユーザー エクスペリエンスと共に、クリップボード保護、ダウンロード時のファイルの暗号化、承認されていないネットワーク共有やクラウド上の場所へのファイルのアップロード防止などの漏洩制御も提供します。 WIP は、境界ベースの構成で動作します。この構成では、IT 管理者が企業の境界を定義し、境界内のすべてのデータが企業データと見なされます。 Chrome の場合、漏洩制御を含む WIP には対応していません。

> [!NOTE]
> Windows 情報保護 (WIP) の構成には、Microsoft Intune または Microsoft Endpoint Configuration Manager のライセンスが必要です。もしくは、サード パーティのモバイル デバイス管理 (MDM) ソリューションを使用できますが、これには追加のライセンス要件がある場合があります。

**Microsoft エンドポイントのデータ損失防止 (エンドポイント DLP) は、Microsoft Edge でネイティブでのみサポートされます**。 エンドポイント DLP は Microsoft Security Center と統合され、Microsoft Edge の情報保護を強化して、ユーザーに対して非準拠アクティビティを通知し、ユーザーがオンラインで作業しているときにデータの損失を防ぐことができます。 クレジット カード番号や行政上の ID (社会保障番号など)、財務情報を含むファイルなど、管理者が定義した基準と一致する企業内の機密データを検出し、ラベルを付けます。Microsoft の情報保護ポリシーは、機密情報の識別子や IT 管理者が既にカスタマイズしたポリシーも含め、Microsoft エンドポイント データ損失防止に追加の再構成なしで展開できます。 これは IT 管理者にとって、情報保護のシームレスな展開です。

エンドポイント DLP の前提条件とその設定方法の詳細については、「[エンドポイントのデータ損失防止の使用を開始する](/microsoft-365/compliance/endpoint-dlp-getting-started?preserve-view=true&view=o365-worldwide)」を参照してください。

> [!NOTE]
> Microsoft 365 E5 または Microsoft 365 E5 Compliance サブスクリプションは、Microsoft エンドポイントのデータ損失防止のために必要です。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [ビデオ: Microsoft Edge のセキュリティ、互換性、管理の容易さ](microsoft-edge-video-security-compatibility-manageability.md)