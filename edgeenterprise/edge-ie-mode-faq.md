---
title: IE モードに関する FAQ
ms.author: cjacks
author: cjacks
manager: saudm
ms.date: 05/27/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: IE モードの Microsoft Edge に関する FAQ とトラブルシューティング
ms.openlocfilehash: fcceb9eab19d667f772c593fe4f362606c1623ff
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980407"
---
# IE モードに関する FAQ

この記事では、Microsoft Edge (バージョン 77 以降) に関するトラブルシューティングのヒントと FAQ を示します。

> [!NOTE]
> この記事は、Microsoft Edge version 77 (**Stable**、**Beta**、および **Dev** チャネル) 以降に適用されます。

## IE モードのトラブルシューティング

IE モードの問題を診断して解決するには、このセクションの情報を使用します。

### Internet Explorer モードの診断情報

Internet Explorer モードの診断情報は、[Microsoft Edge の互換性] タブに表示されます。このタブを開くには、*edge://compat/iediagnostic* に移動します。 このページには、診断メッセージが表示されることがあります。 このページでは、以下のカテゴリの構成情報も提供します。

- **レジストリ キーの確認**。 (確認が失敗した場合にのみ表示されます)。Internet Explorer 統合が、レジストリで正しく設定されていることを確認します。 設定されていない場合、ユーザーは **[修正]** をクリックして、この問題を解決します。
- **Internet Explorer モード**。 構成と OS に基づいて使用される API のバージョンを示します。 問題がある場合、ユーザーは **Windows Update** のインストールを求められることがあります。
- **Internet Explorer モードの設定**。 Internet Explorer モードが有効かどうか、およびその構成方法を示します。
- **コマンド ライン**。 Microsoft Edge を開始するために使用されるコマンド ライン文字列とスイッチを示します。
- **グループ ポリシー設定**。 グループ ポリシーを使用して IE モードが構成されているかどうか、および適用されているポリシーを示します。

### エラー メッセージ: 「このページを Internet Explorer モードで開くには、管理者特権で Microsoft Edge を再インストールしてください。」

必要な Windows Update がすべてインストールされていない場合、このエラーが表示されることがあります。 必要なバージョンの Windows および Microsoft Edge については、「[IE モードの概要](https://docs.microsoft.com/deployedge/edge-ie-mode)」に記載されている前提条件をご覧ください。

必要な Windows Update がすべて既にインストールされている場合、このエラーが表示されるのは以下の理由が考えられます。

- Canary チャネルを使用しています。これは、既定でユーザー レベルでインストールされます。
- Stable、Beta、Dev のいずれかのチャネルを使用しているが、昇格のインストール中に昇格のプロンプトがキャンセルされました。 昇格のプロンプトをキャンセルすると、ユーザー レベルでインストールは続行されます。
- Windows の機能で Internet Explorer 11 が無効になっています。

考えられる解決方法:

- 任意のチャネルのインストーラーをシステム レベルで実行します: `installer.exe --system-level`
- Windows の機能で Internet Explorer 11 を有効にします。

Microsoft Edge がシステム レベルでインストールされていることを確認するには、Microsoft Edge アドレス バーに「edge://version」と入力します。 [実行可能ファイルのパス] に、*C:\Program Files...* から始まるパスが表示されます。これは、システム インストールであることを示します。 [実行可能ファイルのパス] が *C:\Users\* から始まっている場合は、Microsoft Edge をアンインストールしてから、管理者特権で再インストールします。

### エラー メッセージ: 「このページを IE モードで開くには、Microsoft Edge を再起動してみてください。」

Internet Explorer で予期しないエラーが発生した場合、このエラーが表示されることがあります。 Microsoft Edge を再起動すると、通常はこのエラーが解決されます。

### エラー メッセージ: 「リモート デバッグを無効にして、IE モードでこのサイトを開きます。このようにしないと、サイトが正しく動作しない可能性があります。」

リモート デバッグ中に、IE モードで実行するように構成された Web ページに移動する場合、このエラーが表示されることがあります。 続行できますが、ページは Microsoft Edge を使用して表示されます。

## よく寄せられる質問

### IE モードは Internet Explorer 11 に代わる機能ですか?

Internet Explorer は、信頼できる安全なブラウザーとしてサポートされています。 Internet Explorer が Windows のコンポーネントであることに変わりはなく、サポートは、インストールされている OS のサポート ライフサイクルに従って行われます。 詳しくは、「[ライフサイクルに関する FAQ - Internet Explorer](https://support.microsoft.com/help/17454/)」をご覧ください。 Microsoft による Internet Explorer のサポートと更新は続行しますが、最新の機能更新プログラムとプラットフォーム更新プログラムは Microsoft Edge のみで利用可能になります。

### IE モードで SharePoint で [エクスプローラー​​で開く] または [エクスプローラーで表示] を使用できますか?

はい。スタンドアロン Internet Explorer 11 で動作する場合は、IE モードで動作します。 ただし、[エクスプローラー​​で開く] オプションを使用するのではなく、SharePoint 外部のファイルやフォルダを管理するための推奨アプローチは、[SharePoint ファイルの同期](https://support.office.com/en-us/article/sync-sharepoint-files-with-the-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)または [SharePoint でのファイルの移動またはコピー](https://support.office.com/en-us/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc)です。

### Microsoft Edge の IE モードでは、Internet Explorer 11 でサポートされている *nomerge* オプションをサポートしていますか?

Microsoft Edge には、*nomerge* オプションをミラーリングする明示的なコマンドはありませんが、この機能性を提供する、推奨される代替方法がいくつかあります。

1. Microsoft Edge のプロファイルを使用すると、各プロファイルが異なる IE セッションにマッピングされ、*nomerge* オプションと同様に動作します。
2. `--user-data-dir=<path>` のコマンド ラインを使用しますが、各セッションには異なるパスを使用します。 必要な場合は、Microsoft Edge の起動とセッション用パスの変更を両方実行するユーティリティを作成することが可能です。

上記のいずれのオプションもお客様のシナリオでうまくいかない場合は、Microsoft サポート、[TechCommunity フォーラム](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise)、[Microsoft Edge UserVoice](https://microsoftedge.uservoice.com/forums/928825-enterprise)のフィードバック チャネルのいずれかをご確認ください。

## 関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [IE モードの概要](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [その他のエンタープライズ モード情報](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)