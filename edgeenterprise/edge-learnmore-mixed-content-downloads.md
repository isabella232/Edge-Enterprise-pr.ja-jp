---
title: Microsoft Edge と混在したコンテンツのダウンロード
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 04/30/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge と混在したコンテンツのダウンロード
ms.openlocfilehash: a81c44754865b2303320bfe87346c7f7533e6133
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617307"
---
# <a name="learn-about-microsoft-edge-and-mixed-content-downloads"></a>Microsoft Edge と混在したコンテンツのダウンロードについて説明します

この記事では、混在したコンテンツのダウンロードと Microsoft Edge によるその処理方法について説明します。

>[!NOTE]
>この記事は Microsoft Edge version 85 以降に適用されます。

## <a name="what-are-mixed-content-downloads"></a>混在したコンテンツのダウンロードとは?

セキュリティで保護された HTTPS 接続経由で読み込まれた HTML ページからダウンロードを開始するときに、以下のいずれかの条件が存在すると、混在したコンテンツのダウンロードになります。

- 1 つ以上のダウンロード場所のリダイレクトが、セキュリティで保護されていない HTTP 接続経由で読み込まれた。
- 最終的なダウンロード場所がセキュリティで保護されていない HTTP 接続経由で読み込まれた。

いずれの場合も、要求はセキュリティで保護された HTTPS を使用して行われましたが、最終的なダウンロード先に到達するまでに HTTP と HTTPS の両方が関係しているため、混在したコンテンツとなります。 この種のコンテンツの場合、最新のブラウザーには、アクセス元のページはセキュリティで保護されていてもこのダウンロードがセキュリティで保護されていない状態で転送される可能性があることを示す警告がユーザーに表示されます。

## <a name="download-warnings-and-user-options"></a>ダウンロードの警告とユーザー オプション

ダウンロードの警告によって、ダウンロードしているファイルがネットワーク上で悪意のある攻撃者に読み取られる可能性があることをユーザーは確認できます。 このように警告されることにより、ユーザーは十分な情報を得たうえでファイルをダウンロードするかどうかを決定できます。

Microsoft Edge では、混在したコンテンツのダウンロードはブロックされますが、ユーザーは必要に応じてこの設定をオーバーライドして、ファイルをダウンロードできます。 Microsoft Edge での混在したコンテンツの実行可能ファイルのダウンロードのブロックは Microsoft Edge バージョン 85 から開始される予定で、今後のリリースでは各種ファイルがブロックされることになります。

> [!NOTE]
> この機能の展開は、リリース スケジュールとユーザー フィードバックに基づいて変更されることがあります。

<!-- The schedule of the block for different filetypes is to be determined and may be impacted by usage data and user feedback. -->

ダウンロード シェルフの場合、次のスクリーンショットの例のように、ブロックの警告メッセージが表示されます。

 ![ダウンロード トレイの混在したコンテンツの警告](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-tray-warning.png)

[ダウンロード] ページでは、次のスクリーンショットのようなブロックに関する警告が表示されます。

 ![混在したコンテンツのオーバーライドに関するプロンプト](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-page-warning.png)

ユーザーがダウンロードの続行を選択すると、そのアクションを確認するためのプロンプトが表示されます。 この確認メッセージの例が次のスクリーンショットに示されています。

 ![Internet Explorer モードを選択する](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-override.png)

## <a name="supporting-policies"></a>サポート ポリシー

企業が特定の Web サイトから混在したコンテンツのブロックを除外する場合、[InsecureContentAllowedForUrls](./microsoft-edge-policies.md#insecurecontentallowedforurls) ポリシーを使用して行えます。

## <a name="content-license"></a>コンテンツ ライセンス

> [!NOTE]
> このページの一部の情報は、Chromium.org によって作成および共有されている著作物に基づいており、[Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/) に記載されている条項に従って使用されています。 元のページは[こちら](https://developers.google.com/web/fundamentals/security/prevent-mixed-content/what-is-mixed-content)です。
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />この著作物は、<a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a> に従って使用許諾されています。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)