---
title: セルフホスト型 Microsoft Edge 拡張機能
ms.author: aspoddar
author: AndreaLBarr
manager: balajek
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: エンタープライズ内の拡張機能をパッケージ化し、Microsoft Edge をセルフホストする方法について説明します。
ms.openlocfilehash: 8b0e9ed346848f7ee9330c51f6a1c9274df89371
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979957"
---
# <a name="self-host-microsoft-edge-extensions"></a>セルフホスト型 Microsoft Edge 拡張機能

この記事では、独自の Web ストアでホストする拡張機能をパッケージ化する基本的なガイダンスを提供します。 また、組織内のデバイスとユーザーに拡張機能を展開する方法に関する手順も含まれています。

## <a name="prerequisites"></a>前提条件

独自の拡張機能をセルフホストするには、拡張機能とそのマニフェスト ファイルに独自の Web ホスティング サービスを提供する必要があります。

 次の手順では、ユーザーが既に拡張機能を作成し、XML ファイルの経験を持ち、グループ ポリシーの構成に関する知識を持ち、Windows レジストリの使い方を理解していることを前提としています。

## <a name="publish-an-extension"></a>拡張機能を発行する

拡張機能を発行する前に、CRX (Chrome 拡張機能) ファイルにパッキングする必要があります。 拡張子を CRX ファイルとしてパッキングするためのガイドとして、次の手順を使用します。

1. [Microsoft Edgeのアドレス ] バーで、*[edge://extensions] * に移動し、まだ有効になっていない場合は**開発者モード**を有効にします。 
2. **[インストールされている拡張機能] **で、**[ 拡張機能をパック]** をクリックして、 CRX ファイルを作成します。
3. **[拡張機能をパック]** ダイアログを使用して、拡張機能のソースを含むディレクトリを検索します。 ディレクトリを選択し、**[拡張機能をパック]** をクリックします。  これにより、PEM ファイルと共に CRX ファイルが作成されます。 PEM ファイルは、拡張機能のバージョン更新に必要なので保存します。 次のスクリーンショットは、拡張機能のルート ディレクトリを検索する **[拡張機能をパック]** ダイアログを示しています。

   :::image type="content" source="media/microsoft-edge-manage-extensions-webstore/manage-extensions-pack-dialog.png" alt-text="拡張機能のソース コードを検索する [拡張機能をパック] ダイアログ。":::

   > [!IMPORTANT]
   > PEM ファイルは拡張機能のキーであり、将来の更新に必要なので、安全な場所に保存します。

4. CRX ファイルを [拡張機能] ウィンドウにドラッグし、読み込まれることを確認します。
5. 拡張機能をテストし、ID フィールド (これは CRX ID) とバージョン番号をメモします。 この情報は後で必要になります。 次のスクリーンショットは、CRX ID を持つテスト拡張機能を示しています。

   :::image type="content" source="media/microsoft-edge-manage-extensions-webstore/manage-extensions-test-extension.png" alt-text="CRX ID を表示する拡張機能の例":::

6. CRX ファイルをホストにアップロードし、ダウンロード元の URL をメモします。 この情報は、XML マニフェスト ファイルに必要です。
7. アプリ/拡張機能 ID、ダウンロード URL、およびバージョンを使用してマニフェスト XML ファイルを作成するには、次のフィールドを定義します。  

   - **appid** - 手順 5 の内線番号 ID
   - **codebase** - 手順 6 からの CRX ファイルのダウンロード場所
   - **version** - 拡張機能のマニフェストで指定されたバージョンと一致する必要があるアプリ/拡張機能のバージョン。

   次のコード スニペットは、XML マニフェスト ファイルの例を示しています。

   ```xml
   <?xml version='1.0' encoding='UTF-8'?> 
   <gupdate xmlns='http://www.google.com/update2/response' protocol='2.0'> 
     <app appid='ekilpdeokbpjmminmhfcgkncmmohmfeb'> 
     <updatecheck codebase='https://app.somecompany.com/extensionfolder/helloworld.crx' version='1.0' /> 
     </app> 
   </gupdate> 
   ```

   詳細については、[「Microsoft Edge の拡張機能の自動更新 - Microsoft Edge の開発」](/microsoft-edge/extensions-chromium/enterprise/auto-update)を参照してください。

8. 完了済み XML ファイルを、ダウンロードした元の場所にアップロードして、その URL をメモします。 この URL は、グループ ポリシーを使用して拡張機能をインストールするときに必要です。 [「プライベート ホスト拡張機能の配布」](#distribute-a-privately-hosted-extension)を参照してください。

   > [!IMPORTANT]
   > 拡張機能のホスティング場所は認証を必要としません。 ユーザー デバイスを使用する場所にユーザー デバイスがアクセスできる必要があります。

## <a name="publish-updates-to-an-extension"></a>拡張機能への更新プログラムの発行

更新された拡張機能を変更してテストした後、公開できます。 更新プログラムを発行するためのガイドとして、次の手順を使用します。

1. 次の構文: `"version":"versionString"`を使用して、拡張機能のマニフェスト..JSON ファイルのバージョン番号を高い数値に変更します。 "version":"1.0" の場合は、"version":"1.1" または "1.0" より大きい数値に更新できます。
2. 前の手順でマニフェスト ファイルに格納した番号と一致する XML ファイル`<updatecheck>` の "version" を更新します。 次に、例を示します。<br>`<updatecheck codebase='https://app.somecompany.com/extensionfolder/helloworld.crx' version='1.1' />`
3. 新しい変更を含む CRX ファイルを作成します。 *[edge://extensions]* に移動して、**[開発者モード]** を有効にします。
4. **[拡張機能のパック]** をクリックし、拡張ソースのディレクトリに移動します。

   > [!IMPORTANT]
   > CRX ファイルが初めて作成されたときに、生成され保存されたのと同じ PEM ファイルを使用します。 同じ PEM ファイルを使用しない場合は、拡張機能のアプリ ID が変更され、更新プログラムは新しい拡張機能として扱われます。

5. CRX ファイルを [拡張機能] ウィンドウにドラッグ アンド ドロップし、読み込まれることを確認します。 この操作の後、拡張機能は無効になります。 有効にするには、拡張機能の CRX ID を ExtensionInstallAllowList ポリシーに追加します。 
6. 更新された拡張機能をテストします。
7. 古い CRX ファイルと XML ファイルを、更新された拡張子の新しいファイルに置き換えます。

拡張機能の変更は、次のポリシー同期サイクル中に取得されます。 拡張機能の更新の詳細については、[「URLのアップデート」](/microsoft-edge/extensions-chromium/enterprise/auto-update#update-url) および [「マニフェストのアップデート」](/microsoft-edge/extensions-chromium/enterprise/auto-update#updated-manifest)を参照してください。

## <a name="distribute-a-privately-hosted-extension"></a>プライベート ホスト拡張機能の配布

CRX ファイルがホストされている場所のリンクを共有し、ユーザーがブラウザーで URL を入力するとすぐに拡張機能がダウンロードおよびインストールされます。 ユーザーは、[edge://extensions] ページから拡張機能を有効にできます。 ユーザーが自己ホスト型拡張機能をインストールするには、拡張 CRX ID を [ExtensionInstallAllowList](/deployedge/microsoft-edge-policies#extensioninstallallowlist) ポリシーに追加し、CRX ファイルがホストされている場所の URL を [ExtensionInstallSources](/deployedge/microsoft-edge-policies#extensioninstallsources) ポリシーに追加する必要があります。

または、グループ ポリシー [ExtensionInstallForceList](/deployedge/microsoft-edge-manage-extensions-policies#force-install-an-extension) を使用して、ユーザーのデバイスに拡張機能を強制的にインストールすることもできます。

これらのポリシーは、選択したユーザー、デバイス、または両方に適用できます。 ポリシーの更新は即座に行うのではなく、ポリシー設定を有効にするには時間がかかることを覚えておいてください。

## <a name="see-also"></a>関連項目

- [エンタープライズの Microsoft Edge 拡張機能を管理する](microsoft-edge-manage-extensions.md)
- [グループ ポリシーを使用して Microsoft Edge の拡張機能を使用する](microsoft-edge-manage-extensions-policies.md)
- [ExtensionSettings ポリシーの詳細なガイド](microsoft-edge-manage-extensions-ref-guide.md)
- [Microsoft Edge の拡張機能についてのよくある質問](microsoft-edge-manage-extensions-faq.md)
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
