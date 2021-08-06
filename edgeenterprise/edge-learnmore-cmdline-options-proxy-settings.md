---
title: Microsoft Edge のプロキシ設定
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 'コマンド ライン オプションを使用してプロキシ設定を構成する '
ms.openlocfilehash: d10002e5595836976a33a1b70743fe78b7987f00725546d3aae9c241d661c6eb
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "11724400"
---
# <a name="how-to-use-microsoft-edge-command-line-options-to-configure-proxy-settings"></a>Microsoft Edge コマンド ライン オプションを使用してプロキシ設定を構成する方法

この記事では、コマンド ライン オプションを使用して既定のシステム ネットワーク設定を上書きする方法について説明します。

>[!NOTE]
>この記事は、Microsoft Edge version 77 以降に適用されます。

## <a name="system-network-settings"></a>システム ネットワーク設定

Microsoft Edge ネットワーク スタックでは、既定でシステムのネットワーク設定が使用されます。 この設定には、*プロキシ設定*と、*証明書ストアと秘密キー ストア*が含まれます。

シナリオによっては、システムの既定プロキシ設定を使用する以外の手段がユーザーから要求される場合があります。 Microsoft Edge では、そのようなシナリオをサポートするために、カスタムプロキシ設定の構成に使用できるコマンド ライン オプションが用意されています。

これらのコマンド ライン オプションは、**プロキシ サーバー** グループの以下のポリシーに対応しています。

- [ProxyBypassList](./microsoft-edge-policies.md#proxybypasslist)
- [ProxyMode](./microsoft-edge-policies.md#proxymode)
- [ProxyPacUrl](./microsoft-edge-policies.md#proxypacurl)
- [ProxyServer](./microsoft-edge-policies.md#proxyserver)
- [ProxySettings](./microsoft-edge-policies.md#proxysettings)

## <a name="command-line-options-for-proxy-settings"></a>プロキシ設定用のコマンド ライン オプション

Microsoft Edge では、プロキシに関連する以下のコマンド ライン オプションがサポートされています。

 **`--no-proxy-server`**
 
システムでプロキシを使用するように別の手段で構成されていても、プロキシを使用しないように Microsoft Edge に指示します。 指定されている他のプロキシ設定よりも優先されます。

**`--proxy-auto-detect`**

プロキシ構成を試行して自動的に検出するように、Mircrosoft Edge に指示します。 `--proxy-server` が構成されていない場合、この引数は無視されます。

**`--proxy-server=<scheme>=<uri>[:<port>][;...] | <uri>[:<port>] | "direct://"`**

カスタムのプロキシ構成を使用するように Microsoft Edge に指示します。 カスタムのプロキシ構成は、次の 3 つの方法で指定できます。

1. URL/ポートのペアのリストをセミコロン区切りで指定します。 たとえば `--proxy-server="http=proxy1:8080;ftp=ftpproxy"` は、HTTP プロキシ "proxy1:8080" を http の URL に、HTTP プロキシ "ftpproxy:80" を ftp の URL に使用するよう Microsoft Edge に指示しています。
2. すべての URL に使用するために、オプションのポートを指定した単一の URL を指定します。 たとえば、`--proxy-server="proxy2:8080"` では、すべてのトラフィックに対して "proxy2:8080" のプロキシが使用されます。
3. 特殊な "direct://" 値を使用します。 たとえば `--proxy-server="direct://"` では、すべての接続でプロキシが使用されなくなります。 

>[!NOTE]
>プロキシの使用を試行し、プロキシを使用できない場合は直接接続にフォールバックするように Microsoft Edge を構成することもできます。 たとえば、`--proxy-server="http://proxy2:8080,direct://` と記述します。

**`--proxy-bypass-list=(<trailing_domain>|<ip-address>)[:<port>][;...]`**

指定されたセミコロン区切りのホスト一覧については、指定されたプロキシをバイパスするように Microsoft Edge に指示します。 このフラグは、`--proxy-server` と共に使用する必要があります。

>[!NOTE]
>末尾ドメイン照合では、区切り文字 "." が要求されず、"\*microsoft.com" に "imicrosoft.com" が一致します。 たとえば、`--proxy-server="proxy2:8080" --proxy-bypass-list="*.microsoft.com;*example.com;127.0.0.1:8080"` では、すべてのホストについて、ポート 8080 のプロキシ サーバー "proxy2" が使用されます。ただし、ポート 8080 の \*.microsoft.com、example.com、127.0.0.1 への要求は除外されます。 前の例で、imicrosoft.com への要求についてはプロキシが使用されます。 ただし、\*.example.com ではなく \*example.com が指定されているため、iexample.com への要求についてはプロキシがバイパスされます。

**`--proxy-pac-url=<pac-file-url>`**

指定された URL の PAC ファイルを使用するように Microsoft Edge に指示します。 たとえば `--proxy-pac-url="https://wpad/proxy.pac"` は、**proxy.pac** ファイルを使用して URL 要求のプロキシ情報を解決するように Microsoft Edge に指示します。

## <a name="content-license"></a>コンテンツ ライセンス

> [!NOTE]
> このページの一部の情報は、Chromium.org によって作成および共有されている著作物に基づいており、[Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/) に記載されている条項に従って使用されています。 元のページは[こちら](https://www.chromium.org/developers/design-documents/network-settings#TOC-Command-line-options-for-proxy-sett)です。
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />この著作物は、<a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a> に従って使用許諾されています。

## <a name="see-also"></a>関連項目

- 高度な構成設定とその他のオプションについては、Chromium Open Source プロジェクトの[プロキシに関するドキュメント](https://chromium.googlesource.com/chromium/src/+/HEAD/net/docs/proxy.md)をご覧ください。
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)