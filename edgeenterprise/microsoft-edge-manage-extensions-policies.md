---
title: グループ ポリシーを使用して Microsoft Edge の拡張機能を管理する
ms.author: aspoddar
author: AndreaLBarr
manager: balajek
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: グループ ポリシーを使用して、エンタープライズの Microsoft Edge 拡張機能を管理する
ms.openlocfilehash: dad239a448ec1f0ebef60c7072bfaad5c3baed57
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641373"
---
# <a name="use-group-policies-to-manage-microsoft-edge-extensions"></a>グループ ポリシーを使用して Microsoft Edge の拡張機能を管理する

この記事では、グループ ポリシーを使用して拡張機能を管理するためのオプションと手順について説明します。 これらのオプションは、ユーザー向けに Microsoft Edge が既に管理されていることを前提としています。 ユーザー向けに管理する Microsoft Edge をまだ設定していない場合は、以下のリンクをたどって今すぐ設定してください。

- [エンタープライズの Microsoft Edge 拡張機能を管理する](/deployedge/microsoft-edge-manage-extensions)

> [!NOTE]
> この記事は Microsoft Edge バージョン 77 以降に適用されます。

## <a name="block-extensions-based-on-their-permissions"></a>アクセス許可に基づいて拡張機能をブロックする

[ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) ポリシーを使用して、アクセス許可に基づいてユーザーがインストールできる拡張機能を制御できます。 インストールされている拡張機能にブロックされているアクセス許可が必要な場合は、実行されません。 拡張機能は削除されず、無効になるだけです。

> [!NOTE]
> ブロックされたアクセス許可の設定は、拡張機能の設定ポリシー内でのみ設定できます。  

拡張機能をブロックするためのガイドとして、次の手順を使用します。

1. グループ ポリシー管理エディターを開き、**[管理用テンプレート] > [Microsoft Edge] > [拡張機能]** に移動し、**[拡張機能管理設定を構成する]** を選択します。
2. ポリシーを有効にし、圧縮される JSON 文字列を使用して、許可またはブロックするアクセス許可を入力します。 次のスクリーンショットは、アクセス許可 "usb" を使用する拡張機能をブロックする方法を示しています。

    :::image type="content" source="media/microsoft-edge-manage-extensions-policies/manage-extensions-gp-block-1.png" alt-text="拡張機能をブロックするようにグループ ポリシーを構成します。":::

次の例は、アクセス許可 "usb" とその圧縮文字列を使用する必要がある拡張機能をブロックする JSON を示しています。

### <a name="json-example"></a>JSON の例

   ```json
   { 
        "*": { 
             "blocked_permissions": ["usb"] 
        } 
   } 
   ```

   ```json
   {"*":{"blocked_permissions":["usb"]}} 
   ```

   > [!NOTE]
   > アクセス許可を使用するすべての拡張機能をブロックするには、前の例に示すように、拡張子 ID にアスタリスクを使用します。 1 つの拡張子 ID を指定すると、ポリシーはその拡張機能にのみ適用されます。 複数をブロックできますが、それらは別々のエントリである必要があります。

## <a name="prevent-extensions-from-altering-web-pages"></a>拡張機能による Web ページの変更を防止する

この設定により、拡張機能が機密性の高い Web サイトやドメインからデータを読み取ったり変更したりするのを防ぎます。 不要なアクションをブロックするには、Web サイトへのスクリプトの挿入、Cookie の読み取り、Web 要求の変更などのアクションをブロックします。 この設定は、ユーザーが拡張機能をインストールまたは削除するのを防ぐのではなく、拡張機能が指定された Web サイトを変更するのを防ぐだけです。 
  
> [!NOTE]
> [ランタイムが許可/ブロックされたホスト] 設定は、拡張機能の設定ポリシー内でのみ設定できます。  

ExtensionSettings ポリシーで、Web サイトまたはドメインの変更を防止 (または許可) するように、次の設定を構成できます。

- **Runtime_blocked_hosts**。 この設定は、拡張機能が変更を加えたり、指定した Web サイトからデータを読み取ったりするのをブロックします。
- **Runtime_allowed_hosts**。 この設定により、拡張機能は指定した Web サイトからデータの変更または読み取りを行うことができます。 ポリシーの JSON 文字列でサイトを指定するには、次の形式を使用します。

  ```json
  [http|https|ftp|*]://[subdomain|*].[hostname|*].[eTLD|*] [http|https|ftp|*],
  ```

  > [!NOTE]
  > `[hostname|*], and [eTLD|*]` セクションは必須ですが、`[subdomain|*]` セクションは省略可能です。

次の表に、有効なホスト パターンと一致するパターンの例を示します。

|有効なホスト パターン|一致する|一致しない|
|--|--|--|
|  `*://*.example.*` | `http://example.com`<br>`https://test.example.co.uk`   | `https://example.microsoft.com`<br>`http://example.microsoft.co.uk`  |
| `http://example.*` | `http://example.com`<br>`http://example.ly` | `https://example.com`<br>`http://test.example.com`   |
| `http://example.com`   | `http://example.com` | `https://example.com`<br>`http://test.example.co.uk` |
| `*://*`   | すべての URL  |   |

拡張機能による Web サイトまたはドメインへのアクセスをブロックまたは許可するガイドとして、次の手順を使用します。

1. グループ ポリシー管理エディターを開き、**[管理用テンプレート] > [Microsoft Edge] > [拡張機能]** に移動し、**[拡張機能管理設定を構成する]** を選択します。  
2. ポリシーを有効にしてから、許可またはブロックするアクセス許可を入力し、アクセス許可を単一の JSON 文字列に圧縮します。

次の例は、ホスト名の拡張機能をブロックする方法と、同じドメインの拡張機能をブロックする方法を示しています。

### <a name="json-example-to-block-hostname"></a>ホスト名をブロックする JSON の例

この例は、拡張機能が `www.microsoft.com` ホスト名にアクセスするのをブロックするための JSON と圧縮された JSON 文字列を示しています。

```json
{ 
    "*":{ 
            "runtime_blocked_hosts":["www.microsoft.com"] 
    } 
} 
```

```json
{"*":{"runtime_blocked_hosts":["www.microsoft.com"]}} 
```

> [!NOTE]
> すべての拡張機能の Web ページへのアクセスをブロックするには、前の例に示すように、拡張子 ID にアスタリスクを使用します。  アスタリスクの代わりに 1 つの拡張子 ID を指定した場合、ポリシーはその拡張機能にのみ適用されます。 複数の拡張機能をブロックできますが、それらは別々のエントリである必要があります。

### <a name="json-example-to-block-extensions-on-same-domain"></a>同じドメインの拡張機能をブロックする JSON の例

この例は、特定の拡張機能が同じドメイン "importantwebsite" で実行されるのをブロックするための JSON と圧縮された JSON 文字列を示しています。

```json
{ 
    "aapbdbdomjkkjkaonfhkkikfgjllcleb": { 
        "runtime_blocked_hosts": ["*://*.importantwebsite"] 
    }, 
    "bfbmjmiodbnnpllbbbfblcplfjjepjdn": { 
        "runtime_blocked_hosts": ["*://*.importantwebsite"] 
    } 
} 
```

```json
{"aapbdbdomjkkjkaonfhkkikfgjllcleb": {"runtime_blocked_hosts": ["*://,*.importantwebsite"]},"bfbmjmiodbnnpllbbbfblcplfjjepjdn": {"runtime_blocked_hosts": ["*://*.importantwebsite"]}} 
```

## <a name="allow-or-block-extensions-in-group-policy"></a>グループ ポリシーで拡張機能を許可またはブロックする

[ExtensionInstallBlocklist](/DeployEdge/microsoft-edge-policies#extensioninstallblocklist) ポリシーと [ExtensionInstallAllowlist](/DeployEdge/microsoft-edge-policies#extensioninstallallowlist) ポリシーを使用して、ブロックまたは許可する拡張機能を制御できます。 次の手順をガイドとして使用して、ブロックする拡張機能を除くすべての拡張機能を許可します。

1. グループ ポリシー管理エディターを開き、**[管理用テンプレート] > [Microsoft Edge] > [拡張機能]** に移動し、**[インストールできない拡張機能を制御する]** を選択します。
2. **[有効]** を選択します。
3. **[表示]** をクリックします。
4. ブロックする拡張機能のアプリ ID を入力します。 複数のアプリ ID を追加する場合は、ID ごとに個別の行を使用します。
5. すべての拡張機能をブロックするには、* _ をポリシーに入力して、拡張機能 *\** がインストールされるのを防ぐ。 これを "特定の拡張機能のインストールを許可する" ポリシーと組み合わせて使用すると、特定の拡張機能のインストールのみを許可できます。 次のスクリーンショットは、提供されたアプリ ID に基づいてブロックされる拡張機能を示しています。

   :::image type="content" source="media/microsoft-edge-manage-extensions-policies/manage-extensions-gp-block-2.png" alt-text="アプリ ID を使用して拡張機能をブロックします。":::

   > [!TIP]
   > 拡張機能のアプリ ID が見つからない場合は、Microsoft Edge アドオンの Web サイトで拡張機能を確認してください。 特定の拡張機能を見つけると、オムニボックスの URL の末尾にアプリ ID が表示されます。

> [!NOTE]
> ユーザーのコンピューターに既にインストールされているブロックリストに拡張機能を追加できます。 これにより、拡張機能が無効になり、ユーザーが再度有効にすることができなくなります。 アンインストールされず、無効になるだけです。

## <a name="force-install-an-extension"></a>拡張機能を強制的にインストールする

[ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist) ポリシーを使用して、ブロックまたは許可する拡張機能を制御します。 拡張機能を強制的にインストールするためのガイドとして、次の手順を使用します。

1. グループ ポリシー エディターで、[_*管理*用テンプレート]> Microsoft Edge > [ >*] に移動し、[サイレント モードでインストールされている拡張機能を制御する] を**選択します**。
2. **[有効]** を選択します。  
3. **[表示]** をクリックします。
4. 強制的にインストールする 1 つまたは複数の拡張機能のアプリ ID を入力します。  

拡張機能は、ユーザーの操作を必要とせずにサイレント インストールされます。 ユーザーは、拡張機能をアンインストールしたり無効にしたりすることはできません。 この設定は、有効になっているブロックリスト ポリシーを上書きします。

> [!NOTE]
> Chrome Web ストアでホストされている拡張機能の場合は、次のような文字列を使用します: `pckdojakecnhhplcgfflhndiffaohfah;https://clients2.google.com/service/update2/crx`。

## <a name="block-extensions-from-a-specific-store-or-update-url"></a>特定のストアまたは更新 URL からの拡張機能をブロックする

特定のストアまたは URL からの拡張機能をブロックするには、[ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) ポリシーを使用してそのストアの *update_url* をブロックするだけで済みます。

特定のストアまたは URL からの拡張機能をブロックするガイドとして、次の手順を使用します。

1. グループ ポリシー管理エディターを開き、**[管理用テンプレート] > [Microsoft Edge] > [拡張機能]** に移動し、**[拡張機能管理設定を構成する]** を選択します。  
2. ポリシーを有効にしてから、許可またはブロックするアクセス許可を入力し、単一の JSON 文字列に圧縮します。

次の例は、更新 URL (`https://clients2.google.com/service/update2/crx`) を使用して Chrome Web ストアからブロックする JSON と圧縮された JSON 文字列を示しています。

### <a name="json-example-for-blocking-on-update-url"></a>更新 URL でブロックするための JSON の例

```json
{ 
"update_url:https://clients2.google.com/service/update2/crx":{ 
                                                             " installation_mode":"blocked" 
                                                             } 
} 
```

```json
{"update_url:https://clients2.google.com/service/update2/crx":{"installation_mode":"blocked"}} 
```

> [!NOTE]
> 前の例で JSON を使用してストアがブロックされている場合でも、**ExtensionInstallForcelist** と **ExtensionInstallAllowlist** を使用して特定の拡張機能のインストールを許可または強制することができます。

## <a name="see-also"></a>関連項目

- [エンタープライズの Microsoft Edge 拡張機能を管理する](microsoft-edge-manage-extensions.md)
- [Microsoft Edge 拡張機能をホストする Web ストアを作成する](microsoft-edge-manage-extensions-webstore.md)
- [ExtensionSettings ポリシーのリファレンス ガイド](microsoft-edge-manage-extensions-ref-guide.md)
- [Microsoft Edge の拡張機能についてのよくある質問](microsoft-edge-manage-extensions-faq.md)
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
