---
title: ExtensionSettings ポリシーの詳細なガイド
ms.author: aspoddar
author: dan-wesley
manager: balajek
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: ExtensionSettings ポリシーを使用して Microsoft Edge 拡張機能を構成するための詳細なリファレンス ガイド。
ms.openlocfilehash: 3660910a252377efe8dff47dec8f811ecdd2018e
ms.sourcegitcommit: b67ebf9a68205407f5eaec343cb0722cfdd17396
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2021
ms.locfileid: "12061106"
---
# <a name="detailed-guide-to-the-extensionsettings-policy"></a>ExtensionSettings ポリシーの詳細なガイド

Microsoft Edge は、拡張機能を管理するための複数の方法を提供します。 一般的な方法は、[ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) ポリシーを使用して Windows グループ ポリシー エディターまたは Windows レジストリで JSON 文字列を使用して複数のポリシーを 1 か所に設定することです。

> [!NOTE]
> この記事は Microsoft Edge バージョン 77 以降に適用されます。

## <a name="before-you-begin"></a>始める前に

ここですべての拡張機能管理設定を設定するか、他のポリシーを通じてこれらのコントロールを設定するかを決定します。
  
ExtensionSettings ポリシーは、グループ ポリシー内の別の場所で設定した他のポリシー (以下のポリシーを含む) を上書きできます。

- [ExtensionAllowedTypes](/DeployEdge/microsoft-edge-policies#extensionallowedtypes)
- [ExtensionInstallBlocklist](/DeployEdge/microsoft-edge-policies#extensioninstallblocklist)
- [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)
- [ExtensionInstallSources](/DeployEdge/microsoft-edge-policies#extensioninstallsources)
- [ExtensionInstallAllowlist](/DeployEdge/microsoft-edge-policies#extensioninstallsources)

## <a name="extensionsettings-policy-fields"></a>ExtensionSettings ポリシー フィールド

このポリシーでは、更新 URL、拡張機能の初期インストールのダウンロード先、ブロックされたアクセス許可、実行が許可されていないアクセス許可などの設定を制御できます。 使用可能なポリシー フィールドについて、次の表で説明します。

| &nbsp; | 説明 |
|--|--|
| **allowed_types** | 既定の構成を構成する場合にのみ使用できます、*。 ユーザーが Microsoft Edge にインストールできるアプリまたは拡張機能の種類を指定します。 値は文字列のリストであり、各文字列は "extension"、"theme"、"user_script"、および "hosted_app" のいずれかの種類である必要があります。   |
| **blocked_install_message**| ユーザーによる特定の拡張機能のインストールをブロックする場合、ユーザーがそれらをインストールしようとしたときにブラウザーに表示するカスタム メッセージを指定できます。<br>Microsoft Edge アドオンの Web サイトに表示される一般的なエラー メッセージにテキストを追加します。 たとえば、IT 部門への連絡方法や、特定の拡張機能が利用できない理由をユーザーに伝えることができます。 メッセージの長さは最大 1,000 文字です。   |
|**blocked_permissions**  | 組織で許可されていない特定の API アクセス許可を要求する拡張機能をユーザーがインストールして実行できないようにします。 たとえば、Cookie にアクセスする拡張機能をブロックできます。 拡張機能がブロックしたアクセス許可を要求する場合、ユーザーはそれをインストールできません。 ユーザーが以前に拡張機能をインストールした場合、それはもう読み込めません。 拡張機能にオプション要件として、ブロックされたアクセス許可が含まれている場合、通常どおりインストールされます。 その後、拡張機能の実行中、ブロックされたアクセス許可は自動的に拒否されます。<br>使用可能なアクセス許可の一覧については、「[アクセス許可の宣言](/microsoft-edge/extensions-chromium/enterprise/declare-permissions)」を参照してください。   |
| **installation_mode**| 指定した拡張機能を Microsoft Edge に追加するかどうかとその方法を制御します。 インストール モードは、次のいずれかのオプションに設定できます。<br>- 許可: ユーザーは拡張機能をインストールできます。 インストール モードが定義されていない場合、この設定が既定値です。<br>- ブロック: ユーザーは拡張機能をインストールできません。<br>- force_installed: ユーザー操作なしで拡張機能を自動的にインストールします。 ユーザーはそれを削除できません。 また、update_url を使用して拡張機能のダウンロード場所を定義する必要があります。 **注**: Microsoft Edge は自動的にインストールする拡張機能を認識しないため、この設定を * と一緒に使用することはできません。<br>- normal_installed: ユーザー操作なしで拡張機能を自動的にインストールします。 ユーザーはそれを無効にすることができます。 また、update_url を使用して拡張機能のダウンロード場所を定義する必要があります。 **注**: Microsoft Edge は自動的にインストールする拡張機能を認識しないため、この設定を * と一緒に使用することはできません。<br>- 削除: ユーザーは拡張機能をインストールできません。 ユーザーが以前に拡張機能をインストールした場合、Microsoft Edge はそれを削除します。 |  |
| **install_sources** | 既定の構成を構成する場合にのみ使用できます、*。 拡張機能のインストールを許可する URL を指定します。 *.crx ファイルの場所と、ダウンロードが開始されるページ (参照元) の両方を、これらのパターンで許可する必要があります。 URL パターンの例については、[一致パターン](/microsoft-edge/extensions-chromium/enterprise/match-patterns)を参照してください。  |
| **minimum_version_required** |Microsoft Edge は、強制的にインストールされた拡張機能を含む、指定された最小バージョンより古いバージョンの拡張機能を無効にします。<br>バージョン文字列の形式は、拡張マニフェストで使用されているものと同じです。     |
| **update_url** | force_installed および normal_installed にのみ適用されます。 Microsoft Edge が拡張機能をダウンロードする場所を指定します。 拡張機能が Microsoft Edge アドオンの Web サイトでホストされている場合は、次の場所を使用します: `https://edge.microsoft.com/extensionwebstorebase/v1/crx`。<br>Microsoft Edge は、拡張機能の初期インストールに指定した URL を使用します。 以降の拡張機能の更新では、Microsoft Edge は拡張機能のマニフェストの URL を使用します。   |
| **runtime_allowed_hosts**| 拡張機能が runtime_blocked_hosts で定義されている場合でも、指定された Web サイトと対話できるようにします。 最大 100 個のエントリを指定できます。 余分なエントリは破棄されます。<br>ホスト パターンの形式は、パスを定義できないことを除いて、 [一致パターン](/microsoft-edge/extensions-chromium/enterprise/match-patterns) に似ています。 次に、例を示します。<br>- *://*.example.com<br>- *://example。*—eTLD ワイルドカードがサポートされています     |
| **runtime_blocked_hosts**| 拡張機能が、指定した Web サイトと対話したり、指定した Web サイトを変更したりすることを防ぎます。 変更には、JavaScript インジェクションのブロック、Cookie アクセス、および Web 要求の変更が含まれます。<br>最大 100 個のエントリを指定できます。 余分なエントリは破棄されます。<br>ホスト パターンの形式は、パスを定義できないことを除いて、一致パターンに似ています。 次に、例を示します。<br>- *://*.example.com<br>- *://example。*—eTLD ワイルドカードがサポートされています   |
| **override_update_url**| エッジ 93 から利用可能<br>これがに設定されている場合、Edge は、以降の拡張機能の更新のために、ExtensionSettings ポリシーまたは ExtensionInstallForcelist ポリシーで指定された更新 `true` URL を使用します。<br>これが設定されていないか、またはに設定されている場合、Edge は拡張機能のマニフェストで指定された `false` URL を更新に使用します。|
| **toolbar_state**| エッジ 94 から利用可能<br>このポリシー設定を使用すると、ツールバーにインストールされている拡張機能を強制的に表示できます。 既定の状態は `default_shown` 、すべての拡張機能です。 この設定では、次の状態が可能です<br>-`force_shown`: ツールバーにインストールされている拡張機能を強制的に表示するように選択できます。 ユーザーは、特定の拡張機能アイコンをツールバーから非表示にできます。<br>-`default_hidden`: この状態では、拡張機能はインストール時にツールバーから非表示になります。 必要に応じて、ユーザーはツールバーに表示できます。<br>-`default_shown`: これは、ブラウザーにインストールされているすべての拡張機能の聴覚障害者設定です。

グローバル スコープ (*)で許可されるキーは次のとおりです。 

- blocked_permissions
- installation_mode - このスコープの有効な値は、'blocked'、'allowed'、または 'removed' のみです。
- runtime_blocked_hosts
- blocked_install_message
- allowed_types
- runtime_allowed_hosts
- install_sources

これらは、個々の拡張スコープで許可されるキーです。 

- blocked_permissions
- minimum_version_required
- blocked_install_message
- toolbar_state (エッジ 94 から利用可能)
- installation_mode - `"blocked"` `"allowed"` `"removed"` `"force_installed"` 、、、 `"normal_installed"` 可能な値です。
- runtime_allowed_hosts
- update_url
- override_update_url
- runtime_blocked_hosts
- toolbar_state

更新 URL スコープで許可されるキーは次のとおりです。 

- blocked_permissions
- installation_mode - のみ `"blocked"` 、 `"allowed"` または `"removed"` 、このスコープ内の有効な値です。

## <a name="configure-using-a-json-string-in-windows-group-policy-editor"></a>Windows グループ ポリシー エディターで JSON 文字列を使用して構成する

GPO を使用して拡張機能設定ポリシーを使用する手順は、Microsoft Edge ポリシー用の ADM/ADMX が既にインポートされていることを前提としています。

1. グループ ポリシー エディターを開き、**[Microsoft Edge] > [拡張機能] > [拡張機能管理設定ポリシーの構成]** の順に移動します。
2. ポリシーを有効にし、そのコンパクトな JavaScript Object Notation (JSON) データを改行なしの 1 行としてテキスト ボックスに入力します。
3. ポリシーを検証して 1 行に圧縮するには、JSON 圧縮ツールを使用します。

### <a name="properly-format-json-for-the-extension-settings-policy"></a>拡張機能設定ポリシーの JSON を適切に書式設定する

このポリシーの 2 つの部分 (既定のスコープと個々のスコープ) を理解する必要があります。 既定のスコープは、独自のスコープを持たない拡張機能のキャッチオールです。 個々のスコープは、その拡張機能にのみ適用されます。  

既定のスコープはアスタリスク (*) で識別されます。 次の例では、既定のスコープと個々の拡張スコープを定義します。

```json
{ 
   “*”: {}, 
   “nckgahadagoaajjgafhacjanaoiihapd”: {} 
} 
```

拡張機能は、1 つのスコープからのみ設定を取得します。 その拡張機能に個々の拡張スコープがある場合、それらはその拡張機能に適用される設定になります。 個々の拡張スコープが存在しない場合、拡張機能は既定のスコープを使用します。  

次の JSON の例では、拡張機能が `.example.com` で実行されるのをブロックし、アクセス許可 "USB" を必要とする拡張機能をブロックします。

```json
{ 
  "*": { 
    "runtime_blocked_hosts": ["*://*.example.com"], 
    "blocked_permissions": ["usb"] 
  } 
} 
```

**コンパクト JSON**

```json
{"*":{"runtime_blocked_hosts":["*://*.example.com"],"blocked_permissions":["usb"]}} 
```

### <a name="a-few-more-json-examples-for-extension-settings"></a>拡張機能設定のいくつかの JSON の例

#### <a name="using-installation_mode-property-to-allow-and-block-extensions"></a>installation_mode プロパティを使用して、拡張機能を許可およびブロックする

- ユーザーはすべての拡張機能をインストールできます - これは既定の設定です 

  `{ "*": {"installation_mode": "allowed" }}`
- ユーザーは拡張機能をインストールできません。  

  `{ "*": {"installation_mode": "blocked" }}`

- インストールがブロックされたときに表示するカスタム メッセージを指定します。

   `{"*": {"blocked_install_message": ["Call IT(408 - 555 - 1234) for an exception"]}}`

#### <a name="using-installation_mode-property-to-force-install-extensions"></a>installation_mode プロパティを使用して、拡張機能を強制的にインストールする

installation_mode を "force_installed" として使用すると、拡張機能はユーザー操作なしで自動的にインストールされます。 ユーザーは拡張機能を無効にしたり削除したりすることはできません。 拡張機能が "normal" または "force" でインストールされている場合は、**update_url** フィールドも定義する必要があります。 このフィールドは、拡張機能をインストールできる場所を指します。 **update_url** フィールドには次の場所を使用します。

- ダウンロードする拡張機能が Microsoft Edge アドオン ストアでホストされている場合は、[https://edge.microsoft.com/extensionwebstorebase/v1/crx](https://edge.microsoft.com/extensionwebstorebase/v1/crx) を使用します。
- ダウンロードする拡張機能が Chrome Web ストアでホストされている場合は、[https://clients2.google.com/service/update2/crx](https://clients2.google.com/service/update2/crx) を使用します。
- 独自のサーバーで拡張機能をホストしている場合は、Microsoft Edge がパックされた拡張機能 (.crx ファイル) をダウンロードできる URL を使用します。 JSON の例:

   `{"nckgahadagoaajjgafhacjanaoiihapd": {"installation_mode": "force_installed","update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"}}`
  
上記の例では、"force_installed" の代わりに "normal_installed" を使用すると、拡張機能はユーザー操作なしで自動的にインストールされますが、拡張機能を無効にできます。  

   > [!TIP]
   > JSON 文字列を正しく書式設定するのは難しい場合があります。 ポリシーを実装する前に、JSON チェッカーを使用します。 または、[拡張機能設定ジェネレーター ツール](https://microsoft.github.io/edge-extension-settings-generator/minimal)の初期バージョンをお試しください

## <a name="configure-using-the-windows-registry"></a>Windows レジストリを使用して構成する

ExtensionSettings ポリシーは、次のキーでレジストリに書き込む必要があります。

`HKLM\Software\Policies\Microsoft\Edge\`

> [!NOTE]
> HKLM の代わりに HKCU を使用することは可能です。 同等のパスは、グループ ポリシー オブジェクト (GPO) で構成できます。  

Microsoft Edge の場合、すべての設定は次のキーで開始されます。

`HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\`

次に作成するキーは、個々のスコープの拡張子 ID または既定のスコープのアスタリスク (*) のいずれかです。 たとえば、Google ハングアウトに適用される設定には、次の場所を使用します。

`HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\ExtensionSettings\nckgahadagoaajjgafhacjanaoiihapd`

既定のスコープに適用される設定には、次の場所を使用します。

`HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\ExtensionSettings\*`

設定が異なると、文字列であるか文字列の配列であるかに応じて、異なる形式が必要になります。 配列の値には ["value"] が必要です。 文字列値は、この形式で入力できます。 次の一覧は、どの設定が配列または文字列であるかを示しています。

- Installation_mode = 文字列
- update_url = 文字列
- blocked_permissions = 文字列の配列
- allowed_permissions = 文字列の配列
- minimum_version_required = 文字列
- runtime_blocked_hosts = 文字列の配列
- runtime_allowed_hosts = 文字列の配列
- blocked_install_message = 文字列


## <a name="see-also"></a>関連項目

- [エンタープライズの Microsoft Edge 拡張機能を管理する](microsoft-edge-manage-extensions.md)
- [グループ ポリシーを使用して Microsoft Edge の拡張機能を管理する](microsoft-edge-manage-extensions-policies.md)
- [Microsoft Edge の拡張機能についてのよくある質問](microsoft-edge-manage-extensions-faq.md)
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
