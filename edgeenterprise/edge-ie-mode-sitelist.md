---
title: エンタープライズ サイト構成戦略
ms.author: shisub
author: shisub
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Internet Explorer モード用にエンタープライズ モードのサイト リストを構成する方法をステップごとに説明しているガイドです。
ms.openlocfilehash: ec0d1364f3db00bc78e29bab8abbfcf1748f68494791fd5288a435a8b1230018
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "11724420"
---
# <a name="enterprise-site-configuration-strategy"></a>エンタープライズ サイト構成戦略

>[!Note]
> Internet Explorer 11 デスクトップ アプリケーションは廃止され、2022 年 6 月 15 日にサポートが終了します (スコープ内の一覧については、[FAQ を参照してください](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549))。 現在使用しているものと同じ IE11 アプリとサイトを、Internet Explorer モードの Microsoft Edge で開くことができます。 [こちらをご覧ください](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

この記事では、Microsoft Edge バージョン 77 以降の Internet Explorer モードをサポートするエンタープライズ モード サイト リストの変更について説明します。

エンタープライズ モード サイト リスト XML ファイルのスキーマについて詳しくは、[エンタープライズ モード スキーマ v.2 ガイダンス](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)」をご覧ください。

> [!NOTE]
> この記事は Microsoft Edge version 77 以降に適用されます。
<!--
## Updated schema elements

The following table describes the \<open-in app\> element added to the v.2 of the Enterprise Mode schema:

| **Element** | **Description** |
| --- | --- |
| \<open-in app="**true**"\> | A child element that controls what browser is used for sites. This element is required for sites that need to **open in IE11**.|

**Example:**

``` xml
<site url="contoso.com">

  <open-in app="true">IE11</open-in>

</site>
```

The following table shows the possible values of the \<open-in\> element:

| **Value** | **Description** |
| --- | --- |
| **\<open-in\>IE11\</open-in\>** | Opens the site in IE mode or a full IE11 window. To enable IE mode, see [Configure IE mode policies](./edge-ie-mode-policies.md)|
| **\<open-in app="**true**"\>IE11\</open-in\>** | Opens the site in a full IE11 window |
| **\<open-in\>MSEdge\</open-in\>** | Opens the site in Microsoft Edge |
| **\<open-in\>None or not specified\</open-in\>** | Opens the site in the default browser or in the browser where the user navigated to the site. |
|**\<open-in\>Configurable\</open-in\>** | Allows the site to participate in IE mode engine determination. To learn more, see [Learn about Configurable sites in IE mode](edge-learnmore-configurable-sites-ie-mode.md).  |

>[!NOTE]
> The attribute app=**"true"** is only recognized when associated to _'open-in' IE11_. Adding it to the other 'open-in' elements won't change browser behavior.   -->

## <a name="configuration-strategy"></a>構成戦略

次の手順は、IE モードのサイト構成戦略の一部です。
1. サイトの一覧を準備する
2. ニュートラル サイトを構成する
3. (省略可能) 必要に応じて Cookie の共有を使用する

<!--
Step 1.  – if you don’t have one use Site Discovery Step-by-Step
Step 2 – Neutral sites + sticky mode
        Use more examples and explain sticky mode better
Step 3 – If that doesn’t cover your needs, then use Cookie sharing -->

## <a name="prepare-your-site-list"></a>サイトの一覧を準備する

IE11 または Microsoft Edge 従来版のエンタープライズ モード サイトリストを既にお持ちの場合は、IE モードを構成するためにそれを再利用できます。

ただし、サイトの一覧をお持ちでない場合は、 「[エンタープライズ サイト発見ツール](/deployedge/edge-ie-mode-site-discovery)」を使用してリストを作成することができます。

## <a name="configure-neutral-sites"></a>ニュートラル サイトを構成する

IE モードを正しく動作させるには、認証サーバーまたはシングル サインオン (SSO) サーバーをニュートラル サイトとして明示的に構成する必要があります。 構成しないと、IE モードのページが Microsoft Edge にリダイレクトされ、認証に失敗します。

ニュートラル サイトは、ナビゲーションが開始されたブラウザーを使用します。これは Microsoft Edge または IE モードのいずれかです。 ニュートラル サイトを構成すると、これらの最新および従来の両方の認証サーバーを使用するすべてのアプリケーションが引き続き動作します。

Enterprise Mode Site List Manager ツールで [*開く*] ドロップダウンを [なし] に設定するか、サイト リスト XML を直接更新することによって、トラル サイトを構成できます。

``` xml
<site url="login.contoso.com">
   
    <open-in>None</open-in>

</site>
```

認証サーバーを識別するには、IE11 開発者ツールを使用して、アプリケーションからのネットワーク トラフィックを調べます。 認証サーバーを識別するために時間を割く時間が必要な場合は、ユーザーがワークフローを中断することなく継続できるよう、IE モードですべてのページ内ナビゲーションを維持するポリシーを構成し、ユーザーがワークフローを中断することなく続行できるようにすることができます。 不要な場合に IE モードの使用を最小限に抑えるには、認証サーバーを識別してサイト リストに追加したら、この設定を無効にします。 詳しくは、「[IE モードでページ内ナビゲーションを保持する](/deployedge/edge-learnmore-inpage-nav)」をご覧ください。

>[!NOTE]
   >IE モード統合では、エンタープライズ モード スキーマ v.1 がサポートされていません。 現在、Internet Explorer 11 でスキーマ v.1 を使用している場合は、スキーマ v.2 にアップグレードする必要があります。 詳しくは、「[エンタープライズ モード スキーマ v.2 ガイダンス](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)」をご覧ください。

## <a name="optional-use-cookie-sharing-if-necessary"></a>(省略可能) 必要に応じて Cookie の共有を使用する

既定では、Microsoft Edge や Internet Explorer のプロセスはセッション Cookie を共有しません。この共有の欠如は、IE モードの使用時に、場合によっては不便になってしまう可能性があります。 たとえば、ユーザーが以前に IE モードで再認証する必要がある場合、または Microsoft Edge セッションからサインアウトしても、重要なトランザクションのために Internet Explorer モード セッションからサイン アウトしない場合があります。 これらのシナリオでは、SSO によって設定された特定の Cookie が Microsoft Edge から Internet Explorer へと送信されるように構成することで、再認証の必要性を排除し、認証エクスペリエンスをよりシームレスにすることができます。 詳しくは、「[Microsoft Edge から Internet Explorer に Cookie を共有する](/deployedge/edge-ie-mode-add-guidance-cookieshare)」をご覧ください。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [IE モードの概要](./edge-ie-mode.md)
- [その他のエンタープライズ モード情報](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
