---
title: Microsoft Edge から Internet Explorer への Cookie の共有
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 12/21/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 'Microsoft Edge から Internet Explorer へと Cookie を共有する方法 '
ms.openlocfilehash: ddd9d34b5e2b0ee49093734da82e4a4fa7aa6a69
ms.sourcegitcommit: 306582403d4272831bcac390154c7cc7041a9b7e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2020
ms.locfileid: "11238184"
---
# Microsoft Edge から Internet Explorer への Cookie の共有

この記事では、Internet Explorer モードの使用中に、Microsoft Edge プロセスから Internet Explorer プロセスへのセッション Cookie の共有を構成する方法について説明します。

> [!NOTE]
> この記事は Microsoft Edge version 87 以降に適用されます。

## 前提条件

- Windows 更新プログラム

  - Windows 10 バージョン 2004、Windows Server バージョン 2004 - KB4571744 以上
  - Windows 10 バージョン 1909、Windows Server バージョン 1909 – KB4566116 以上
  - Windows 10 バージョン 1903、Windows Server バージョン 1903 – KB4566116 以上
  - Windows 10 バージョン 1809、Windows Server バージョン 1809、および Windows Server 2019 - KB4571748 以降
  - Windows 10 バージョン 1803 – KB4577032 以降

- Microsoft Edge バージョン 87 以降
- エンタープライズ モード サイト一覧を使用して構成された [IE モード](https://aka.ms/iemodeonedge) 

## 概要

大規模な組織では、最新のブラウザー上で動作するアプリケーションを、ワークフローの一部としてシングル サインオン (SSO) を有効にした状態で Internet Explorer モードで開くように構成されている可能性のある別のアプリケーションにリンクさせることが一般的です。

既定では、Microsoft Edge や Internet Explorer のプロセスはセッション Cookie を共有しないため、場合によっては不便になってしまう可能性があります。 たとえば、Internet Explorer モードでユーザーの再認証が必要な場合や、Microsoft Edge のセッションからサインアウトしても、Internet Explorer モードのセッションからはサインアウトしない場合などです。 これらのシナリオでは、SSO によって設定された特定の Cookie が Microsoft Edge から Internet Explorer へと送信されるように構成することで、再認証の必要性を排除し、認証エクスペリエンスをよりシームレスにすることができます。

> [!NOTE]
> セッション Cookie は、Microsoft Edge から Internet Explorer にのみ共有することができます。 セッション Cookie を逆方向へ (Internet Explorer から Microsoft Edge へと) 共有することはできません。

## Cookie の共有のしくみ

エンタープライズ モード サイト一覧の XML が拡張され、Microsoft Edge のセッションから Internet Explorer と共有する必要のある Cookie を指定する要素が追加できるようになりました。  

Microsoft Edge のセッションで初めての Internet Explorer モードのタブが作成されると、一致するすべての Cookie が Internet Explorer のセッションへと共有されます。 その後は、ルールに一致する Cookie が追加、削除、修正されるたびに、Internet Explorer のセッションに対する更新として送信されます。 また、サイト一覧が更新されると、共有 Cookie のセットも再評価されます。

### 更新されたスキーマ要素

以下の表では、Cookie の共有機能をサポートするために追加された \<shared-cookie\> 要素について説明します。

| 要素| 説明 |
|-|-|
| \<shared-cookie **domain**=".contoso.com" **name**="cookie1"\>\</shared-cookie\><br><br>または<br><br>\<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2"\>\</shared-cookie\>   |**(必須)** \<shared-cookie\> 要素には、最低でも*ドメイン* (ドメイン Cookie の場合) または *host* (ホストオンリー Cookie の場合) 属性と *name* 属性が必要です。<br>これらは、Cookie のドメインと名前のそれぞれに完全に一致する必要があります。 **注** サブドメインは一致しません。<br><br>*domain* 属性はドメイン Cookie に使用されます (先頭のドットは許可されていますが、オプションです)。<br>*host* 属性はホストオンリー Cookie に使用されます (先頭のドットはエラーとなります)。 どちらも指定しない、または両方を指定する場合、エラーが発生します。<br>* Cookie 文字列にドメインが指定されている場合 (HTTP Set-Cookie 応答ヘッダーまたは document.cookie JS API 経由)、Cookie はドメイン Cookie となります。 ドメイン Cookie は、指定されたドメインとすべてのサブドメインに適用されます。 Cookie 文字列にドメインが指定されていない場合、Cookie はホストオンリー Cookie となり、設定されている特定のホストにのみ適用されます。 1 単語によるホスト名 (例: http://intranetsite)) や IP アドレス (例: http://10.0.0.1)) などの URL のいくつかのクラスについては、ホストオンリー Cookie の設定ができることにご注意ください。    |
| \<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2" **path**="/a/b/c"\>\</shared-cookie\>  | **(オプション)** *path* 属性は指定される場合があります。 path 属性が指定されていない場合 (または path 属性が空白の場合)、ドメイン/ホストと名前が一致する Cookie は、パスに関係なくポリシーに一致します (ワイルドカード ルール)。<br><br>パスが指定される場合は、完全一致である必要があります。<br>Cookie がパスが指定されているルールに一致する場合、パスが指定されていないルールよりも優先されます。 |

#### 共有の例

```xml
<site-list version="1">
<shared-cookie domain=".contoso.com" name="cookie1"></shared-cookie> 
<shared-cookie host="subdomain.contoso.com" name="cookie2" path="/a/b/c">
</shared-cookie>
</site-list>
```

## 関連項目

- [IE モードの概要](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [構成可能なサイトの情報](https://docs.microsoft.com/deployedge/edge-learnmore-configurable-sites-ie-mode)
- [その他のエンタープライズ モード情報](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
