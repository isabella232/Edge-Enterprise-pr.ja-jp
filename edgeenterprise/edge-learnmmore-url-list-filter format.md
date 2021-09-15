---
title: Microsoft Edge URL ポリシーのフィルター形式
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge の URLBlocklist ポリシーおよび URLAllowlist ポリシーで使用するフィルター形式について説明します。
ms.openlocfilehash: e178dad518ff4bee07bf89d9faca3231ee6cf246
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979590"
---
# <a name="filter-format-for-url-list-based-policies"></a>URL 一覧ベースのポリシーのフィルター形式

この記事では、Microsoft Edge の URL 一覧ベースのポリシー ([URLBlocklist](microsoft-edge-policies.md#urlblocklist)、[URLAllowList](microsoft-edge-policies.md#urlallowlist)、[CertificateTransparencyEnforcementDisabledForUrls](microsoft-edge-policies.md#certificatetransparencyenforcementdisabledforurls) などのポリシー) に使用するフィルター形式について説明します。

> [!NOTE]
> この記事は、Microsoft Edge version 77 以降に適用されます。

## <a name="the-filter-format"></a>フィルター形式

フィルター形式は次のとおりです。

```
    [scheme://][.]host[:port][/path][@query]
```

このフィルター形式には、以下のフィールドが含まれています。

| フィールド | 説明 |
| --- | --- |
| **scheme** (*オプション*) | http://、https://、ftp://、edge:// などを指定できます。 |
| **host** (*必須*) | 有効なホスト名である必要があります。ワイルドカード ("\*") を使用できます。 サブドメインの照合を無効にするには、**host** の前にオプションのドット (".") を含めます。 単一の IP アドレス リテラル ホスト名を指定できますが、IP アドレス リテラルホスト名に対してワイルドカードはサポートされていません。 |
| **port** (*オプション*) | 有効な値は 1 ～ 65535 です。 |
| **path** (*オプション*) | パスには任意の文字列を使用できます。 |
| **query** (*オプション*) | **query** には、キーと値またはキーのみのトークンをアンパサンド ("&") で区切って指定します。 キーと値のトークンは、等号 ("=") で区切ります。 プレフィックスの一致を指定するには、**query** の最後にアスタリスク ("\*") を使用できます。 |

## <a name="comparing-the-filter-format-to-the-url-format"></a>フィルター形式と URL 形式の比較

フィルター形式は URL 形式に似ていますが、次の点が異なります。

- "user:pass" を含めても無視されます (http://user:pass@ftp.contoso.com/pub/example.iso など)。
- フラグメント識別子 ("#") を含めた場合、この識別子と、それ以降の文字列はすべて無視されます。
- **host** としてワイルドカード ("*") を使用できます。また、プレフィックスとしてドット (".") を付けることができます。
- **host** のサフィックスとして、スラッシュ ("/") またはドット (".") を使用できます。 この場合、サフィックスは無視されます。

## <a name="filter-selection-criteria"></a>フィルター選択条件

URL 用に選択されるフィルターは、次のフィルター選択規則を処理した後に検出される、最も明確な一致です。

1. **host** の一致部分が最も長いフィルターが最初に選択されます。
2. 選択されたフィルターから、scheme または port が一致しないフィルターは破棄されます。
3. 残りのフィルターから、一致する **path** が最も長いフィルターが選択されます。
4. 残りのフィルターから、query トークンのセットが最も長いフィルターが選択されます。 この手順では、両方のフィルターで **path** の長さと **query** トーックンの数が同じであれば、許可一覧フィルターがブロック一覧フィルターより優先されます。
5. 有効なフィルターが残っていない場合は、**host** から最上位のサブドメインが削除され、選択プロセスが手順 1. から再び開始されます。 特殊なアスタリスク ("*") の **ホスト**が最後に検索され、すべてのホストに一致します。
6. フィルターが使用可能であれば、URL 要求がブロックまたは許可されます。

   >[!NOTE]
   >フィルターの一致がない場合、既定の動作では、URL 要求が許可されます。

## <a name="example-filter-selection-criteria"></a>フィルター選択条件の例

この例では、"https://sub.contoso.com/docs" との一致を検索するときに、フィルター選択で次の処理が行われます。

1. "sub.contoso.com" のフィルターを検索します。 フィルターが見つかった場合、検索の処理は手順 2. に進みます。 フィルターが見つからない場合は、"contoso.com"、"com"、最終的には "" を使用して検索が再試行されます。
2. 選択されたフィルターから、**scheme** に "http" が含まれていないものはすべて削除されます。
3. 残りのフィルターから、正確なポート番号が "80" ではないものはすべて削除されます。
4. 残りのフィルターから、**path** のプレフィックスが "/docs" でないものはすべて削除されます。
5. 残りのフィルターから、path のプレフィックスが最も長いフィルターが選択され、適用されます。 フィルターが見つからない場合は、選択プロセスが手順 1. から再び開始されます。 プロセスは、次のサブドメインで繰り返されます。

### <a name="additional-filter-information"></a>フィルターに関する追加情報

フィルターに、**host** のプレフィックスとしてドット (".") が含まれている場合は、**host** への正確な一致のみがフィルター選択されます。 次に、例を示します。

- "contoso.com" (ドットなし) は "contoso.com"、"www.contoso.com"、および "sub.www.contoso.com" と一致します。
- ".www.contoso.com" (ドットのプレフィックスあり) は、"www.contoso.com" にのみ一致します。

標準スキーマまたはカスタム **スキーマ**のいずれかを使用できます。 サポートされている標準スキーマは次のとおりです。

- _about_、_blob_、_content_、_edge_、_cid_、_data_、_file_、_filesystem_、_ftp_、_gopher_、_http_、_https_、_javascript_、_mailto_、_ws_、_wss_

その他の **schema** はカスタムの **schema** として処理されますが、許可されるパターンは _schema:*_ および _schema://*_ のみです。 次に、例を示します。

- "custom:\*" または "custom://\*" は "custom:app" と一致します
- "custom:app" と "custom://app" は無効です

**schema** と **host** では、大文字と小文字が区別されません。 次に、例を示します。

- フィルター "http://contoso.com" は、"HTTP://contoso.com"、"http://contoso.COM"、"http://contoso.com" に一致します。

**path** と **query** では、大文字と小文字が区別されます。 次に、例を示します。

- フィルター "http://contoso.com/path?query=A" は、"http://contoso.com/Path?query=A" または "http://contoso.com/path?Query=A" に一致しません。 "http://contoso.COM/path?query=A" には一致します。

## <a name="content-license"></a>コンテンツ ライセンス

> [!NOTE]
> このページの一部の情報は、Chromium.org によって作成および共有されている著作物に基づいており、[Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/) に記載されている条項に従って使用されています。 元の [Chromium のページはこちら](https://www.chromium.org/administrators/url-blacklist-filter-format)です。
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />この著作物は、<a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a> に従って使用許諾されています。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
