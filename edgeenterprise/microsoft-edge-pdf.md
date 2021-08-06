---
title: Microsoft Edge の PDF リーダー
ms.author: adigan
author: AndreaLBarr
manager: balajek
ms.date: 07/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge の PDF リーダーについて説明します。
ms.openlocfilehash: b15632f75499e8271d38d85fd1a713a03f9171f896febbd59093fcc2585b3f37
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "11724990"
---
# <a name="pdf-reader-in-microsoft-edge"></a>Microsoft Edge の PDF リーダー

PDF ファイルは、私たちの毎日の生活の大きな部分をなしています。 これらは、契約書および合意書、ニュースレター、申込用紙、リサーチ記事、履歴書などのフォームに使用されます。 これらのファイルは、企業にとって高い信頼性、安全性、および性能を備えた PDF リーダーを採用する必要性を協調します。

Microsoft Edge には、組み込みの PDF リーダーが用意されています。このリーダーを使用すると、ローカル、オンライン、または Web ページに埋め込まれた PDF ファイルを開くことができます。 これらのファイルに注釈を付けて、インクや強調表示することができます。 この PDF リーダーでは、Web ページおよび PDF ドキュメントのニーズを満たす単一のアプリケーションが提供されます。 Microsoft Edge PDF リーダーは、Windows および macOS デスクトップ プラットフォームで動作する、安全で信頼性の高いアプリケーションです。

> [!NOTE]
> この記事は Microsoft Edge version 77 以降に適用されます。

## <a name="prerequisites-support-and-constraints"></a>前提条件、サポート、および制約

次の表は、Microsoft Edge で各 PDF リーダー機能をサポートするチャネルとバージョンを示しています。

| 機能 | Stable チャネル バージョン |
|---------|------------------------|
| ローカル、オンライン、および埋め込みの PDF ファイルを表示して印刷する | 79.0.309.71                |
| 基本フォームの入力<br>(JavaScript フォームはサポートされていません) | 79.0.309.71           |
|目次| 86.0.622.38 |
| ページ ビュー | 88.0.705.50 |
| キャレット モードのブラウジング |87.0.664.41 |
| インク操作  | 80.0.361.48            |
| インク操作のカスタマイズ | 83.0.478.54  |
| Highlight  | 81.0.416.53         |
| テキスト ノート | 88.0.705.50 |
| 音声読み上げ | 84.0.522.63  |
| 同じビジネス テナント内での Microsoft Information Protection (MIP) で保護されたファイルの表示 | 80.0.361.48 で Windows をサポート<br>81.0.416.53 で Mac をサポート |
| ビジネス テナント間での Microsoft Information Protection (MIP) で保護されたファイルの表示 | 91.0.864.37  |
|  Information Rights Management (IRM) で保護されたファイルの表示  | 83.0.478.37            |


### <a name="constraints"></a>制約

現在の PDF リーダーでは、次のような制約があります。

-  XML Forms Architecture (XFA) は、Microsoft Edge でサポートされていない旧式のフォームです。
-  現在サポートされていないアクセシビリティ シナリオに関連するドキュメントは、[Microsoft アクセシビリティ適合レポート](https://cloudblogs.microsoft.com/industry-blog/government/2018/09/11/accessibility-conformance-reports/) ブログに記載されています。

## <a name="features"></a>機能

Microsoft Edge に組み込まれた PDF リーダーには、[ズーム]、[回転]、[ページ/幅に合わせる]、[ページへジャンプ]、[検索] などの基本的な読み取り機能とナビゲーション機能が付属しています。 PDF コンテンツの上部にあるピン留め可能なツール バーからアクセスできます。 このセクションでは、いくつかの重要な機能の概要について説明します。 次のスクリーンショットは、PDF リーダー ツールバーを示しています。

![PDF リーダー ツールバー](media/microsoft-edge-pdf/pdf-reader-toolbar.png)

### <a name="table-of-contents"></a>目次

目次を使用すると、ユーザーは目次を含む PDF ドキュメント内を簡単に移動できます。 ユーザーが目次アイコンをクリックすると、ラベル付きのセクションとサブセクションの一覧を PDF ドキュメントに表示するナビゲーション ウィンドウが表示されます。 するとユーザーは、ウィンドウ内の任意のラベルをクリックして、ドキュメントのそのセクションに移動できます。 ウィンドウは必要な限り開いたままにされ、ユーザーがドキュメントの閲覧に戻るときに閉じることができます。 次のスクリーンショットは、開いているドキュメントのナビゲーション ウィンドウを示しています。

![目次を含む PDF リーダー ナビゲーション](media/microsoft-edge-pdf/pdf-reader-toc.png)

### <a name="page-view"></a>ページ ビュー

Microsoft Edge は、Dev チャネルと Canary チャネルで PDF ドキュメントのさまざまなビューをサポートしています。 ユーザーは、ドキュメントのレイアウトを 1 つのページ ビューから 2 つのページが並べて表示されるビューに変更できます。 PDF ドキュメントの表示方法を変更するには、PDF ツール バーの [ページ ビュー] ボタンをクリックし、使用するビューを選択します。 次のスクリーンショットは、2 ページ ビューを示しています。

![ドキュメントの 2 ページ ビューを使用した PDF リーダー。](media/microsoft-edge-pdf/pdf-reader-page-view.png)

### <a name="caret-mode-browsing"></a>キャレット モードのブラウジング

キャレット ブラウジングは、Microsoft Edge で開いた PDF ファイルで利用できます。つまり、ユーザーはキーボードを使用して PDF ファイルを操作できます。 ユーザーがブラウザーの任意の場所で F7 キーを押すと、キャレット ブラウジングを有効にすべきかどうかを確認するメッセージが表示されます。 有効にした場合、PDF ファイルか Web ページかにかかわらず、ブラウザーで開いたどのコンテンツにもキャレット ブラウジングを使用できます。 ユーザーがもう一度 F7 キーを押すと、キャレット ブラウジングはオフになります。 キャレット ブラウジングがアクティブで、コンテンツにフォーカスがある場合、PDF ファイルに点滅するカーソルが表示されます。 キャレットは、ファイル内を移動したり、カーソルを動かしながら Shift キーを押してテキストを選択したりするためにも使用できます。 この機能を使用すると、ユーザーは強調表示などの要素を簡単に作成したり、キーボードを使用してリンクやフォーム フィールドなどの要素を操作したりすることができます。 次のスクリーンショットは、キャレット モードのブラウジングをオンにするポップアップ メニューを示しています。

![キャレット モードのブラウジング用の PDF リーダー メニュー。](media/microsoft-edge-pdf/pdf-reader-caret-mode.png)

### <a name="inking"></a>インク操作

PDF ファイルのインク操作を行うと、 PDF フォームに手軽に参照できるメモを取ったり、サインしたり、記入したりすることができます。 この機能は、Microsoft Edge で使用できるようになりました。 必要に応じた PDF ファイルのインク操作に加えて、PDF の別の部分に注目を集めるために色を使用したりストロークの幅を使用したりすることができます。 次のスクリーンショットは、ユーザーが PDF ページにインク操作を追加できるようにする方法を示しています。

![PDF ページにインク操作を追加する](media/microsoft-edge-pdf/pdf-reader-inking.png)

### <a name="highlight"></a>Highlight

Microsoft Edge の PDF リーダーには、強調表示の追加と編集のサポートが用意されています。 強調表示を作成するには、シンプルにテキストを選択し、それを右クリックしてメニューの [強調表示] を選び、目的の色を選びます。 強調表示は、ペンまたはキーボードを使って作成することもできます。 次のスクリーンショットは、使用できる強調表示オプションを示しています。

![PDF リーダーで強調表示オプションを使用する](media/microsoft-edge-pdf/pdf-reader-highlight.png)

### <a name="text-notes"></a>テキスト ノート

PDF ファイルを読んでいる間、ファイル内のテキストにテキスト ノートを追加して、後で簡単に参照できるように考えを書き込むことができます。

ユーザーは、メモを追加するテキストを選択し、右クリックすると表示されるコンテキスト メニューを呼び出して、メモを追加できます。 メニューの **[コメントの追加]** オプションを選択すると、ユーザーがコメントを追加できるテキスト ボックスが開きます。 コメントを入力し、チェック マークをクリックしてコメントを保存できます。

メモを追加すると、選択したテキストが強調表示され、コメントを示すためのコメント アイコンが表示されます。 ユーザーは、そのアイコンをポイントしてコメントをプレビューしたり、クリックしてメモを開いて編集したりできます。

次のスクリーンショットは、強調表示されたテキストにメモが追加される様子を示しています。

![PDF リーダーがドキュメントにテキスト メモを追加しています。](media/microsoft-edge-pdf/pdf-reader-text-note.png)

### <a name="read-aloud"></a>音声読み上げ

PDF の音声読み上げは、ユーザーが重要なタスクを実行しながら PDF コンテンツを聞くことができる便利な機能です。 また、聴覚で学ぶ学習者が内容に集中することができるため、学習への取り組みがより簡単になります。 次のスクリーンショットに、音声読み上げの例を示します。 強調表示は現在読み上げているテキストを示しています。

![PDF リーダーの読み上げ機能で強調表示オプションを使用する](media/microsoft-edge-pdf/pdf-reader-read-aloud-example.png)

### <a name="protected-pdfs"></a>保護された PDF

[Microsoft Information Protection (MIP)](/microsoft-365/compliance/protect-information?preserve-view=true&view=o365-worldwide) により、ユーザーは組織のコンプライアンス ポリシーに準拠しながら、他のユーザーと安全に共同作業することが可能です。 ファイルが保護されると、ユーザーがファイルに実行できるアクションは割り当てられているアクセス許可によって決定されます。

> [!IMPORTANT]
> MIP にはライセンスが必要です。 詳細については、この「[Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)」を参照してください。

これらのファイルは、他のソフトウェアをダウンロードしたり、アドインをインストールしたりすることなく、ブラウザーで直接開くことができます。 この機能により、MIP が提供するセキュリティが直接ブラウザーに統合され、シームレスなワークフローを実現します。
MIP で保護されたファイルをビジネス テナント間で表示できます。 現在、コンシューマー ID を使用してファイルを表示する機能はサポートされていません。

![保護された PDF ドキュメント。](media/microsoft-edge-pdf/pdf-reader-protected-pdf2.png)

MIP で保護されたファイルに加えて、SharePoint ライブラリに保護された [Information Rights Management (IRM)](/microsoft-365/compliance/set-up-irm-in-sp-admin-center?preserve-view=true&view=o365-worldwide) 内の PDFファイルは、ブラウザーでネイティブに開くこともできます。

Microsoft Edge では、ユーザーはローカルまたはクラウドに保存されている MIP 保護ファイルを表示できます。 ローカルに保存した場合、ファイルをブラウザーで直接開くことができます。 クラウドサービスから SharePoint としてファイルを開いた場合、ユーザーは [ブラウザーで開く] オプションを使用することが必要になる場合があります。

ユーザーが Microsoft Edge にログインしているプロファイルに、少なくともファイルを表示するアクセス許可が与えられている場合、Microsoft Edge でファイルが開きます。

![MIP によって保護されている SharePoint PDF ページを保存するかどうかを尋ねるメッセージ](media/microsoft-edge-pdf/pdf-reader-sharepoint-irm.png)

### <a name="view-and-validate-certificate-based-digital-signatures"></a>証明書ベースのデジタル署名の表示と検証

このデジタルな世界では、ドキュメント内のコンテンツの信頼性と所有権を確立することが重要になります。 証明書ベースのデジタル署名は、ドキュメント内のコンテンツが作成者の意図した内容と同じであり、変更されていないことを確認するため、PDF ドキュメントでよく使用されます。 Microsoft Edge では、PDF で証明書のデジタル署名を表示し、検証できます。

Microsoft はさらに多くのシナリオに対処するため、サポートの改善に積極的に取り組んでいます。この機能についての皆様のフィードバックをお待ちしております。

## <a name="accessibility"></a>アクセシビリティ

PDF リーダーには、Windows および macOS デバイスでのキーボードのアクセシビリティ、ハイコントラスト モード、スクリーンリーダーのサポートが用意されています。

### <a name="keyboard-accessibility"></a>キーボードのアクセシビリティ

ユーザーは、キーボードを使用して、フォームフィールドや強調表示などのユーザーが操作できるドキュメントの一部に移動できます。 ユーザーはキャレット モードを使用して、キーボードで PDF ファイル内を移動して操作することもできます。

### <a name="high-contrast-mode"></a>ハイ コントラスト モード

PDF リーダーは、オペレーティング システム レベルで定義された設定を使用して、PDF コンテンツをハイ コントラスト モードで表示します。

### <a name="screen-reader-support"></a>スクリーン リーダーのサポート

ユーザーは、Windows および Mac コンピューターのスクリーン リーダーを使用して、PDF ファイル内を移動したり、読んだりすることができます。

## <a name="security-and-reliability"></a>セキュリティと信頼性

セキュリティは、あらゆる組織にとって最も重要な原則です。 PDF リーダーのセキュリティは、Microsoft Edge セキュリティの設計に必要不可欠です。 PDF リーダーの観点から最も重要なセキュリティ機能は2つあります。それは、プロセスの分離および Microsoft Defender Application Guard (Application Guard) です。

- プロセスの分離。 異なる Web サイトから開いた PDF は、プロセスが完全に分離されます。 ブラウザーは、いかなる Web サイトとも通信する必要はなく、別のソースから開いている PDF ファイルと通信する必要もありません。 PDF の閲覧は、危険にさらされた PDF を攻撃の拠点として計画されたいかなる攻撃からもセキュリティで保護されます。

- Application Guard。 Application Guard を使用すると、管理者は組織で信頼されるサイトの一覧を設定することが可能です。 ユーザーが他のいかなるサイトを開いた場合でも、Application Guard ウィンドウによって独自のコンテナーを実行し、分離して開かれます。 このコンテナーは、企業ネットワークとユーザーのコンピューター上のあらゆるデータが危険にさらされるのを防止するのに役立ちます。<br><br>
また、この保護は、表示されるあらゆるオンライン PDF ファイルにも適用されます。 さらに、Application Guard ウィンドウからダウンロードされたいかなる PDF ファイルも保存され、必要があれば、コンテナー内で再び開きます。 これにより、ファイルがダウンロードされた場合だけでなく、ライフサイクル全体を通した環境がセキュリティ保護されます。 詳細については、「[Application Guard](./microsoft-edge-security-windows-defender-application-guard.md)」 を参照してください。

### <a name="reliability"></a>信頼性

Microsoft Edge は Chromium ベースであるため、ユーザーは他の Chromium ベースのブラウザーの表示に使用されるのと同じレベルの信頼性を期待できます。

## <a name="deploy-and-update-pdf-reader"></a>PDF リーダーの展開と更新

PDF リーダーは、Microsoft Edge ブラウザーの残りの部分で展開および更新されます。 Microsoft Edge の展開の詳細については、 [[Microsoft Edge を数百から数千の デバイスに展開する]](microsoft-edge-video-deploy.md)ビデオをご覧ください。 展開の詳細については、[Microsoft Edge のドキュメント](./index.yml) ランディングページに掲載されています。

> [!TIP]
> 組織で Microsoft Edge を既定の PDF リーダーにすることができます。 これを行うためには、[次の手順を実行します](./edge-default-browser.md)。

## <a name="roadmap-and-feedback"></a>ロードマップとフィードバック

Microsoft Edge での PDF リーダーのロードマップについては、[こちら](https://techcommunity.microsoft.com/t5/articles/roadmap-for-pdf-reader-in-microsoft-edge/m-p/1467667)を参照してください。

Microsoft は、機能に関する皆様からのご意見をお待ちしております。 [Microsoft Edge Insider](https://techcommunity.microsoft.com/t5/microsoft-edge-insider/ct-p/MicrosoftEdgeInsider) フォーラムを通して、フィードバックをお送りください。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)
- [ビデオ: Microsoft Edge エンタープライズ グレードの PDF リーダー](microsoft-edge-video-pdf-reader.md)