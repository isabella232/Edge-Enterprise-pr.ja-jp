---
title: Microsoft Edge および Microsoft Defender Application Guard
ms.author: srugh
author: AndreaLBarr
manager: seanlyn
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge での Microsoft Defender Application Guard のサポート
ms.openlocfilehash: 6273204cc66fa90b1840f279106b3a26d895ca96
ms.sourcegitcommit: 9088e839e82d80c72460586e9af0610c6ca71b83
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2021
ms.locfileid: "11675964"
---
# <a name="microsoft-edge-support-for-microsoft-defender-application-guard"></a>Microsoft Edge での Microsoft Defender Application Guard のサポート

この記事では、Microsoft Edge による Microsoft Defender Application Guard (Application Guard) のサポートについて説明します。

> [!NOTE]
> この記事は Microsoft Edge version 77 以降に適用されます。

## <a name="overview"></a>概要

エンタープライズのセキュリティ設計者は、生産性とセキュリティとの間の葛藤に取り組む必要があります。 ブラウザーをロック ダウンし、少数の信頼されたサイトだけを読み込むようにするのは比較的簡単です。 このアプローチにより全体的なセキュリティ態勢を向上させることはできますが、生産的とは言えないでしょう。 生産性を向上するために制限を緩めると、リスク プロファイルは増大します。 バランスを取るのは簡単ではありません。

脅威の情勢は常に変化しているため、新たな脅威に対抗し続けるのはさらに大変です。 ブラウザーの基本的な役割は、ユーザーが信頼されていないソースからの信頼されていないコンテンツにアクセスし、ダウンロードして開けるようにすることであるため、ブラウザーはクライアント デバイスにおける主要な攻撃対象であり続けています。 悪意のある攻撃者は、ブラウザーに対する新しい形態の攻撃をソーシャル エンジニアリングの手法で仕掛けることに余念がありません。 セキュリティ インシデントの防止または検出/対応の戦略では、100% の安全性を保証できません。

検討すべき重要なセキュリティ対策は、[侵害を想定する手法](/office365/Enterprise/office-365-monitoring-and-testing#assume-breach-methodology)です。これは、攻撃を防ぐ努力をしたとしても、少なくとも 1 度は攻撃が成功することを受け入れることを意味しています。 この考え方では、被害を抑えるための防御を構築することが必要になります。こうすれば、このシナリオにおいて、企業のネットワークと他のリソースを保護し続けることが可能になります。  Microsoft Edge に Application Guard を展開することは、この戦略にうまく適合します。

## <a name="about-application-guard"></a>Application Guard について

Application Guard は Windows 10 と Microsoft Edge 向けに設計されており、ハードウェア分離のアプローチを採用しています。 このアプローチでは、信頼されていないサイトへの移動はコンテナー内で行われます。 ハードウェア分離により、エンタープライズは、セキュリティが侵害されたサイトや悪意のあるサイトにユーザーがアクセスした場合でも、企業のネットワークとデータを保護することができるようになります。

エンタープライズ管理者は、信頼済みサイト、クラウド リソース、内部ネットワークを定義します。 信頼済みサイトのリストに入っていないものはすべて、信頼されていないと見なされます。 これらのサイトは、ユーザーのデバイス上で企業ネットワークとデータから分離されます。

詳しくは、次のトピックをご覧ください。

- Application Guard を使用した [Microsoft Edge ブラウザー分離に関するビデオをご覧ください](microsoft-edge-video-security-application-guard.md)
- 「[Application Guard の概要とその仕組み](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview#what-is-application-guard-and-how-does-it-work)」を参照してください

次のスクリーンショットは、ユーザーが安全なサイトを閲覧していることを示す Application Guard のメッセージの例です。

![安全な閲覧を示す Application Guard のメッセージ](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-1.png)

## <a name="whats-new"></a>新着情報

新しい Microsoft Edge ブラウザーでの Application Guard のサポートは、Microsoft Edge 従来版と機能的に同等ですが、いくつかの改善が含まれています。

### <a name="favorites-synchronizing-from-the-host-to-the-container"></a>ホストからコンテナーに同期するお気に入り

一部のお客様は、Application Guard のホスト ブラウザーとコンテナーの間でお気に入りの同期を求める場合があります。 Microsoft Edge 91 から、ユーザーはホストからコンテナーに自分のお気に入りを同期するために Application Guard を構成するオプションを使用できます。 これにより、コンテナーにも新しいお気に入りが表示されます。

このサポートは、ポリシーを使用して制御できます。 Edge ポリシー [ApplicationGuardFavoritesSyncEnabled](/deployedge/microsoft-edge-policies#applicationguardfavoritessyncenabled) を更新して、お気に入りの同期を有効または無効にできます。

> [!Note]
> セキュリティ上の理由から、お気に入りの同期はホストからコンテナーの方向にのみ可能であり、それ以外の方法では可能ではありません。 ホストとコンテナー間で統一されたお気に入りの一覧を提供するために、コンテナー内でお気に入り管理を無効にしました。

### <a name="identify-network-traffic-originating-from-the-container"></a>コンテナーから発信されるネットワーク トラフィックを識別する

コンテナーから送信されるネットワーク トラフィックを識別する特定の構成で WDAG を使用しているお客様もいます。 このシナリオの一部は次のとおりです。

- 一握りの信頼されていないサイトにのみアクセスを制限するには
- コンテナーからのインターネット アクセスのみを許可するには

Microsoft Edge バージョン 91 から、Application Guard コンテナーから発信されるネットワーク トラフィックにタグ付けするサポートが組み込まれたため、企業はプロキシを使用してトラフィックをフィルター処理し、特定のポリシーを適用できます。 ヘッダーを使用して [、ApplicationGuardTrafficIdentificationEnabled](/deployedge/microsoft-edge-policies#applicationguardtrafficidentificationenabled)を使用して、どのトラフィックがコンテナー経由か、ホスト経由かを識別できます。

### <a name="extension-support-inside-the-container"></a>コンテナー内の拡張機能サポート

コンテナー内の拡張機能サポートは、お客様からの上位のリクエストの 1 つでした。 ブラウザーのパフォーマンスを向上するためにコンテナー内で広告ブロック機能を実行することから、コンテナー内で自社製のカスタム拡張機能を実行できるようにすることまで、シナリオは多岐にわたります。

Microsoft Edge バージョン 81 から、コンテナー内での拡張機能のインストールがサポートされるようになりました。 このサポートは、ポリシーを使用して制御できます。 [ExtensionInstallForcelist](./microsoft-edge-policies.md#extensioninstallforcelist) ポリシーで使用される `updateURL` は、Application Guard が使用するネットワークの分離ポリシーでニュートラル リソースとして追加する必要があります。

コンテナーのサポートの例には、次のようなシナリオが含まれます。

- ホストでの拡張機能のインストールを強制する
- ホストから拡張機能を削除する
- ホストで拡張機能がブロックされる

> [!NOTE]
> また、拡張機能ストアからコンテナー内に個々の拡張機能を手動でインストールすることも可能です。 手動でインストールされた拡張機能は、[永続化の許可](/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard#application-specific-settings)ポリシーが有効な場合にのみ、コンテナーで保持されます。

### <a name="identifying-application-guard-traffic-via-dual-proxy"></a>デュアル プロキシを介した Application Guard トラフィックの識別

一部の企業のお客様は、Microsoft Defender Application Guard コンテナーから送信される Web トラフィックをプロキシ レベルで識別する必要がある特定のユース ケースで Application Guard を展開しています。 安定チャネルのバージョン 84 以降、Microsoft Edge はデュアル プロキシをサポートしてこの要件に対応します。 この機能は、[ApplicationGuardContainerProxy](./microsoft-edge-policies.md#applicationguardcontainerproxy) ポリシーを使用して構成できます。

次の図は、Microsoft Edge のデュアル プロキシ アーキテクチャを示しています。

![Application Guard のデュアル プロキシ アーキテクチャ](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-dual-proxy.png)

### <a name="diagnostic-page-for-troubleshooting"></a>トラブルシューティングのための診断ページ

ユーザーにとってのもう一つの問題点は、問題が報告されたときにデバイス上で Application Guard の構成をトラブルシューティングすることです。 Microsoft Edge には、ユーザーの問題をトラブルシューティングするための診断ページ (`edge://application-guard-internals`) があります。 これらの診断の 1 つは、ユーザー デバイス上の構成に基づいて URL の信頼性を確認することです。

次のスクリーンショットは、デバイス上でユーザーが報告した問題の診断に役立つ、複数のタブを含む診断ページを示しています。

![Application Guard の診断ページ](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-2.png)

### <a name="microsoft-edge-updates-in-the-container"></a>コンテナーでの Microsoft Edge の更新

コンテナーでの Microsoft Edge 従来版の更新は、Windows OS の更新サイクルに含まれています。 新しいバージョンの Microsoft Edge の更新そのものは Windows OS から独立しているため、コンテナーの更新への依存関係はなくなりました。 ホストの Microsoft Edge のチャネルとバージョンは、コンテナー内で複製されます。

## <a name="prerequisites"></a>前提条件

次の要件は、Application Guard を Microsoft Edge で使用するデバイスに適用されます。

- Windows 10 1809 (RS5) 以降。
- Windows クライアント SKU のみ

  > [!NOTE]
  > Application Guard は、Windows 10 Pro と Windows 10 Enterprise SKU でのみサポートされます。

- [ソフトウェア要件](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard#software-requirements)に記載されている管理ソリューションのいずれか

## <a name="how-to-install-application-guard"></a>Application Guard のインストール方法

Application Guard をインストールし、Microsoft Edge で構成およびテストするために必要な情報は、次の記事を参照してください。

- [システム要件](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)
- [Microsoft Defender Application Guard のインストール](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)
- [Microsoft Defender Application Guard ポリシー設定の構成](/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard)
- [Application Guard をテストする](/windows/security/threat-protection/microsoft-defender-application-guard/test-scenarios-md-app-guard)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="does-application-guard-work-in-ie-mode"></a>Application Guard は IE モードで動作しますか?

IE モードでは Application Guard の機能がサポートされますが、IE モードではこの機能を多用することは想定していません。 IE モードは、信頼された内部サイトの一覧に展開することをお勧めします。Application Guardは信頼されていないサイト専用です。 Application Guard によって信頼済みリソースとみなされるようにするため、すべての IE モードのサイトや IP アドレスが、ネットワークの分離ポリシーにも追加されていることを確認してください。

### <a name="do-i-need-to-install-the-application-guard-chrome-extension"></a>Application Guard の Chrome 拡張機能をインストールする必要はありますか?

いいえ。Application Guard 機能は Microsoft Edge でネイティブでサポートされています。 事実、Application Guard の Chrome 拡張機能の構成は、Microsoft Edge ではサポートされていません。

### <a name="can-employees-download-documents-from-the-application-guard-edge-session-onto-host-devices"></a>従業員は、Application Guard Edge セッションからホスト デバイスにドキュメントをダウンロードできますか。

バージョン Windows 10 Enterpriseバージョン 1803 では、ユーザーは分離された Application Guard コンテナーからホスト PC にドキュメントをダウンロードできます。 この機能はポリシーによって管理されます。

Windows 10 Enterprise バージョン 1709、または Windows 10 Professional エディションバージョン 1803 では、分離された Application Guard コンテナーからホスト コンピューターにファイルをダウンロードできません。 ただし、従業員は [Print as PDF] (PDF 形式で印刷) または [Print as XPS] (XPS 形式で印刷) オプションを使って、それらのファイルをホスト デバイスに保存できます。

### <a name="can-employees-copy-and-paste-between-the-host-device-and-the-application-guard-edge-session"></a>従業員は、ホスト デバイスと Application Guard Edge セッション間でコピーや貼り付けを実行できますか。

組織の設定に応じて、従業員はイメージ (.bmp) とテキストを分離コンテナーにコピーして貼り付けることができます。

### <a name="why-dont-employees-see-their-favorites-in-the-application-guard-edge-session"></a>従業員が Application Guard Edge セッションで自分のお気に入りを表示しない理由

組織の設定によっては、[お気に入り同期] がオフになっている可能性があります。 ポリシーを管理するには、「Microsoft EdgeとMicrosoft Defender Application Guard |Microsoft Docs。

### <a name="why-arent-employees-able-to-see-their-extensions-in-the-application-guard-edge-session"></a>従業員が Application Guard Edge セッションで拡張機能を表示できない理由

Application Guard 構成で拡張機能ポリシーを有効にしてください。

### <a name="my-extension-doesnt-seem-to-work-in-edge-application-guard"></a>拡張機能が Edge Application Guard で動作していないように見える

構成で MDAG に対して拡張機能ポリシーが有効になっている場合は、拡張機能にネイティブ メッセージ処理コンポーネントが必要な場合、それらの拡張機能は Application Guard コンテナーではサポートされません。

### <a name="im-trying-to-watch-playback-video-with-hdr-why-is-the-hdr-option-missing"></a>HDR で再生ビデオを見ようとしているのに、なぜ HDR オプションが見つからないのですか?

コンテナー内で HDR ビデオ再生を機能するには、Application Guard で vGPU ハードウェア アクセラレータを有効にする必要があります。

### <a name="are-there-any-other-platform-related-faqs"></a>FAQ に関連する他のプラットフォームはありますか?

はい、できます。 [よく寄せられる質問: Microsoft Defender Application Guard](/windows/security/threat-protection/microsoft-defender-application-guard/faq-md-app-guard) 

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Defender Advanced Threat Protection](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [ビデオ: Application Guard を使用した Microsoft Edge ブラウザー分離](https://www.youtube.com/watch?v=zQjaRqNXMqw&t=3s)
