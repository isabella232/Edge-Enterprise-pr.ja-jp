---
title: エンタープライズ モード サイト リストでのサイトの構成
ms.author: cjacks
author: cjacks
manager: saudm
ms.date: 05/28/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: エンタープライズ サイト リストの構成
ms.openlocfilehash: 9b1943e4d50dcc770b4a634b99ecbd001d1ffbcc
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447651"
---
# <a name="configure-sites-on-the-enterprise-mode-site-list"></a>エンタープライズ モード サイト リストでのサイトの構成

この記事では、Microsoft Edge バージョン 77 以降の IE モードの構成をサポートするエンタープライズ モード サイト リストの変更について説明します。

エンタープライズ モード サイト リスト XML ファイルのスキーマについて詳しくは、[エンタープライズ モード スキーマ v.2 ガイダンス](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)」をご覧ください。

> [!NOTE]
> この記事は、Microsoft Edge version 77 (**Stable**、**Beta**、および **Dev** チャネル) 以降に適用されます。

## <a name="updated-schema-elements"></a>更新されたスキーマ要素

次の表は、エンタープライズ モード スキーマ v.2 に追加された \<open-in app\> 要素を示しています。

| **要素** | **説明** |
| --- | --- |
| \<open-in app="**true**"\> | サイトに使われるブラウザーの種類を制御する子要素。 **IE11 で開く**必要があるサイトには、この要素が必要です。|

**例:**

``` xml
<site url="contoso.com">

  <open-in app="true">IE11</open-in>

</site>
```

次の表は、\<open-in\> 要素の有効値を示しています。

| **値** | **説明** |
| --- | --- |
| **\<open-in\>IE11\</open-in\>** | IE モードまたはフル IE11 ウィンドウでサイトを開きます。 IE モードを有効にするには、「[IE モード ポリシーの構成](./edge-ie-mode-policies.md)」を参照してください|
| **\<open-in app="**true**"\>IE11\</open-in\>** | フル IE11 ウィンドウでサイトを開きます |
| **\<open-in\>MSEdge\</open-in\>** | Microsoft Edge でサイトを開きます |
| **\<open-in\>none または未指定\</open-in\>** | 既定のブラウザー、またはサイトに移動したブラウザーでサイトを開きます。 |
|**\<open-in\>構成可能\</open-in\>** | サイトが IE モード エンジンの決定に参加できるようにします。 詳細については、「[IE モードで構成可能なサイトの詳細](edge-learnmore-configurable-sites-ie-mode.md)」を参照してください。  |

>[!NOTE]
> 属性 app=**"true"** が認識されるのは、_'open-in' IE11_ に関連付けられている場合のみです。 他の 'open-in' 要素に追加しても、ブラウザーの動作は変わりません。   

## <a name="configure-neutral-sites"></a>ニュートラル サイトを構成する

IE モードを正しく動作させるには、認証サーバーまたはシングル サインオン サーバーをニュートラル サイトとして明示的に構成する必要があります。 構成しないと、IE モードのページが Microsoft Edge にリダイレクトされ、認証に失敗します。

ニュートラル サイトは、ナビゲーションが開始されたブラウザーを使用します。これは Microsoft Edge または IE モードのいずれかです。 ニュートラル サイトを構成すると、これらの最新および従来の両方の認証サーバーを使用するすべてのアプリケーションが引き続き動作します。

Enterprise Mode Site List Manager ツールで [*開く*] ドロップダウンを [なし] に設定するか、サイト リスト XML を直接更新することによって、トラル サイトを構成できます。

``` xml
<site url="login.contoso.com">
   
    <open-in>None</open-in>

</site>
```

認証サーバーを識別するには、IE11 開発者ツールを使用して、アプリケーションからのネットワーク トラフィックを調べます。 認証サーバーの識別にさらに時間が必要な場合は、ページ内ナビゲーションがすべて IE モードのままになるようにポリシーを構成できます。 IE モードの使用を最小限に抑えるには、認証サーバーを識別してサイト リストに追加したら、この設定を無効にします。 詳細については、[ページ内ナビゲーションがすべて IE モードのままになるように構成する方法](./microsoft-edge-policies.md#internetexplorerintegrationsiteredirect)に関する記事をご覧ください。

>[!NOTE]
   >IE モード統合では、エンタープライズ モード スキーマ v.1 がサポートされていません。 現在、Internet Explorer 11 でスキーマ v.1 を使用している場合は、スキーマ v.2 にアップグレードする必要があります。 詳しくは、「[エンタープライズ モード スキーマ v.2 ガイダンス](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)」をご覧ください。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [IE モードの概要](./edge-ie-mode.md)
- [その他のエンタープライズ モード情報](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)