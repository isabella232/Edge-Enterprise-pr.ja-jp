---
title: Internet Explorer 11 を無効にする
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 03/04/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge で Internet Explorer 11 を無効にし、Internet Explorer モードを使用する方法をご紹介します。
ms.openlocfilehash: be52f33b091977aff0ca29a4e10d4fc6ea4be957
ms.sourcegitcommit: f63a30c3e64e9e57fd76b6675ddff1fc2bbbeac8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393611"
---
# <a name="disable-internet-explorer-11"></a>Internet Explorer 11 を無効にする

この記事では、お使いの環境でスタンドアロン ブラウザー Internet Explorer 11 を無効にする方法について説明します。

## <a name="prerequisites"></a>前提条件

次の Windows 更新プログラムと Microsoft Edge ソフトウェアが必要です。

- Windows 更新プログラム

  - Windows 10 バージョン 2004、Windows Server バージョン 2004、Windows 10 バージョン 20H2: [KB4598291](https://support.microsoft.com/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b) 以降
  - Windows 10 バージョン 1909、Windows Server バージョン 1909: [KB4598298](https://support.microsoft.com/topic/january-21-2021-kb4598298-os-build-18363-1350-preview-02dfd9ba-91a2-1b82-dede-42f288c02511) 以降
  - Windows 10 バージョン 1809、Windows Server バージョン 1809、および Windows Server 2019: [KB4598296](https://support.microsoft.com/topic/january-21-2021-kb4598296-os-build-17763-1728-preview-4c0931ff-45b7-ff59-5e00-c03b5afb363d) 以降
  - Windows 10 バージョン 1607、Windows Server 2016: [KB4601318](https://support.microsoft.com/topic/february-9-2021-kb4601318-os-build-14393-4225-c5e3de6c-e3e6-ffb5-6197-48b9ce16446e) 以降
   - Windows 10 初期バージョン (2015 年 7 月): [KB4601331](https://support.microsoft.com/office/february-9-2021%e2%80%94kb4601331-os-build-10240-18842-6227d078-fef3-8d67-27e0-1882e6cb79ff?ui=en-US&rs=en-US&ad=US) 以降
  - Windows 8.1: [KB4601384](https://support.microsoft.com/topic/february-9-2021-kb4601384-monthly-rollup-16bdbb75-dd4b-2910-abc5-7891c9756b96) 以降
  - Windows Server 2012: [KB4601348](https://support.microsoft.com/topic/february-9-2021-kb4601348-monthly-rollup-2c338c0c-73d6-fb80-cc91-f1a86e80db0c) 以降
  
- Microsoft Edge 安定チャネル


## <a name="overview"></a>概要

従来の互換性のために Internet Explorer 11 (IE11) が必要な組織では、Microsoft Edge の Internet Explorer モード (IE モード) にシームレスで単一のブラウザー エクスペリエンスが用意されています。 ユーザーは、IE11 に切り替えなくても、Microsoft Edge 内から従来のアプリケーションにアクセスできます。

IE モードを構成した後、グループ ポリシーを使用して組織全体の **IE モード機能に影響を与えることなく**、スタンドアロン ブラウザーとして IE11 を無効にできます。

> [!NOTE]
> 特定のサイトにスタンドアロンの IE11 アプリが必要で、他のすべてのブラウザー トラフィックを Microsoft Edge にリダイレクトする場合は、[サイト リストに含まれていないすべてのサイトを Microsoft Edge に送信する](https://docs.microsoft.com/deployedge/edge-ie-mode-policies#redirect-sites-from-ie-to-microsoft-edge)ポリシーを構成して、サイトを IE から Microsoft Edge にリダイレクトできます。

## <a name="user-experience-after-redirecting-traffic-to-microsoft-edge"></a>Microsoft Edge にトラフィックをリダイレクトした後のユーザー エクスペリエンス

**[スタンドアロン ブラウザーとして Internet Explorer 11 を無効にする]** ポリシーを有効にした場合は、すべての IE11 アクティビティが Microsoft Edge にリダイレクトされ、ユーザーは次のエクスペリエンスを利用できます。

- スタート メニューの IE11 アイコンは削除されますが、タスク バー上の IE11 アイコンは残ります。
- ユーザーが IE11 を使用するショートカットまたはファイルの関連付けを起動しようとすると、Microsoft Edge で同じファイルまたはURL を開くようにリダイレクトされます。
- ユーザーが IExplore.exe バイナリを直接呼び出して IE11 を起動しようとすると、代わりに Microsoft Edge が起動します。

このエクスペリエンスのポリシー設定の一環として、オプションで IE11 を起動しようとするユーザーごとにダイレクト メッセージを表示できます。 このメッセージは、"常に" または "ユーザーごとに 1 回" を表示するように設定できます。 既定では、次のスクリーンショットに表示されるリダイレクト メッセージは表示されません。

:::image type="content" source="media/edge-ie-disable-ie11/disable-ie-redirect-msg.png" alt-text="Microsoft Edge へのリダイレクトがアクティブな場合は、IE を開こうとすると警告します。":::

エンタープライズ モード サイト一覧に IE11 アプリで開くよう構成されたアプリケーションが含まれている場合、このポリシーを使用して IE11 を無効にすると、Microsoft Edge の IE モードで開きます。
> [!NOTE]
> サイトが IE11 で開くように構成されていて、かつ IE11 を無効にするポリシーが構成されている場合、ユーザー フローに問題があることが知られています。 積極的に調査している問題。

## <a name="disable-internet-explorer-11-as-a-standalone-browser"></a>スタンドアロン ブラウザーとして Internet Explorer 11 を無効にする

グループ ポリシーを使用して Internet Explorer 11 を無効にするには、次の手順に従います。

1. 最新の  [Microsoft Edge ポリシー テンプレート](https://www.microsoft.com/edge/business/download)をダウンロードしてインストールします。
2. グループ ポリシー エディターを開きます。
3. ***[コンピューターの構成]、[管理用テンプレート]、[Windows コンポーネント/Internet Explorer] ***の順に移動します。 
4.  **[スタンドアロン ブラウザーとして Internet Explorer 11 を無効にする] **をダブルクリックします。
5.  **[有効化]** を選択します。
6.  **[オプション] **で、次のいずれかの値を選択します。

   - **[なし]**  IE11 が無効であることをユーザーに通知しない場合。
   - **[常に]**  IE11 からリダイレクトされるたびにユーザーに通知する場合。
   - **[ユーザーごとに 1 回]**  リダイレクトされた初回のみユーザーに通知する場合。

7.  **[OK]**  または  **[適用]**  をクリックして、このポリシー設定を保存します。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [IE モードの概要](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [その他のエンタープライズ モード情報](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
