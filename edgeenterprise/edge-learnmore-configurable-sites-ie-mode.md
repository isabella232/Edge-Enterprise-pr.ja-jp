---
title: Microsoft Edge と IE モードで構成可能なサイト
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 05/28/2020
audience: ITPro
ms.topic: procedural
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge と IE モードで構成可能なサイト
ms.openlocfilehash: a846d71d63a4f837041acc9b601f704999bb826a
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980498"
---
# IE モードで構成可能なサイトについて学ぶ

この記事では、Microsoft Edge で IE モードを使用する場合のエンタープライズモードサイトリストの構成可能サイト機能について説明します。

## 前提条件

- Windows 更新プログラム

  - Windows 10 バージョン 1909, Windows server バージョン 1909 – KB4550945 以降
  - Windows 10 バージョン 1903, Windows server バージョン 1903 – KB4550945 以降
  - Windows 10 version 1809, Windows Server version 1809, Windows Server 2019 - KB4550969 以降
  - Windows 10 version 1803 – KB4550944 以降
  - Windows 10 version 1607, Windows Server 2016 - KB4556826 以降
  - Windows 10 初期バージョン, July 2015 - KB4550947 以降
  - Windows 8.1 – KB4556798 以降

- Microsoft Edge version 83 以降
- エンタープライズモードサイトリストで構成された [IEモード](https://aka.ms/iemodeonedge)

## 概要

エンタープライズモードサイトリストで IE モードを必要とするサイトを構成すると、レガシーアプリケーションを使用するほとんどの環境で問題なく機能します。 ただし、このアプローチが、IEモードでドメイン全体をレンダリングせずに、IEモードで開くようにサイトのサブセットを構成するのに最適ではない場合があります。 例えば、ご自分の環境に単一のサーバーで実行されている最新のアプリケーションとレガシーアプリケーションの両方が含まれている場合や、IE モードでレガシーアプリケーションのみをレンダリングし、残りのアプリケーションを Microsoft Edge モードでレンダリングする柔軟性がご希望の場合です。

解決策は、[エンタープライズモードサイトリスト] の [構成可能なサイト] 機能を使用することです。 この機能が有効になっている場合、Microsoft Edge は、「構成可能」タグが付いたサイトがIEモードエンジンの決定に参加できるようにします。

## 構成可能なサイトの仕組み

### Microsoft Edge エンジンから IE モードエンジンへの自動切り替え

[構成可能なサイト] 機能を使用するには、エンタープライズオプションサイトリストで 1 つ以上のサイトが `<open-in>Configurable</open-in>` オプションを持っている必要があります。

例:

```
<site-list version="1">
  <site url="app.com">
    <open-in>Configurable</open-in>
  </site>
</site-list>
```

構成可能なサイト機能を有効にすると、次の動作が発生します。

1. 設定可能なサイトにリクエストを送信するとき、Microsoft Edge は HTTP 要求ヘッダー"`X-InternetExplorerModeConfigurable: 1`"を送信します。
2. 構成可能なサイトは、Microsoft Edge がサイトを IE モードでロードすることを要求するために、HTTP 応答ヘッダー "`X-InternetExplorerMode: 1`"を含むリダイレクト応答（HTTP 302 など）を送信する場合があります。
3. リダイレクトのターゲット（つまり、**ロケーション**応答ヘッダーの値）も**構成可能**サイトまたは**中立**サイトである必要があります。そうでない場合、IEモード応答ヘッダーは無視されます。 リダイレクトのターゲットは通常、元のURLと同じであると予想されます。 ただし、必ずしもそうである必要はありません。

   > [!NOTE]
   > リダイレクト応答は、リダイレクトに対する Microsoft Edge の通常の HTTP キャッシング動作に従ってキャッシングされる可能性があります。

### IE モードエンジンから Microsoft Edge エンジンに戻す

Microsoft Edge で構成可能なサイトを有効にすると、IE モードのタブで次の動作が自動的に有効になります。

1. 設定可能なサイトへのリクエストを行う場合、IE モードのタブは、Microsoft Edge のタブと同じように、HTTP 要求ヘッダー "`X-InternetExplorerModeConfigurable: 1`" を送信します。
2. 構成可能なサイトは、HTTP 応答ヘッダー "`X-InternetExplorerMode: 0`"を含むリダイレクト応答（HTTP 302など）を送信して、ナビゲーションが Microsoft Edge モードに戻るよう要求する場合があります。
3. リダイレクトのターゲット（つまり、**ロケーション**応答ヘッダーの値）も**構成可能**サイトまたは**中立**サイトである必要があります。そうでない場合、IEモード応答ヘッダーは無視されます。 リダイレクトのターゲットは通常、元のURLと同じであると予想されます。 ただし、必ずしもそうである必要はありません。

   > [!NOTE]
   > リダイレクト応答は、リダイレクトに対する Microsoft Edge の通常の HTTP キャッシング動作に従ってキャッシングされる可能性があります。

> [!TIP]
> どちらのブラウザーエンジンも、構成可能なサイトに同じ "`X-InternetExplorerModeConfigurable: 1`" 要求ヘッダーを送信します。 ユーザーエージェント要求ヘッダーを使用して、Microsoft Edge モードからのリクエストと IE モードからのリクエストを区別し、サイトがすでに正しいエンジンに読み込まれているときにリダイレクトされないようにする必要があります。

## 関連項目

- [IE モードの概要](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [その他のエンタープライズ モード情報](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)