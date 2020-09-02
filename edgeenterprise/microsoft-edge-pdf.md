---
title: Microsoft Edge の PDF リーダー
ms.author: adigan
author: dan-wesley
manager: balajek
ms.date: 08/05/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge の PDF リーダーについて説明します。
ms.openlocfilehash: c189bc08d4af0c9d5c4d9c573e0b5b7ef32a7fb3
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980523"
---
# Microsoft Edge の PDF リーダー

PDFファイルは、日常生活でかなり大きな割合を占めています。 これらは、契約書および合意書、ニュースレター、申込用紙、リサーチ記事、履歴書などのフォームに使用されます。 これらのファイルは、企業にとって高い信頼性、安全性、および性能を備えた PDF リーダーを採用する必要性を協調します。

Microsoft Edge には、組み込みの PDF リーダーが用意されています。このリーダーを使用すると、ローカル、オンライン、または Web ページに埋め込まれた PDF ファイルを開くことができます。 これらのファイルに注釈を付けて、インクや強調表示することができます。 この PDF リーダーでは、Web ページおよび PDF ドキュメントのニーズを満たす単一のアプリケーションが提供されます。 Microsoft Edge PDF リーダーは、Windows および macOS デスクトップ プラットフォームで動作する、安全で信頼性の高いアプリケーションです。

> [!NOTE]
> この記事は Microsoft Edge version 77 以降に適用されます。

## 前提条件、サポート、および制約

次の表は、Microsoft Edge で各 PDF リーダー機能をサポートするチャネルとバージョンを示しています。

| 機能 | Stable チャネル バージョン |
|---------|------------------------|
| ローカル、オンライン、および埋め込みの PDF ファイルを表示して印刷する | 79.0.309.71                |
| 基本フォームの入力<br>(JavaScript フォームはサポートされていません) | 79.0.309.71           |
| インク操作  | 80.0.361.48            |
| インク操作のカスタマイズ | 83.0.478.54  |
| Highlight  | 81.0.416.53         |
| 音声読み上げ | 現在、[Microsoft Edge Insider](https://www.microsoftedgeinsider.com/) チャネルで宣伝中 |
| MIP 保護ファイルの表示 | 80.0.361.48 の Windows サポート<br>81.0.416.53 の Mac のサポート |
|  IRM 保護ファイルの表示  | 83.0.478.37            |

### 制約

現在の PDF リーダーでは、次のような制約があります。

-  XML Forms Architecture (XFA) は、Microsoft Edge でサポートされていない旧式のフォームです。
-  現在サポートされていないアクセシビリティ シナリオに関連するドキュメントは、[Microsoft アクセシビリティ適合レポート](https://cloudblogs.microsoft.com/industry-blog/government/2018/09/11/accessibility-conformance-reports/) ブログに記載されています。

## 機能

### インク操作

PDF ファイルのインク操作を行うと、 PDF フォームに手軽に参照できるメモを取ったり、サインしたり、記入したりすることができます。 この機能は、Microsoft Edge で使用できるようになりました。 必要に応じた PDF ファイルのインク操作に加えて、PDF の別の部分に注目を集めるために色を使用したりストロークの幅を使用したりすることができます。 次のスクリーンショットは、ユーザーが PDF ページにインク操作を追加できるようにする方法を示しています。

<!-- SCREENSHOT -->
![PDF ページにインク操作を追加する](media/microsoft-edge-pdf/pdf-reader-inking.png)

### Highlight

Microsoft Edge の PDF リーダーには、強調表示の追加と編集のサポートが用意されています。 強調表示を作成するには、シンプルにテキストを選択し、それを右クリックしてメニューの [強調表示] を選び、目的の色を選びます。 次のスクリーンショットでは、使用できる強調表示オプションを示しています。

![PDF リーダーで強調表示オプションを使用する](media/microsoft-edge-pdf/pdf-reader-highlight.png)

### 音声読み上げ

PDF 用の音声読み上げを行うことで、ユーザーは、重要なタスクを実行しながら PDF コンテンツを聞くことができる便利な機能が追加されました。 また、聴覚障がいを持つ学習者がコンテンツを絞り込むことができるので、より学習に取り組みやすくなります。 次のスクリーンショットに、音声読み上げの例を示します。 強調表示されているのは、現在読み取り中のテキストです。

![PDF リーダーで強調表示オプションを使用する](media/microsoft-edge-pdf/pdf-reader-read-aloud-example.png)

### 保護された PDF

[Microsoft Information Protection (MIP)](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) により、ユーザーは組織のコンプライアンス ポリシーに準拠しながら、他のユーザーと安全に共同作業することが可能です。 ファイルが保護された後、ユーザーがアクセスできるアクションは、割り当てられているアクセス許可によって決まります。

これらのファイルは、他のソフトウェアをダウンロードしたり、アドインをインストールしたりすることなく、ブラウザーで直接開くことができます。 これにより、MIP が提供するセキュリティが直接ブラウザに統合され、シームレスなワークフローを実現します。

<!-- SCREENSHOT -->
![保護された PDF ドキュメント。](media/microsoft-edge-pdf/pdf-reader-protected-pdf2.png)

MIP で保護されたファイルに加えて、SharePoint ライブラリに保護された [Information Rights Management (IRM)](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center?view=o365-worldwide) 内の PDFファイルは、ブラウザーでネイティブに開くこともできます。

Microsoft Edge では、ユーザーはローカルまたはクラウドに保存されている MIP 保護ファイルを表示できます。 ローカルに保存した場合、ファイルをブラウザーで直接開くことができます。 クラウドサービスから SharePoint としてファイルを開いた場合、ユーザーは [ブラウザーで開く] オプションを使用することが必要になる場合があります。

ユーザーが Microsoft Edge にログインしているプロファイルに、少なくともファイルを表示するアクセス許可が与えられている場合、Microsoft Edge でファイルが開きます。

<!-- SCREENSHOT -->
![MIP によって保護されている SharePoint PDF ページを保存するかどうかを確認する](media/microsoft-edge-pdf/pdf-reader-sharepoint-irm.png)

## アクセシビリティ

PDF リーダーには、Windows および macOS デバイスでのキーボードのアクセシビリティ、ハイコントラスト モード、スクリーンリーダーのサポートが用意されています。

### キーボードのアクセシビリティ

ユーザーは、キーボードを使用して、フォームフィールドや強調表示などのユーザーが操作できるドキュメントの一部に移動できます。

<!-- SCREENSHOT -->

### ハイ コントラスト モード

PDF リーダーは、オペレーティング システム レベルで定義された設定を使用して、PDF コンテンツをハイ コントラスト モードで表示します。

<!-- SCREENSHOT -->
<!--![High contrast mode for pdf file](media/microsoft-edge-pdf/pdf-reader-high-contrast.png)-->

### スクリーン リーダーのサポート

ユーザーは、Windows および Mac コンピューターのスクリーン リーダーを使用して、PDF ファイル内を移動したり、読んだりすることができます。 <!--The next screenshot shows the toolbar that users can use for audio settings when they're using the Read Aloud option in PDF reader. -->

<!-- SCREENSHOT -->
<!--
![Screen reader toolbar](media/microsoft-edge-pdf/pdf-reader-read-aloud.png) -->

## セキュリティと信頼性

セキュリティは、あらゆる組織にとって最も重要な原則です。 PDF リーダーのセキュリティは、Microsoft Edge セキュリティの設計に必要不可欠です。 PDF リーダーの観点から最も重要なセキュリティ機能は2つあります。それは、プロセスの分離および Microsoft Defender Application Guard (Application Guard) です。

- プロセスの分離。 異なる Web サイトから開いた PDF は、プロセスが完全に分離されます。 ブラウザーは、いかなる Web サイトとも通信する必要はなく、別のソースから開いている PDF ファイルと通信する必要もありません。 PDF の閲覧は、危険にさらされた PDF を攻撃の拠点として計画されたいかなる攻撃からもセキュリティで保護されます。

- Application Guard。 Application Guard を使用すると、管理者は組織で信頼されるサイトの一覧を設定することが可能です。 ユーザーが他のいかなるサイトを開いた場合でも、Application Guard ウィンドウによって独自のコンテナーを実行し、分離して開かれます。 このコンテナーは、企業ネットワークとユーザーのコンピューター上のあらゆるデータが危険にさらされるのを防止するのに役立ちます。<br><br>
また、この保護は、表示されるあらゆるオンライン PDF ファイルにも適用されます。 さらに、Application Guard ウィンドウからダウンロードされたいかなる PDF ファイルも保存され、必要があれば、コンテナー内で再び開きます。 これにより、ファイルがダウンロードされた場合だけでなく、ライフサイクル全体を通した環境がセキュリティ保護されます。 詳細については、「[Application Guard](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-defender-application-guard)」 を参照してください。

### 信頼性

Microsoft Edge は Chrome がベースなので、ユーザーは Google Chrome の表示に使用されるのと同じレベルの信頼性を期待できます。

## PDF リーダーの展開と更新

PDF リーダーは、Microsoft Edge ブラウザーの残りの部分で展開および更新されます。 Microsoft Edge の展開の詳細については、 [[Microsoft Edge を数百から数千の デバイスに展開する]](microsoft-edge-video-deploy.md)ビデオをご覧ください。 展開の詳細については、[Microsoft Edge のドキュメント](https://docs.microsoft.com/DeployEdge/) ランディングページに掲載されています。

> [!TIP]
> 組織で Microsoft Edge を既定の PDF リーダーにすることができます。 これを行うためには、[次の手順を実行します](https://docs.microsoft.com/deployedge/edge-default-browser)。

## ロードマップとフィードバック

Microsoft Edge での PDF リーダーのロードマップは、[こちら](https://techcommunity.microsoft.com/t5/articles/roadmap-for-pdf-reader-in-microsoft-edge/m-p/1467667) で使用可能です。

お客様からのご意見をお待ちしております。 [Microsoft Edge UserVoice](https://microsoftedge.uservoice.com/) および [Microsoft Edge Insider](https://techcommunity.microsoft.com/t5/microsoft-edge-insider/ct-p/MicrosoftEdgeInsider) フォーラムを通して、フィードバックをお送りください。

## 関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)