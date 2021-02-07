---
title: Microsoft Edge の展開を計画する
ms.author: collw
author: appcompatguy
manager: srugh
ms.date: 02/05/2021
audience: ITPro
ms.topic: procedural
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge の展開を計画する
ms.openlocfilehash: 1b56d9874550c2002cec0577a53a3bf5766e2805
ms.sourcegitcommit: 16a92a51560fdba6f6480e4533453348f026c7ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "11313877"
---
# Microsoft Edge の展開を計画する

この記事では、エンタープライズ環境で Microsoft Edge を展開する際に推奨される方法について説明します。

>[!NOTE]
>この記事は Microsoft Edge version 77 以降に適用されます。

以降のセクションでは、Microsoft Edge の展開を計画するための具体的なガイダンスを提供します。

- [ブラウザーの環境と要件を評価する](#evaluate-your-existing-browser-environment-and-browser-needs)
- [Windows 10 デバイスの準備ができていることを確認します](#make-sure-your-windows-10-devices-are-ready)
- [展開方法の選択](#determine-your-deployment-methodology)
- [サイト検出を実行する](#do-site-discovery)
- [チャネル戦略の選択](#determine-your-channel-strategy)
- [ポリシーを識別し構成する](#define-and-configure-policies)
- [アプリの互換性をテストする](#do-app-compatibility-testing)
- [Microsoft Edge パイロット](#deploy-microsoft-edge-to-a-pilot-group)
- [パイロットの評価](#validate-your-deployment)
- [Microsoft Edge をエンタープライズ全体に展開する](#broad-deployment-of-microsoft-edge)

## 既存のブラウザー環境とブラウザーのニーズを評価する

現在のブラウザーの状態とプロジェクトのビジョンを把握するための時間を取り、すべてのプロジェクトの利害関係者が同じ結果に向かって作業していることを確認します。

現在の状態を明確にすることから開始します。

- 現在どのブラウザーが環境に展開されていますか。
- どのブラウザーが既定のブラウザーとして設定されていますか。
- 一部のアプリで Internet Explorer を使用する必要がありますか。
- 現在、エンタープライズモードサイト一覧を使用して Internet Explorer を構成していますか。
- お客様の環境でどの OS プラットフォームがサポートされていますか  (Windows 10、macOS、Windows 7、Windows Server など)。
- ブラウザー管理にどのような管理ツールを使用していますか。
- ブラウザーの構成と管理を担当するのはだれですか。
- ブラウザーの互換性を検証するプロセスはどのようなものですか。

現在の状態を把握したら、次のことを考慮して、適切なブラウザー展開の目標を決定できます。

- [Microsoft Edge を既定のブラウザーとして設定する](https://docs.microsoft.com/DeployEdge/edge-default-browser)必要がありますか。
- どのように [Microsoft Edge を構成](https://docs.microsoft.com/DeployEdge/configure-microsoft-edge)しますか。
- 初期展開では、どのような機能を構成する必要がありますか。
- 特定された互換性または構成の問題に対処するためのプロセスはどのようなものですか。

また、関心のある次のような機能の**前提条件**についても理解しておく必要があります。

- [Windows Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-guard/reqs-wd-app-guard)
- [Internet Explorer モード](https://docs.microsoft.com/DeployEdge/edge-ie-mode)
- [認証と同期](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-identity)

これらの回答を考慮することで、Microsoft Edge の展開を計画する準備が整いました。
<!--bookmark -->

## Windows 10 デバイスの準備ができていることを確認します

Edge Stableチャネルでは、2019年10月以降 (またはそれ以降) の最新の累積更新プログラム (LCU) を必要とします。 以前の LCU を含む Windows 10 デバイスに展開しようとすると、インストールが失敗します。 Edgeを展開する前に適用する必要がある最小限の LCU についての詳細は、[「Windows update を する」](https://docs.microsoft.com/DeployEdge/microsoft-edge-sysupdate-windows-updates)を参照してください。

## 展開方法を決定する

目指している最終的な状態を把握できたら、そこに到達するための計画を開始します。 Microsoft Edge を展開するための主な方法は、ロール別に展開する方法と、サイト別に展開する方法の 2 つです。

### ロール別にエンド ユーザーに展開する

アプリの互換性が主な問題であり、どのアプリをテストする必要があるかを把握していない場合は、ロール別にエンド ユーザーに展開することを検討します。 これにより、段階的な展開の各グループで、互換性の問題に対処するために構成を変更する必要があるアプリについてのフィードバックやインサイトを得ることができます。

### サイト別にエンド ユーザーに展開する

帯域幅が主な問題である場合は、事前にアプリケーションの互換性テストを実施することを検討します。 テストが完了したら、サイト別にエンド ユーザーに展開して、他のソフトウェア配信の最適化のキャッシュを活用できるようにします。

## サイト検出を実行する

レガシ Web アプリケーションに依存しており、Internet Explorer モードの使用を計画している場合 (ほとんどのお客様が該当)、追加のサイト検出の実行が必要になる可能性があります。

### レガシ バージョンの Microsoft Edge を既に展開し、構成している場合

レガシ バージョンの Microsoft Edge で使用するようにエンタープライズ サイト一覧が既に構成されている場合、作業はほぼ完了です。 ニュートラル サイトの追加が必要になる場合があります。

ニュートラルサイトは、通常、シングル サインオン (SSO) を提供するサイトです。 Microsoft Edge からニュートラル サイトに移動する場合は、Microsoft Edge で認証する必要があります。 Internet Explorer モードでニュートラル サイトに移動する場合は、Internet Explorer モードで認証する必要があります。

使用する SSO (またはその他のニュートラル) サイトを特定し、エンタープライズ サイト一覧に追加します。

### 既定のブラウザーとして Internet Explorer を構成していた場合

現在、Internet Explorer のみを使用している場合は、どのサイトが最新の Web 標準にアップグレードされ、どのサイトでまだ Internet Explorer が必要であるかを把握していない可能性があります。 これらのサイトを検索して、エンタープライズ サイト一覧に追加する必要があります。 これにより、必要なサイトでのみ Internet Explorer モードを使用できます。

> [!TIP]
> [Enterprise Site Discovery](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery?redirectedfrom=MSDN) ツールを使用して、Internet Explorer モードを必要とする可能性があるサイトを検出します。 Windows 10、Windows 8.1、Windows 7 で、Windows Internet Explorer 8 から Internet Explorer 11 までを実行しているコンピューターでデータを収集できます。

### サイト検出データを分析する

サイト データを収集した後、次の 4 つの手順を実行してデータを分析することをお勧めします。

1. データをドメインごと、次に URL ごとに並べ替えます。
2. Internet Explorer モード用に構成する "アプリ" の境界を定義します。 アプリを定義するすべてのサイトと Web コントロールを含める必要があります。 ただし、アプリの定義を広くしすぎるすることで、余分なサイトやコントロールを含めないようにします。 サイトによって、"http://contoso.com/app1" のように単純なものもあれば、複数のサイトやページを定義する必要があるものもあります。
3. アプリをテストして、ネイティブに機能していないことを確認します。 多くのサイトでは、最新のブラウザーが検出されると最新のコンテンツが提供され、Internet Explorer が検出された場合にのみレガシ コンテンツが提供されます。
4. アプリがテストではねられた場合は、エンタープライズ サイト一覧にアプリを追加します。

   > [!NOTE]
   > ベスト プラクティスとして、アプリを構成するすべてのサイトをグループ化することをお勧めします。 1 つのタスクを実行するためにすべてのサイトを使用する必要がある場合、およびそれらがまとめて更新される傾向がある場合は、そのサイトをグループ化することをお勧めします。 これにより、アプリをアップグレードするときに、サイト全体を Internet Explorer モードから削除し、そのアプリに最新のブラウザーを使用し始めるのが簡単になります。

## チャネル戦略を決定する

Microsoft Edge は[複数のチャネル](https://docs.microsoft.com/DeployEdge/microsoft-edge-channels)でリリースされます。

> [!NOTE]
> 1 台のデバイスに複数のチャネルをインストールできます。

Stable チャネルは、ほとんどのデバイスに展開する必要があります。 ただし、複数のデバイスと複数のチャネルを含む展開戦略を検討する必要があります。

### 複数のデバイスとチャネル

Beta チャネルを使用するように構成されたデバイスの代表的なサブセットを用意することをお勧めします。 これにより、ブラウザーに対する今後の変更点をプレビューできます。 これらの変更点がエンド ユーザーまたはアプリに影響するかどうかを確認できます。

また、Dev チャネル (または Canary チャネル) を Web 開発者などの一部のロールで使用できるようにすることもできます。 より流動的で急速に変化するチャネルで一部のデバイスをターゲットにするか、またはこれらのチャネルをユーザーがインストールすることを選択できるようにするかを検討します。

1 台のデバイスに複数のチャネルをインストールできるため、プレリリース版のチャネルをインストールすることを選択したユーザーについてテストのリスクを軽減することができます。 たとえば、Beta チャンネルを使用しているユーザーがいて、問題が発生した場合、ユーザーは Stable チャンネルに切り替えて作業を続けることができます。 これにより、問題を解決できるようになるまでの間も、ユーザーはブロックされません。

> [!NOTE]
> ユーザーが同期を有効にした場合、その構成はチャネル間で同期されるため、チャネル間の移行がさらに容易になります。

## ポリシーを定義および構成する

エンタープライズ サイト一覧を作成したら、Microsoft Edge を使用して展開する予定のポリシーを特定し、構成することをお勧めします。 これにより、テストの実行時にこれらのポリシーが確実に適用されます。

最初に、ユーザーに提供する初回実行時のエクスペリエンスを検討します。 現在のブラウザーから自動的に設定をインポートする場合は、[AutoImportAtFirstRun](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autoimportatfirstrun) のポリシーを構成します。

セキュリティ ポリシーについては、Microsoft Edge セキュリティ ベースラインから始めることをお勧めします。 セキュリティベース ラインは、[推奨されるセキュリティ ベースラインの設定](https://techcommunity.microsoft.com/t5/Microsoft-Security-Baselines/Security-baseline-DRAFT-for-Chromium-based-Microsoft-Edge/ba-p/949991)または [Microsoft Intune](https://docs.microsoft.com/intune/protect/security-baseline-settings-edge) を使用して適用できます。

その他のポリシーについては、[Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policies) と [Microsoft Edge Update](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) のポリシー構成を確認することをお勧めします。

### 更新の戦略とポリシーを定義する

Microsoft Edge の展開後に更新プログラムを実行する方法を決定することもできます。

- **Microsoft Edge の自己更新を許可する** (既定)。 Microsoft Edge の自動更新を許可するように選択した場合、展開したチャネルによって決定されているペースで Microsoft Edge が自動的に更新されます。
- **ユーザーのペースで Microsoft Edge を更新する** 更新プログラムを展開するタイミングを明示的に制御する場合は、自動更新を無効にして自分で展開することができます ([更新ポリシー リファレンス](https://docs.microsoft.com/DeployEdge/microsoft-edge-update-policies)を参照してください)。自動更新を無効にした後、次のいずれかのツールを使用して、各チャネルの更新プログラムを展開できます。

- [Intune](https://docs.microsoft.com/intune/apps/apps-windows-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json)
- [Configuration Manager](https://docs.microsoft.com/DeployEdge/deploy-edge-with-configuration-manager)
- 選択した展開ツール

更新戦略に関係なく、リングによる展開戦略を活用することをお勧めします。 自動更新では、Beta チャネルを実行しているユーザーの代表的なサンプルに、Stable チャネルになる候補に関する問題を特定してもらうことを意味します。 手動更新では、新しい Stable チャネル ビルドがリリースされた後に、パイロット グループの追加の検証を含めるような場合もあります。 この後に、広範な展開が行われます。

>[!NOTE]
>Microsoft Edge のサポートは、各チャネルの最新バージョンの Microsoft Edge にのみ適用されます。

## アプリの互換性テストを実行する

Microsoft Edge のアプリケーションの互換性は非常に高いため、Microsoft は互換性に関する次のような約束をしています。

1. Microsoft Edge *version 45 以前*で動作している場合、Microsoft Edge *version 77 以降*でも動作します。
2. Internet Explorer で機能している場合、Internet Explorer モードの Microsoft Edge でも動作します。
3. Google Chrome で機能している場合、Microsoft Edge でも動作します。

この互換性の約束が果たされていないアプリケーションがある場合、Microsoft は [Microsoft App Assure](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure) によってお約束通り、アプリの修正を行います。

### 内部機関業務アプリのテスト

このように互換性の約束をしていますが、多くの組織では自社のコンプライアンスまたはリスク管理の理由から一部のアプリケーションを検証する必要があるということも理解しています。 これは非常に簡単であると予測されますが、アプリのテストは整理して厳格に実行することが重要です。

アプリの互換性テストを行うには、2 つの方法があります。

1. ラボ テスト。 アプリケーションは、特定の構成を持つ厳格に制御された環境で検証されます。
2. パイロット テスト。 アプリケーションは、日常的な作業環境で、限られた数のユーザーが自分のデバイスを使用することによって検証されます。

互換性テストに過剰投資を行わずにリスクを管理するために、各アプリに最適な方法を選択します。

### サード パーティ製のアプリのサポート

独自の基幹業務アプリに加えて、多くの組織は、外部ソースによって提供されるアプリを使用します。 [[Microsoft Edge 用 に準備されている](deploy-edge-ready-for-edge.md)] の記事には、組織内で使用されている可能性のある Web アプリケーションの一覧が含まれています。 このリストでは、Microsoft Edge と共に使用した際の製品のプロバイダー サポート ステートメントへのリンクを提供します。

## パイロット グループに Microsoft Edge を展開する

ポリシーを定義し、初期のアプリの互換性テストが完了したら、パイロット グループに展開できます。 次のいずれかのツールを使用して、パイロット グループに展開します。

- [Windows 用の Microsoft Intune](https://docs.microsoft.com/intune/apps/apps-windows-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json) または [macOS 用の Microsoft Intune](https://docs.microsoft.com/intune/apps/apps-edge-macos?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json)
- [Configuration Manager](https://docs.microsoft.com/DeployEdge/deploy-edge-with-configuration-manager)
- 別の管理ツールで、[Microsoft Edge 用の MSI ファイル](https://www.microsoftedgeinsider.com/enterprise)をダウンロードして展開します。

## 展開を検証する

パイロットを展開した後、ユーザーからのすべてのフィードバックを取得する必要があります。

- 互換性に関するフィードバックを取得します。 エンタープライズ サイト一覧に含まれていて、サイト検出中に識別されなかったサイトを特定します。
- ポリシー構成に関するフィードバックを取得します。 セキュリティ ガイドラインを遵守しながら、ユーザーが主要な機能を使用して、作業を確実に行うことができるようにします。
- 使いやすさと新機能に関するフィードバックを取得します。 ユーザーの疑問点に基づきトレーニングを開発して実施する必要がある領域を特定します。

## Microsoft Edge の広範な展開

パイロットを完了し、パイロットから学んだ教訓を使用して展開計画を更新した後、すべてのユーザーに Microsoft Edge の完全な展開を行うことができます。  お疲れさまでした。

## 関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [ビデオ - Microsoft Edge の展開](microsoft-edge-video-deploy.md)
