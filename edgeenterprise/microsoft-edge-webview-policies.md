---
title: Microsoft Edge WebView2 ポリシードキュメント
ms.author: stmoody
author: dan-wesley
manager: tahills
ms.date: 11/03/2020
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge ブラウザーでサポートされているすべてのポリシーに関する Windows と Mac のドキュメント
ms.openlocfilehash: ed7d87e14ba4439c6dbae57d647ed219ef567088
ms.sourcegitcommit: a5b13de18c5f9006c92a7c8deba1e1645601ad5c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "11155264"
---
# Microsoft Edge WebView2 - ポリシー

最新バージョンの Microsoft Edge WebView2には、次のポリシーが含まれています。 これらのポリシーを使用して、組織内での Microsoft Edge WebView2の動作方法を構成することができます。

Microsoft Edge WebView2の更新方法とタイミングを制御するために使用される追加のポリシー セットについては、「[Microsoft Edge更新ポリシーの参照](microsoft-edge-update-policies.md)」をご覧ください。


> [!NOTE]
> この記事は Microsoft Edge version 87 以降に適用されます。

## 使用可能なポリシー

次の表は、Microsoft Edge WebView2で使用可能な、このリリースのすべてのグループ ポリシーの一覧を示しています。 個々のポリシーに関する詳しい情報を取得するには、表内のリンクをお使いください。

|||
|-|-|
|[ローダーの上書き設定](#loader-override-settings)|

### [*ローダーの上書き設定*](#loader-override-settings-policies)

|ポリシー名|キャプション|
|-|-|
|[browserExecutableFolder](#browserexecutablefolder)|ブラウザーの実行可能フォルダーの場所を構成する|
|[releaseChannelPreference](#releasechannelpreference)|リリースチャネルの優先検索順序を設定する|




  ## ローダーの上書き設定ポリシー

  [ページのトップへ](#microsoft-edge-webview2---policies)

  ### browserExecutableFolder

  #### ブラウザーの実行可能フォルダーの場所を構成する

  
  
  #### サポートされているバージョン:

  - Windows での 87 以降

  #### 説明

  このポリシーでは、指定したパスの WebView2 ランタイムを使用するように WebView2 アプリケーションを構成します。 フォルダーには、msedgewebview2.exe、 msedge.dll などのファイルが含まれている必要があります。

フォルダーパスの値を設定するには、値の名前と値のペアを入力します。 アプリケーションユーザーモデル ID または実行可能ファイル名に値の名前を設定します。 すべてのアプリケーションに適用するには、""*" wildcardを値の名前として使用できます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: BrowserExecutableFolder
  - GP 名: ブラウザーの実行可能ファイルフォルダーの場所を構成する
  - GP path (必須): 管理用テンプレート/Microsoft Edge WebView2/ローダーの上書き設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdgeWebView2.admx

  ##### Windows レジストリの設定

  - Path (必須): SOFTWARE\Policies\Microsoft\Edge\WebView2\BrowserExecutableFolder
  - パス (推奨): なし
  - 値の名前: REG_SZ の一覧
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\WebView2\BrowserExecutableFolder = "Name: *, Value: C:\\Program Files\\Microsoft Edge WebView2 Runtime Redistributable 85.0.541.0 x64"

```

  

  [ページのトップへ](#microsoft-edge-webview2---policies)

  ### releaseChannelPreference

  #### リリースチャネルの優先検索順序を設定する

  
  
  #### サポートされているバージョン:

  - Windows での 87 以降

  #### 説明

  既定のチャネル検索順序は、WebView2 ランタイム、ベータ、開発、およびカナリアです。

既定の検索順序を反転するには、このポリシーを1に設定します。

リリースチャネルの基本設定の値を設定するには、値の名前と値のペアを入力します。 アプリケーションユーザーモデル ID または実行可能ファイル名に値の名前を設定します。 すべてのアプリケーションに適用するには、""*" wildcardを値の名前として使用できます。

  #### サポートされている機能:

  - 必須にすることができるか: はい
  - 推奨にすることができるか: いいえ
  - 動的なポリシーの更新: はい

  #### ［データの種類］:

  - 文字列のリスト

  #### Windows の情報と設定

  ##### グループ ポリシー (ADMX) 情報

  - GP 固有の名前: ReleaseChannelPreference
  - GP 名: リリースチャネルの優先検索順序を設定する
  - GP path (必須): 管理用テンプレート/Microsoft Edge WebView2/ローダーの上書き設定
  - GP パス (推奨): なし
  - GP ADMX ファイル名: MSEdgeWebView2.admx

  ##### Windows レジストリの設定

  - Path (必須): SOFTWARE\Policies\Microsoft\Edge\WebView2\ReleaseChannelPreference
  - パス (推奨): なし
  - 値の名前: REG_SZ の一覧
  - 値の種類: REG_SZ の一覧

  ##### サンプル値:

```
SOFTWARE\Policies\Microsoft\Edge\WebView2\ReleaseChannelPreference = "Name: *, Value: 1"

```

  

  [ページのトップへ](#microsoft-edge-webview2---policies)


## 関連項目

- [Microsoft Edge の構成](configure-microsoft-edge.md)
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Office セキュリティ ベースライン ブログ](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/bg-p/Microsoft-Security-Baselines)