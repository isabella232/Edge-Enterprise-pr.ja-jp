---
title: 'ポリシーによるサイトごとの構成 '
ms.author: collw
author: AndreaLBarr
manager: laurawi
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 'ポリシーによるサイトごとの構成 '
ms.openlocfilehash: 4f1bf9a421f0098ba8105e78f77ac4af62530239
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641693"
---
# <a name="persite-configuration-by-policy"></a>ポリシーによるサイトごとの構成

## <a name="introduction-browsers-as-decision-makers"></a>概要: 意思決定者としてのブラウザー

すべてのページ読み込みの一環として、ブラウザーは多くの決定をします — 特定の API を利用できるようにする必要がありますか? リソースの負荷を許可する必要がありますか? スクリプトの実行を許可する必要がありますか? リストは長いです。

ほとんどの場合、決定は、ユーザー設定と決定が行われたページの URL の 2 つの入力によって管理されます。

従来の Internet Explorer Web プラットフォームでは、これらの各決定は  [URLAction](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537178%28v%3dvs.85%29) と呼ばれ、インターネット コントロール パネル内の Enterprise グループ ポリシーとユーザー設定は、ブラウザーが各決定を処理する方法を制御しました。  

Microsoft Edge では、サイトごとのアクセス許可の大部分は、ワイルド カードのサポートが制限された単純な構文を使用して表現される設定とポリシーによって制御されます。 Windows セキュリティ ゾーンは、構成の決定の数が少ない場合にのみ使用されます。

## <a name="background-windows-security-zones"></a>背景: Windows セキュリティ ゾーン

ユーザーまたは管理者の構成を簡素化するために、従来のプラットフォームはサイトを 5 つの異なる **セキュリティ ゾーン** (ローカル コンピューター、ローカル イントラネット、信頼済み、インターネット、制限付きサイト) に分類しました。

決定を下す場合、ブラウザーは最初に Web サイトをゾーンにマップしてから、そのゾーンの URLAction の設定を参照して、実行する操作を決定します。 "イントラネットからの認証の課題を自動的に満たす" のような妥当な既定値は、ほとんどのユーザーが既定から設定を変更する必要がなかったことを意味します。

ユーザーは、インターネット コントロール パネルを使用して、特定のサイトをゾーンに割り当て、各ゾーンのアクセス許可の結果を構成できます。 管理環境では、管理者はグループ ポリシーを使用して、特定のサイトを ("サイトとゾーンの割り当て一覧" ポリシー経由で) ゾーンに割り当て、ゾーンごとに URLActions の設定を指定できます。 手動による管理またはユーザーによるゾーンへのサイトの割り当て以外に、追加のヒューリスティックが [サイトをローカル イントラネット ゾーンに割り当てる](/archive/blogs/ieinternals/the-intranet-zone)可能性があります。 特に、ドットレス ホスト名 (例: `http://payroll`) がイントラネット ゾーンに割り当て済みです。 プロキシ構成スクリプトが使用されている場合、プロキシをバイパスするように構成されたサイトはイントラネット ゾーンにマップされます。

Microsoft Edge 従来版は、いくつかの単純化された変更を加えて、Internet Explorer の前身からゾーン アーキテクチャを継承しました。

- Windows の 5 つの組み込みゾーンは、インターネット (インターネット)、信頼済み (イントラネット + 信頼済み)、およびローカル コンピューターの 3 つに統合されました。 制限付きサイト ゾーンは削除されました。

- ゾーンから URLAction へのマッピングはブラウザーにハードコードされ、インターネット コントロール パネルのグループ ポリシーと設定は無視されます。

## <a name="per-site-permissions-in-the-microsoft-edge"></a>Microsoft Edge でのサイトごとのアクセス許可

以前のものとは異なり、新しい Microsoft Edge では Windows セキュリティ ゾーンの使用が非常に制限されています。 代わりに、 [ポリシー](/deployedge/microsoft-edge-policies)を介して管理者にサイトごとの構成を提供するほとんどのアクセス許可と機能は、 [URL フィルター形式](/DeployEdge/edge-learnmmore-url-list-filter%20format)のルールの一覧に依存します。

エンド ユーザーが開くと <code>edge://settings/content/siteDetails?site=https://example.com</code>、さまざまなアクセス許可の構成スイッチとリストの長い一覧が表示されます。 ユーザーが [設定] ページを直接使用することはめったにありません。代わりに、 **[ページ情報]**  ドロップダウン (アドレス バーのロック アイコンをクリックすると表示されます) で、またはアドレス バーの右端にあるさまざまなプロンプトやボタンで、さまざまなウィジェットやトグルを使用して閲覧中に選択を行います。

企業は、グループ ポリシーを使用して、ブラウザーの動作を制御する個々のポリシーのサイト リストをプロビジョニングできます。 これらのポリシーを見つけるには、 [Microsoft Edge グループ ポリシーのドキュメント](/deployedge/microsoft-edge-policies) を開き、 **ForUrls**  を検索して、読み込まれたサイトの URL に基づいて動作を許可およびブロックするポリシーを検索します。 関連する設定のほとんどは、 [[コンテンツ設定のグループ ポリシー]](/deployedge/microsoft-edge-policies#content-settings) セクションに一覧表示されています。

特定の設定の既定の動作を制御するポリシー (名前に  **Default** が含まれる) も多数用意されています。

設定の多くは非常にあいまい (WebSerial、WebMIDI) であり、既定 (Images) から設定を変更する理由がないことがよくあります。

## <a name="common-questions"></a>一般的な質問

## <a name="q-can-the-url-filter-format-match-on-a-sites-ip-address"></a>Q: URL フィルター形式はサイトの IP アドレスと一致しますか?

いいえ、この形式では、許可リストとブロック リストの IP 範囲の指定はサポートされていません。 個々の IP  **リテラル**の指定はサポートされますが、そのようなルールは、ユーザーが上記のリテラル (例:  <http://127.0.0.1/>) を使用してサイトに移動した場合にのみ尊重されます。 ホスト名が使用されている場合 (<http://localhost>)、ホストの解決済み IP がフィルターにリストされた IP と一致していても、IP リテラル ルールは尊重されません。

## <a name="q-can-url-filters-matchjustdotless-host-names"></a>Q: URL フィルターはドットレス ホスト名と一致しますか?

いいえ、そうではありません。 必要なホスト名 (`https://payroll`、`https://stock`、`https://who` など) を個別にリストする必要があります。

ホスト名が次の形式になるようにイントラネットを構造化するのに十分な前向きな考えを持っていた場合:

- <div style="display: inline">`https://payroll.contoso-intranet.com`</div>

- <div style="display: inline">`https://timecard.contoso-intranet.com`</div>

- <div style="display: inline">`https://sharepoint.contoso-intranet.com`</div>

おめでとうございます。ベスト プラクティスを実装しました。 **_.contoso-intranet.com_* エントリを使用して各ポリシーを構成すると、   イントラネット全体がオプトインされます。

## <a name="use-of-security-zones-inthe-microsoft-edge"></a>Microsoft Edge でのセキュリティ ゾーンの使用

Microsoft Edge は主に URL フィルター形式を使用する個々のポリシーに依存しますが、これまでゾーン構成に依存してきた企業内での展開を簡素化するために、既定で Windows のセキュリティ ゾーンを少数の場所で引き続き使用します。 次の動作は、ゾーン ポリシーによって制御されます。

1. Windows 統合認証 (Kerberos/NTLM) 資格情報を自動的に解放するかどうかを決定する場合

2. ファイルのダウンロードを処理する方法を決定する場合

3. Internet Explorer モードの場合

## <a name="credential-release"></a>資格情報のリリース

既定では、Microsoft Edge は URLACTION_CREDENTIALS_USE を評価して Windows 統合認証が自動的に使用されるかどうかを判断するか、代わりにユーザーが手動認証プロンプトを表示する必要があります。 [AuthServerAllowlist サイト リスト ポリシー](/deployedge/microsoft-edge-policies#authserverallowlist)を構成すると、ゾーン ポリシーが参照されなくなります。

## <a name="file-downloads"></a>ファイルのダウンロード

ファイルのダウンロードの発生元に関する証拠 (いわゆる "[Web のマーク](https://textslashplain.com/2016/04/04/downloads-and-the-mark-of-the-web/)") は、インターネット ゾーンからダウンロードされたファイルに記録されます。 他のアプリケーション (Windows シェル、Microsoft Office など) は、ファイルの処理方法を決定する際に、この発生元の証拠を考慮に入れる場合があります。

Windows セキュリティ ゾーン ポリシーが [アプリケーションの起動と安全でないファイルの起動] 設定を無効にするように構成されている場合、Microsoft Edge ダウンロード マネージャーは、そのゾーン内のサイトからのファイルのダウンロードをブロックします。"ダウンロードできませんでした - ブロックされました" というメモが付きます。  

## <a name="ie-mode"></a>IE モード

IE モードは、 [すべてのイントラネット サイトを IE モードで開く](/deployedge/edge-ie-mode#configure-all-intranet-sites)ように構成できます。 この構成では、Edge は IE モードで開くかどうかを決定するときに URL のゾーンを評価します。 この最初の決定を超えて、IE モード タブは実際に Internet Explorer を実行しており、その結果、Internet Explorer 自体が行ったように、すべてのポリシー決定のゾーン設定を評価します。

## <a name="summary"></a>要約

ほとんどの場合、Microsoft Edge の設定は既定値のままにしておくことができます。 すべてのサイトまたは特定のサイトの既定値を変更する管理者は、適切なグループ ポリシーを使用してサイト一覧または既定の動作を指定できます。 いくつかのケース (資格情報の解放、ファイルのダウンロード、IE モード) では、管理者は Windows セキュリティ ゾーンの設定を構成することで引き続き動作を制御します。
