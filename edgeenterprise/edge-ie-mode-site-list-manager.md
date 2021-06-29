---
title: 'Microsoft Edge の Enterprise Site List Manager '
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 05/19/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 'Microsoft Edge で Enterprise Site List Manager を有効にして使用する '
ms.openlocfilehash: aa468888a05753fb5b033a8b99c2f6045f4e1b12
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617407"
---
# <a name="enterprise-site-list-manager-in-microsoft-edge"></a>Microsoft Edge の Enterprise Site List Manager

>[!Note]
> Internet Explorer 11 デスクトップ アプリケーションは廃止され、2022 年 6 月 15 日にサポートが終了します (スコープ内の一覧については、[FAQ を参照してください](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549))。 現在使用しているものと同じ IE11 アプリとサイトを、Internet Explorer モードの Microsoft Edge で開くことができます。 [こちらをご覧ください](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

この記事では、Microsoft Edge で Enterprise Site List Manager にアクセスして、Internet Explorer モード用の Enterprise Mode Site List を作成、編集、およびエクスポートする方法について説明します。

> [!NOTE]
> この記事は、Microsoft Edge バージョン 89 以降に適用されます。 

## <a name="overview"></a>概要

Enterprise Site List Manager は、[スタンドアロンの Enterprise Mode Site List Manager ツール](https://www.microsoft.com/download/details.aspx?id=49974)のブラウザー版で、組織のサイト リストを作成、編集、およびエクスポートできます。

機能が強化された Internet Explorer モード用のツールは、今後 Microsoft Edge の Enterprise Site List Manager で利用可能になる予定です。 スタンドアロン ツールは引き続きダウンロード センターから入手できますが、機能は更新されません。

## <a name="enabling-access-to-enterprise-site-list-manager"></a>Enterprise Site List Manager へのアクセスの有効化

[EnterpriseModeSiteListManagerAllowed](./microsoft-edge-policies.md#enterprisemodesitelistmanagerallowed) グループ ポリシーを使用して、ツールへのアクセスを構成できます。

有効にすると、左側のナビゲーション ウィンドウに Enterprise Site List Manager という名前のオプションが *edge://compat* に表示されます。 [無効] の場合、左側のナビゲーション ウィンドウにエンタープライズ サイト リスト マネージャーへのエントリ ポイントは表示されません。 これは既定の動作です。

## <a name="using-the-enterprise-site-list-manager"></a>Enterprise Site List Manager の使用

Enterprise Site List Manager ツールは、スキーマの v.2 バージョンを使用します。 Enterprise Site List Manager (スキーマ v.2) に v.1 バージョン スキーマをインポートすると、XML が v.2 バージョンのスキーマに保存されます。 「[エンタープライズ モード スキーマ v.2 ガイダンス](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)」を参照してください。

### <a name="add-single-sites-to-your-site-list"></a>サイト リストへの単一サイトの追加  

サイト リストに個々のサイトを追加するには、次の手順を実行します。

> [!NOTE]
> 特定の URL だけを追加できます。インターネット ゾーンやイントラネット ゾーンを追加することはできません。

1. Enterprise Site List Manager で、 **[サイトを追加する]** をクリックします。
2. 追加する Web サイトの URL を入力します (例: URL ボックスに  <domain>.com または  <domain>.com/<path>  を入力)。
3. **[開く]**  リストから、次のいずれかのオプションを選択します。

   - **IE11**。 IE11 アプリケーションでサイトを開きます。
   - **IE モード**。 Microsoft Edge が有効の場合は Internet Explorer モードで、有効でない場合は IE11 アプリでサイトを開きます。 「 [Microsoft Edge の Internet Explorer モード](./edge-ie-mode.md)」を参照してください。
   - **MSEdge**。 Microsoft Edge でサイトを開きます。
   - **設定可能**。 サイトが IE モード エンジンの決定に参加できるようにします。 「[IE モードで構成可能なサイト](./edge-learnmore-configurable-sites-ie-mode.md)」を参照してください。
   - **なし**。 ユーザーが選択したブラウザーで開きます。  

4.  **[互換モード]** で、次のいずれかのオプションを選択します。

   - **IE8Enterprise**。 IE8 エンタープライズ モードでサイトを読み込みます。
   - **IE7Enterprise**。 IE7 エンタープライズ モードでサイトを読み込みます。
   - **IE[x]**。 [x] はドキュメント モードの番号を示し、サイトは指定されたドキュメント モードで読み込まれます。
   - **既定のモード**。 ページの既定の互換モードを使ってサイトを読み込みます。

   ドメイン内のパスには、ドメイン自体とは別の互換モードが必要な場合があります。 たとえば、既定の IE11 ブラウザーではドメインに問題がないように見えても、パスに問題があるためエンタープライズ モードを使う必要がある場合などです。 以前にドメインを追加した場合、最初に選んだ互換性が保持されます。 ただし、ドメインが新しい場合、自動的に  **[IE8 エンタープライズ モード]**  が選ばれます。

   エンタープライズ モードはドキュメント モードより優先されるため、エンタープライズ モード サイト一覧に既に含まれているサイトはこの更新の影響を受けず、引き続き通常どおりエンタープライズ モードで読み込まれます。 ドキュメント モードの使用方法について詳しくは、「  [ドキュメント モードとエンタープライズ モード サイト一覧を使って Web 互換性の問題を修正する](/internet-explorer/ie11-deploy-guide/fix-compat-issues-with-doc-modes-and-enterprise-mode-site-list)」をご覧ください。

5. **[リダイレクトを許可する**] チェックボックスは、サーバ側リダイレクトの処理に適用されます。 このチェックボックスをオンにすると、[開く] タグで指定されたブラウザーでサーバ側リダイレクトが開きます。 詳細については、 [こちら](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance#updated-schema-attributes)を参照してください。
6. Web サイトに関するコメントを  **[コメント]** ボックスに入力します。 管理者は、このツールを使用している間のみコメントを表示でき、これらのコメントはサイト リストの xml に保持されます。
7.  **[追加]** をクリックして、サイトをサイト リストに追加します。

### <a name="export-site-list-to-xml"></a>XML にサイト一覧をエクスポートする

Enterprise Site List Manager でサイト一覧を作成すると、その内容をエンタープライズ モード (.EMIE) または XML ファイルにエクスポートできます。 

> [!NOTE]
> このファイルには、互換モードの選択を含むすべての URL が含まれているため、安全な場所に保存する必要があります。

サイト一覧をエクスポートするには、以下の手順を実行します。

1. Enterprise Site List Manager で、**[XML にエクスポート]** をクリックします。
2. **バージョン番号**と**ファイル名**を入力します。
3. **[エクスポート]** をクリックします。

ファイルは、ローカルにもネットワーク共有にも保存できます。 ただし、必ずレジストリ キーで指定された場所に展開する必要があります。 詳細については、「 [Internet Explorer モードをオンにして、サイト一覧を使用する](./edge-ie-mode-policies.md)」を参照してください。

### <a name="import-multiple-sites-to-your-site-list"></a>サイト一覧に複数のサイトをインポートする

.xml ファイルを作成したら、**[XML からインポート** を使用して、エディターにサイトを一括追加できます。

エディターのすべての内容を置き換える場合は、省略記号 (…) をクリックし、**[リストのクリア]** を選択します。 エディターをクリアしたら、次の手順でサイトをインポートします。

1. Enterprise Site List Manager で、**[XML からインポート**] をクリックします。 
2. **[ファイルの選択]** をクリックしてサイト一覧を選択し、含まれているサイトをツールに追加します。 追加するサイト一覧を選択し、 **[開く]** をクリックします。 インポートでサポートされる形式は、Enterprise Mode Site List の v.2 スキーマを含む .xml、.emie、または .txt です。 「[エンタープライズ モード スキーマ v.2 ガイダンス](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)」を参照してください。
3.  **[読み込み]**  をクリックして、エディターでファイル tp からサイトを追加します。

ファイルは、ローカルにもネットワーク共有にも保存できます。 ただし、必ずレジストリ キーで指定された場所に展開する必要があります。 詳細については、「 [Internet Explorer モードをオンにして、サイト一覧を使用する](./edge-ie-mode-policies.md)」を参照してください。

### <a name="edit-sites-in-your-site-list"></a>サイト一覧内のサイトを編集する

 Enterprise Site List Manager で既存のサイト エントリの属性を編集できます。 関連付けられたコメントを追加したり削除したりすることもできます。

1. Enterprise Site List Manager で省略記号 (…) をクリックし、編集する URL で **[サイトの編集]** を選択します。
2. URL 以外のサイト エントリの任意の属性を編集できます。 編集が終了したら、**[保存]** をクリックします。

   > [!NOTE]
   > サイト エントリを削除する場合は、手順 1 で **[サイトの削除]** を選択します。

3. **[XML にエクスポート]** をクリックし、更新されたファイルを保存します。

ファイルは、ローカルにもネットワーク共有にも保存できます。 ただし、必ずレジストリ キーで指定された場所に展開する必要があります。 詳細については、「 [Internet Explorer モードをオンにして、サイト一覧を使用する](./edge-ie-mode-policies.md)」を参照してください。

### <a name="preview-your-site-list-in-xml-format"></a>XML 形式でサイト一覧をプレビューする

エクスポートしてサイト一覧の場所に保存する前に、エディターでサイトを XML 形式でプレビューできます。 **[XML プレビュー]** をクリックして、新しいタブでファイルを開きます。

### <a name="search-in-the-enterprise-site-list-manager"></a>Enterprise Site List Manager で検索する

特定のサイトが既にサイト一覧に存在するかどうかは、検索して調べることができるため、もう一度追加する必要はありません。

検索するには、エディターの右上隅にある  **[URL でサイトをフィルター処理する**] 検索ボックスに URL の一部を入力します。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [IE モードの概要](./edge-ie-mode.md)
- [エンタープライズ モード スキーマ v.2 ガイダンス](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)
- [その他のエンタープライズ モード情報](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)