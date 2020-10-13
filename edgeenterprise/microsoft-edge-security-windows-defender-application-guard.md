---
title: Microsoft Edge および Microsoft Defender Application Guard
ms.author: srugh
author: dan-wesley
manager: seanlyn
ms.date: 10/12/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge での Microsoft Defender Application Guard のサポート
ms.openlocfilehash: fcf9bb6e36ddd5e014bd8176643554bfe3ff8fd4
ms.sourcegitcommit: b813f91803b8f0f27489634f49e7e0585b746d48
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114365"
---
# Microsoft Edge での Microsoft Defender Application Guard のサポート

この記事では、Microsoft Edge による Microsoft Defender Application Guard (Application Guard) のサポートについて説明します。

> [!NOTE]
> この記事は Microsoft Edge version 77 以降に適用されます。

## 概要

エンタープライズのセキュリティ設計者は、生産性とセキュリティとの間の葛藤に取り組む必要があります。 ブラウザーをロック ダウンし、少数の信頼されたサイトだけを読み込むようにするのは比較的簡単です。 このアプローチにより全体的なセキュリティ態勢を向上させることはできますが、生産的とは言えないでしょう。 生産性を向上するために制限を緩めると、リスク プロファイルは増大します。 バランスを取るのは簡単ではありません。

脅威の情勢は常に変化しているため、新たな脅威に対抗し続けるのはさらに大変です。 ブラウザーの基本的な役割は、ユーザーが信頼されていないソースからの信頼されていないコンテンツにアクセスし、ダウンロードして開けるようにすることであるため、ブラウザーはクライアント デバイスにおける主要な攻撃対象であり続けています。 悪意のある攻撃者は、ブラウザーに対する新しい形態の攻撃をソーシャル エンジニアリングの手法で仕掛けることに余念がありません。 セキュリティ インシデントの防止または検出/対応の戦略では、100% の安全性を保証できません。

検討すべき重要なセキュリティ対策は、[侵害を想定する手法](https://docs.microsoft.com/office365/Enterprise/office-365-monitoring-and-testing#assume-breach-methodology)です。これは、攻撃を防ぐ努力をしたとしても、少なくとも 1 度は攻撃が成功することを受け入れることを意味しています。 この考え方では、被害を抑えるための防御を構築することが必要になります。こうすれば、このシナリオにおいて、企業のネットワークと他のリソースを保護し続けることが可能になります。  Microsoft Edge に Application Guard を展開することは、この戦略にうまく適合します。

## Application Guard について

Application Guard は Windows 10 と Microsoft Edge 向けに設計されており、ハードウェア分離のアプローチを採用しています。 このアプローチでは、信頼されていないサイトへの移動はコンテナー内で行われます。 ハードウェア分離により、エンタープライズは、セキュリティが侵害されたサイトや悪意のあるサイトにユーザーがアクセスした場合でも、企業のネットワークとデータを保護することができるようになります。

エンタープライズ管理者は、信頼済みサイト、クラウド リソース、内部ネットワークを定義します。 信頼済みサイトのリストに入っていないものはすべて、信頼されていないと見なされます。 これらのサイトは、ユーザーのデバイス上で企業ネットワークとデータから分離されます。

詳細については、「[Application Guard の概要とその仕組み](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview#what-is-application-guard-and-how-does-it-work)」を参照してください。

次のスクリーンショットは、ユーザーが安全なサイトを閲覧していることを示す Application Guard のメッセージの例です。

![安全な閲覧を示す Application Guard のメッセージ](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-1.png)

## 新着情報

新しい Microsoft Edge ブラウザーでの Application Guard のサポートは、Microsoft Edge 従来版と機能的に同等であり、いくつかの改善が含まれています。

### コンテナー内の拡張機能サポート

コンテナー内の拡張機能サポートは、お客様からの上位のリクエストの 1 つでした。 ブラウザーのパフォーマンスを向上するためにコンテナー内で広告ブロック機能を実行することから、コンテナー内で自社製のカスタム拡張機能を実行できるようにすることまで、シナリオは多岐にわたります。

Microsoft Edge バージョン 81 から、コンテナー内での拡張機能のインストールがサポートされるようになりました。 このサポートは、ポリシーを使用して制御できます。 [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist) ポリシーで使用される `updateURL` は、Application Guard が使用するネットワークの分離ポリシーでニュートラル リソースとして追加する必要があります。

コンテナーのサポートの例には、次のようなシナリオが含まれます。

- ホストでの拡張機能のインストールを強制する
- ホストから拡張機能を削除する
- ホストで拡張機能がブロックされる

> [!NOTE]
> また、拡張機能ストアからコンテナー内に個々の拡張機能を手動でインストールすることも可能です。 手動でインストールされた拡張機能は、[永続化の許可](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard#application-specific-settings)ポリシーが有効な場合にのみ、コンテナーで保持されます。

### デュアル プロキシを介した Application Guard トラフィックの識別

一部の企業のお客様は、Microsoft Defender Application Guard コンテナーから送信される Web トラフィックをプロキシ レベルで識別する必要がある特定のユース ケースで Application Guard を展開しています。 安定チャネルのバージョン 84 以降、Microsoft Edge はデュアル プロキシをサポートしてこの要件に対応します。 この機能は、[ApplicationGuardContainerProxy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#applicationguardcontainerproxy) ポリシーを使用して構成できます。

次の図は、Microsoft Edge のデュアル プロキシ アーキテクチャを示しています。

![Application Guard のデュアル プロキシ アーキテクチャ](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-dual-proxy.png)

### トラブルシューティングのための診断ページ

ユーザーにとってのもう一つの問題点は、問題が報告されたときにデバイス上で Application Guard の構成をトラブルシューティングすることです。 Microsoft Edge には、ユーザーの問題をトラブルシューティングするための診断ページ (`edge://application-guard-internals`) があります。 これらの診断の 1 つは、ユーザー デバイス上の構成に基づいて URL の信頼性を確認することです。

次のスクリーンショットは、デバイス上でユーザーが報告した問題の診断に役立つ、複数のタブを含む診断ページを示しています。

![Application Guard の診断ページ](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-2.png)

### コンテナーでの Microsoft Edge の更新

コンテナーでの Microsoft Edge 従来版の更新は、Windows OS の更新サイクルに含まれています。 新しいバージョンの Microsoft Edge の更新そのものは Windows OS から独立しているため、コンテナーの更新への依存関係はなくなりました。 ホストの Microsoft Edge のチャネルとバージョンは、コンテナー内で複製されます。

## 前提条件

次の要件は、Application Guard を Microsoft Edge で使用するデバイスに適用されます。

- Windows 10 1809 (RS5) 以降。
- Windows クライアント SKU のみ

  > [!NOTE]
  > Application Guard は、Windows 10 Pro と Windows 10 Enterprise SKU でのみサポートされます。

- [ソフトウェア要件](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard#software-requirements)に記載されている管理ソリューションのいずれか

## Application Guard のインストール方法

Application Guard をインストールし、Microsoft Edge で構成およびテストするために必要な情報は、次の記事を参照してください。

- [システム要件](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)
- [Microsoft Defender Application Guard のインストール](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)
- [Microsoft Defender Application Guard ポリシー設定の構成](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard)
- [Application Guard をテストする](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/test-scenarios-md-app-guard)

## よく寄せられる質問

### Application Guard は IE モードで動作しますか?

IE モードは Application Guard の機能をサポートしていますが、IE モードでのこの機能の使用はあまり想定されていません。 IE モードは信頼済み内部サイトのリストに対して展開されることが推奨されており、Application Guard は信頼されていないサイトのみを対象としています。 Application Guard によって信頼済みリソースとみなされるようにするため、すべての IE モードのサイトや IP アドレスが、ネットワークの分離ポリシーにも追加されていることを確認してください。

### Application Guard の Chrome 拡張機能をインストールする必要はありますか?

いいえ。Application Guard 機能は Microsoft Edge でネイティブでサポートされています。 事実、Application Guard の Chrome 拡張機能の構成は、Microsoft Edge ではサポートされていません。

### FAQ に関連する他のプラットフォームはありますか?

はい、できます。 [よく寄せられる質問: Microsoft Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/faq-md-app-guard) 

## 関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [ビデオ: Application Guard を使用した Microsoft Edge ブラウザー分離](https://www.youtube.com/watch?v=zQjaRqNXMqw&t=3s)
