---
title: Microsoft Edge Update のポリシーに関するドキュメント
ms.author: stmoody
author: dan-wesley
manager: tahills
ms.date: 11/12/2020
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge アップデーターでサポートされているすべてのポリシーに関するドキュメント
ms.openlocfilehash: 0cdcda984efff8d10a84431e44c49ffbf28ddf07
ms.sourcegitcommit: c2ac4f889b625210b9365a60a447482fb5b4c9d4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2020
ms.locfileid: "11167309"
---
# Microsoft Edge - 更新ポリシー

最新バージョンの Microsoft Edge には、Microsoft Edge をいつどのように更新するかを制御するために使用できる以下のポリシーが含まれています。

Microsoft Edge で使用できるその他のポリシーについて詳しくは、[Microsoft Edge ブラウザー ポリシー リファレンス](microsoft-edge-policies.md)をご覧ください。
> [!NOTE]
> この記事は、Microsoft Edge version 77 以降に適用されます。
##  <a name="available-policies"></a>使用可能なポリシー
次の表は、このリリースの Microsoft Edge で使用可能な、更新関連のすべてのグループ ポリシーの一覧を示しています。 個々のポリシーに関する詳しい情報を取得するには、表内のリンクをお使いください。

|||
|-|-|
|[アプリケーション](#applications)|[基本設定](#preferences)|
|[プロキシ サーバー](#proxy-server)|[Microsoft Edge WebView](#microsoft-edge-webview)|

### [アプリケーション](#applications-policies)
|ポリシー名|キャプション|
|-|-|
|[InstallDefault](#installdefault)|インストールの既定の動作を許可する|
|[UpdateDefault](#updatedefault)|更新ポリシーのオーバーライドの既定値|
|[Install](#install)|インストールを許可する (チャネルごと)|
|[Update](#update)|更新ポリシーのオーバーライド (チャネルごと)|
|[Allowsxs](#allowsxs)|Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する|
|[CreateDesktopShortcutDefault](#createdesktopshortcutdefault)|既定値のインストール時にデスクトップへのショートカットの作成を禁止する|
|[CreateDesktopShortcut](#createdesktopshortcut)|インストール時にデスクトップへのショートカットの作成を禁止する (チャネル単位)|
|[RollbackToTargetVersion](#rollbacktotargetversion)|ターゲットバージョンにロールバック (チャネル単位)|
|[TargetVersionPrefix](#targetversionprefix)|ターゲットバージョンの上書き (チャネルごと) |

### [基本設定](#preferences-policies)
|ポリシー名|キャプション|
|-|-|
|[AutoUpdateCheckPeriodMinutes](#autoupdatecheckperiodminutes)|自動更新チェック期間のオーバーライド|
|[UpdatesSuppressed](#updatessuppressed)|自動更新チェックを停止する 1 日あたりの時間帯|

### [プロキシ サーバー](#proxy-server-policies)
|ポリシー名|キャプション|
|-|-|
|[ProxyMode](#proxymode)|プロキシ サーバーの設定をどのように指定するかを選択する|
|[ProxyPacUrl](#proxypacurl)|プロキシ .pac ファイルへの URL|
|[ProxyServer](#proxyserver)|プロキシ サーバーのアドレスまたは URL|

### [Microsoft Edge WebView](#microsoft-edge-webview-policies)
|ポリシー名|キャプション|
|-|-|
|[Install](#install-webview)|インストールを許可する|
|[更新](#update-webview)|更新ポリシーのオーバーライド|

##  <a name="applications-policies"></a>アプリケーションに関するポリシー

[ページのトップへ](#microsoft-edge---update-policies)
###  <a name="installdefault"></a>InstallDefault
#### インストールの既定の動作を許可する
>Microsoft Edge Update 1.2.145.5 以降

#### 説明
すべてのチャネルに既定の動作を指定して、ドメインに参加しているデバイスで Microsoft Edge を許可またはブロックすることができます。

特定のチャネルの['インストールを許可する'](#install)ポリシーを有効にすることで、チャネルごとにポリシーを上書きできます。

このポリシーを無効にすると、Microsoft Edge のインストールがブロックされます。 これは、[[インストールの許可](#install)] ポリシーが未構成に設定されている場合は、Microsoft Edge ソフトウェアのインストールにのみ影響します。

このポリシーによって、Microsoft Edge Update の実行は禁止されません。また、ユーザーが Microsoft Edge ソフトウェアを他の方法を使用してインストールすることも禁止されません。

このポリシーは、Microsoft® Active Directory®ドメインに参加している Windows インスタンスでのみ使用できます。
#### Windows の情報と設定
##### グループ ポリシー (ADMX) 情報
- GP 固有の名前: InstallDefault
- GP の名前: インストールの既定の動作を許可する
- GP パス: 管理用テンプレート/Microsoft Edge Update/アプリケーション
- GP ADMX ファイル名:  msedgeupdate.admx
##### Windows レジストリの設定
- パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 値の名前: InstallDefault
- 値の種類: REG_DWORD
##### サンプル値:
```
0x00000001
```
[ページのトップへ](#microsoft-edge---update-policies)


###  <a name="updatedefault"></a>UpdateDefault
####  <a name="update"></a>更新ポリシーのオーバーライドの既定値
>Microsoft Edge Update 1.2.145.5 以降

#### 説明
Microsoft Edge で利用できる更新プログラムを Microsoft Edge Update で処理する方法について、すべてのチャネルを対象とした既定の動作を指定できます。 特定のチャネルに対して['更新ポリシーの上書き'](#update) ポリシーを指定することにより、個々のチャネルに対して上書きできます。

  このポリシーを有効にした場合、Microsoft Edge Update では、以下のオプションの構成方法に従って Microsoft Edge の更新プログラムを処理します。
   - [常に更新を許可する]: 定期的な更新チェックまたは手動更新チェックで検出された場合に、更新プログラムを必ず適用します。
   - [自動サイレント更新のみ]: 更新プログラムは、定期的な更新チェックで検出された場合にのみ適用されます。
   - [手動更新のみ]: 更新プログラムは、ユーザーが実行した手動更新チェックで検出された場合にのみ適用されます。
   - [更新を無効にする]: 更新プログラムは適用されません。

  手動更新を選択した場合は、アプリの手動更新メカニズムを使用して、必ず定期的に更新プログラムをチェックしてください (手動更新メカニズムが利用できる場合)。 更新を無効にした場合は、定期的に更新プログラムをチェックして、ユーザーに配布してください。

  このポリシーを有効にして構成しない場合、Microsoft Edge Update は、['更新ポリシーの上書き'](#update) ポリシーで指定された使用可能な更新を処理します。

  このポリシーは、Microsoft® Active Directory®ドメインに参加している Windows インスタンスでのみ使用できます。
#### Windows の情報と設定
##### グループ ポリシー (ADMX) 情報
- GP 固有の名前: UpdateDefault
- GP の名前: 更新ポリシーのオーバーライドの既定値
- GP パス: 管理用テンプレート/Microsoft Edge Update/アプリケーション
- GP ADMX ファイル名:  msedgeupdate.admx
##### Windows レジストリの設定
- パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 値の名前: UpdateDefault
- 値の種類: REG_DWORD
##### サンプル値:
```
0x00000003
```
[ページのトップへ](#microsoft-edge---update-policies)


###  <a name="install"></a>Install
#### インストールを許可する
>Microsoft Edge Update 1.2.145.5 以降

#### 説明
ドメインに参加しているデバイスに Microsoft Edge チャネルをインストールできるかどうかを示します。

  このポリシーをチャネルに対して有効にすると、Microsoft Edge はインストールのブロックをされなくなります。

  チャネルに対してこのポリシーを無効にすると、Microsoft Edge はインストールされなくなります。

  チャネルにこのポリシーを構成しない場合、「[インストールの既定の動作を許可する](#installdefault)」 ポリシー構成により、ユーザーがMicrosoft Edge のそのチャネルをインストールできるかどうかが決まります。

  このポリシーは、Microsoft® Active Directory®ドメインに参加している Windows インスタンスでのみ使用できます。
#### Windows の情報と設定
##### グループ ポリシー (ADMX) 情報
- GP 固有の名前: Install
- GP の名前: インストールを許可する
- GP パス:  
  - 管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge
  - 管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Beta
  - 管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Canary
  - 管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Dev
- GP ADMX ファイル名:  msedgeupdate.admx
##### Windows レジストリの設定
- パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 値の名前:  
  - (Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- 値の種類: REG_DWORD
##### サンプル値:
```
0x00000001
```
[ページのトップへ](#microsoft-edge---update-policies)


###  <a name="update"></a>Update
####  <a name="update"></a>更新ポリシーのオーバーライド
>Microsoft Edge Update 1.2.145.5 以降

#### 説明
Microsoft Edge で利用できる更新プログラムを Microsoft Edge Update でどのように処理するかを指定します。

このポリシーを有効にした場合、Microsoft Edge Update では、以下のオプションの構成方法に従って Microsoft Edge の更新プログラムを処理します。
  - [常に更新を許可する]: 定期的な更新チェックまたは手動更新チェックで検出された場合に、更新プログラムを必ず適用します。
  - [自動サイレント更新のみ]: 更新プログラムは、定期的な更新チェックで検出された場合にのみ適用されます。
  - [手動更新のみ]: 更新プログラムは、ユーザーが実行した手動更新チェックで検出された場合にのみ適用されます。 (アプリによっては、このオプション用のインターフェイスがない場合もあります。)
  - [更新を無効にする]: 更新プログラムは適用されません。

手動更新を選択した場合は、アプリの手動更新メカニズムを使用して、必ず定期的に更新プログラムをチェックしてください (手動更新メカニズムが利用できる場合)。 更新を無効にした場合は、定期的に更新プログラムをチェックして、ユーザーに配布してください。

このポリシーを有効にせず、構成しない場合、Microsoft Edge Update は、[「更新ポリシー上書きの既定値」](#updatedefault) ポリシーで指定された使用可能な更新プログラムを処理します。

詳細については、「[https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406)」を参照してください。

このポリシーは、Microsoft® Active Directory®ドメインに参加している Windows インスタンスでのみ使用できます。
#### Windows の情報と設定
##### グループ ポリシー (ADMX) 情報
- GP 固有の名前: Update
- GP の名前: 更新ポリシーのオーバーライド
- GP パス:  
  - 管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge
  - 管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Beta
  - 管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Canary
  - 管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Dev
- GP ADMX ファイル名:  msedgeupdate.admx
##### Windows レジストリの設定
- パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 値の名前:  
  - (Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- 値の種類: REG_DWORD
##### サンプル値:
```
0x00000001
```
[ページのトップへ](#microsoft-edge---update-policies)


###  <a name="allowsxs"></a>Allowsxs
####  <a name="accessibility-in-microsoft-edge"></a>Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する
>Microsoft Edge Update 1.2.145.5 以降

#### 説明
このポリシーを使用すると、ユーザーは Microsoft Edge (Edge HTML) と Microsoft Edge (Chromium ベース) を同時に実行できます。

このポリシーを "未構成" に設定した場合、Microsoft Edge (Chromium ベース) 安定チャネルと 2019 年 11 月のセキュリティ更新プログラムをインストールすると、Microsoft Edge (Edge HTML) が Microsoft Edge (Chromium ベース) に置き換わります。  これは、"無効" に設定した場合と同じ動作です。

"無効" に設定した場合、同時実行エクスペリエンスがブロックされ、Microsoft Edge (Chromium ベース) 安定チャネルと 2019 年 11 月のセキュリティ更新プログラムをインストールすると、Microsoft Edge (Edge HTML) が Microsoft Edge (Chromium ベース) に置き換わります。  これは、"未構成" に設定した場合と同じ動作です。

このポリシーを "有効" に設定した場合、Microsoft Edge (Chromium ベース) をインストールすると、Microsoft Edge (Chromium ベース) と Microsoft Edge (Edge HTML) を同時に実行できます。

このグループ ポリシーを有効するには、Windows Update による Microsoft Edge (Chromium ベース) の自動インストールが行われる前に、ポリシーを構成する必要があります。 注意: ユーザーは、Microsoft Edge (Chromium ベース) Blocker Toolkit を使用して、Microsoft Edge (Chromium ベース) の自動更新をブロックできます。
#### Windows の情報と設定
##### グループ ポリシー (ADMX) 情報
- GP 固有の名前: Allowsxs
- GP の名前: Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する
- GP パス: 管理用テンプレート/Microsoft Edge Update/アプリケーション
- GP ADMX ファイル名:  msedgeupdate.admx
##### Windows レジストリの設定
- パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 値の名前: Allowsxs
- 値の種類: REG_DWORD
##### サンプル値:
```
0x00000001
```
[ページのトップへ](#microsoft-edge---update-policies)


###  <a name="createdesktopshortcutdefault"></a>CreateDesktopShortcutDefault
#### 既定値のインストール時にデスクトップへのショートカットの作成を禁止する
>Microsoft Edge Update 1.3.128.0 以降

#### 説明
Microsoft Edge がインストールされている場合に、デスクトップにショートカットを作成するすべてのチャネルに対する既定の動作を指定できます。

  このポリシーを有効にすると、Microsoft Edge がインストールされている場合、デスクトップにショートカットが作成されます。
このポリシーを無効にすると、Microsoft Edge インストールされていても、デスクトップにショートカットは作成されません。
このポリシーを構成していない場合は、インストール中に Microsoft Edge のデスクトップにショートカットが作成されます。
Microsoft Edge が既にインストールされている場合、このポリシーの効果はありません。
#### Windows の情報と設定
##### グループ ポリシー (ADMX) 情報
- GP 固有の名前: CreateDesktopShortcutDefault
- GP の名前: 既定値のインストール時にデスクトップへのショートカットの作成を禁止する
- GP パス: 管理用テンプレート/Microsoft Edge Update/アプリケーション
- GP ADMX ファイル名:  msedgeupdate.admx
##### Windows レジストリの設定
- パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 値の名前: CreateDesktopShortcutDefault
- 値の種類: REG_DWORD
##### サンプル値:
```
0x00000001
```
[ページのトップへ](#microsoft-edge---update-policies)


###  <a name="createdesktopshortcut"></a>CreateDesktopShortcut
#### インストール時にデスクトップへのショートカットの作成を禁止する
>Microsoft Edge Update 1.3.128.0 以降

#### 説明
このポリシーを有効にすると、Microsoft Edge がインストールされている場合、デスクトップにショートカットが作成されます。
このポリシーを無効にすると、Microsoft Edge インストールされていても、デスクトップにショートカットは作成されません。
このポリシーを構成していない場合は、インストール中に Microsoft Edge のデスクトップにショートカットが作成されます。
Microsoft Edge が既にインストールされている場合、このポリシーの効果はありません。

  チャネルにこのポリシーを構成しない場合、「[インストール時にデスクトップショートカットを作成しない](#createdesktopshortcutdefault)」ポリシー構成により、Microsoft Edge のインストール時にショートカットの作成が決まります。
#### Windows の情報と設定
##### グループ ポリシー (ADMX) 情報
- GP 固有の名前: CreateDesktopShortcut
- GP の名前: インストール時にデスクトップへのショートカットの作成を禁止する
- GP パス:  
  - 管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge
  - 管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Beta
  - 管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Canary
  - 管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Dev
- GP ADMX ファイル名:  msedgeupdate.admx
##### Windows レジストリの設定
- パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- キーの値:  
  - (Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- 値の種類: REG_DWORD
##### サンプル値:
```
0x00000001
```
[ページのトップへ](#microsoft-edge---update-policies)


###  <a name="rollbacktotargetversion"></a>RollbackToTargetVersion
#### ターゲットバージョンにロールバックする
>Microsoft Edge Update 1.3.133.3以降

#### 説明
Microsoft Edge の更新プログラムで、Microsoft Edge のインストールを '[ターゲットバージョンの上書き](#targetversionprefix)' で指定されたバージョンにロールバックするように指定します。

このポリシーは、[[ターゲットバージョンが上書きする]](#targetversionprefix)' が設定されていて、[[更新ポリシーの上書き]](#update)' がオン状態のいずれかに設定されている場合を除き (常に更新プログラム、自動サイレント更新のみ、手動更新のみを許可します)何も影響がありません。

このポリシーを無効にした場合、または構成しなかった場合、'[ターゲットバージョンの上書き](#targetversionprefix)' で指定されているバージョンよりも高いバージョンにするようなインストールは変化せずそのまま残ります。

このポリシーを有効にした場合、["ターゲットバージョンの上書き](#targetversionprefix)" によって指定されたよりも高いバージョンにするようなインストールは、ターゲットバージョンにダウングレードされます。

最新のセキュリティ更新プログラムによる保護機能を使用するには、Microsoft Edge ブラウザーの最新バージョンをインストールすることをお勧めします。 以前のバージョンにロールバックすると、既知のセキュリティ問題にさらされるリスクがあります。 このポリシーは、Microsoft Edge ブラウザーの更新プログラムの問題に対処するための一時的な修正プログラムとして使用されます。

ブラウザーのバージョンを一時的にロールバックする前に、組織内のすべてのユーザーの同期 ([https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032)) を有効にすることを強くお勧めします。 同期を有効にしない場合、閲覧データが永久に失われる危険性があります。 このポリシーは、自己の責任においてご使用ください。

注: ロールバック可能なすべてのバージョンは、ここにあります [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise)。

これは、Microsoft Edge バージョン 86以降に適用されます。

詳細については、「[https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918)」を参照してください。

このポリシーは、Microsoft® Active Directory®ドメインに参加している Windows インスタンスでのみ使用できます。
#### Windows の情報と設定
##### グループ ポリシー (ADMX) 情報
- GP 固有の名前: RollbackToTargetVersion
- GP 名: ターゲットバージョンにロールバックする
- GP パス:  
  - 管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge
  - 管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Beta
  - 管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Canary
  - 管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Dev
- GP ADMX ファイル名:  msedgeupdate.admx
##### Windows レジストリの設定
- パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- キーの値:  
  - (Stable): RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (ベータ): RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (カナリア): RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- 値の種類: REG_DWORD
##### サンプル値:
```
0x00000001
```
[ページのトップへ](#microsoft-edge---update-policies)


###  <a name="targetversionprefix"></a>TargetVersionPrefix
#### ターゲット バージョンの上書き
>Microsoft Edge Update 1.3.119.43 以降

#### 説明
このポリシーを有効にして自動更新を有効にすると、Microsoft Edge がこのポリシー値で指定されたバージョンに更新されます。

ポリシー値は、83.0.499.12 のような特定の Microsoft Edge バージョンである必要があります。

指定した値より新しいバージョンの Microsoft Edge がデバイスにある場合、Microsoft Edge は新しいバージョンのままとなり、指定されたバージョンにダウングレードされません。

指定したバージョンが存在しない場合、または正しく書式設定されていない場合は、Microsoft Edge は現在のバージョンにとどまり、将来のバージョンに自動的に更新されません。

詳細については、「[https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707)」を参照してください。

このポリシーは、Microsoft® Active Directory®ドメインに参加している Windows インスタンスでのみ使用できます。
#### Windows の情報と設定
##### グループ ポリシー (ADMX) 情報
- GP 固有の名前: TargetVersionPrefix
- GP の名前: ターゲット バージョンの上書き
- GP パス:  
  - 管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge
  - 管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Beta
  - 管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Canary
  - 管理用テンプレート/Microsoft Edge Update/アプリケーション/Microsoft Edge Dev
- GP ADMX ファイル名:  msedgeupdate.admx
##### Windows レジストリの設定
- パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- キーの値:  
  - (Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- 値の種類: REG_SZ
##### サンプル値:
```
83.0.499.12
```
[ページのトップへ](#microsoft-edge---update-policies)


##  <a name="preferences-policies"></a>基本設定に関するポリシー

[ページのトップへ](#microsoft-edge---update-policies)
###  <a name="autoupdatecheckperiodminutes"></a>AutoUpdateCheckPeriodMinutes
#### 自動更新チェック期間のオーバーライド
>Microsoft Edge Update 1.2.145.5 以降

#### 説明
有効にした場合、このポリシーによって、自動更新チェックの最小間隔の値 (分単位) を設定できます。 有効にしなかった場合、自動更新チェックでは、既定で 10 時間ごとに更新が確認されます。

  すべての自動更新チェックを無効にする場合は、値を 0 に設定します (推奨しません)。
#### Windows の情報と設定
##### グループ ポリシー (ADMX) 情報
- GP 固有の名前: AutoUpdateCheckPeriodMinutes
- GP の名前: 自動更新チェック期間のオーバーライド
- GP パス: 管理用テンプレート/Microsoft Edge Update/基本設定
- GP ADMX ファイル名:  msedgeupdate.admx
##### Windows レジストリの設定
- パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 値の名前: AutoUpdateCheckPeriodMinutes
- 値の種類: REG_DWORD
##### サンプル値:
```
0x00000578
```
[ページのトップへ](#microsoft-edge---update-policies)


###  <a name="updatessuppressed"></a>UpdatesSuppressed
#### 自動更新チェックを停止する 1 日あたりの時間帯
>Microsoft Edge Update 1.3.33.5 以降

#### 説明
このポリシーを有効にした場合、更新チェックは毎日指定の時刻 (時:分) に停止され、一定の期間、更新チェックが行われなくなります (分単位)。 この期間では夏時間が考慮されません。 たとえば、開始時間が 22:00、期間が 480 分の場合、その期間内で夏時間の開始や終了が発生しても、更新は正確に 8 時間停止されます。

  このポリシーを無効にした場合または構成しなかった場合、更新チェックが一定期間停止されることはありません。
#### Windows の情報と設定
##### グループ ポリシー (ADMX) 情報
- GP 固有の名前: UpdatesSuppressed
- GP の名前: 自動更新チェックを停止する 1 日あたりの時間帯
  - オプション { Hour, Minute, Duration }
- GP パス: 管理用テンプレート/Microsoft Edge Update/基本設定
- GP ADMX ファイル名:  msedgeupdate.admx
##### Windows レジストリの設定
- パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 値の名前:  
  - UpdatesSuppressedDurationMin
  - UpdatesSuppressedStartHour
  - UpdatesSuppressedStartMin
- 値の種類: REG_DWORD
##### サンプル値:
```
duration   : 0x0000003c
start hour : 0x00000001
start min  : 0x00000002
```
[ページのトップへ](#microsoft-edge---update-policies)


##  <a name="proxy-server-policies"></a>プロキシ サーバーに関するポリシー

[ページのトップへ](#microsoft-edge---update-policies)
###  <a name="proxymode"></a>ProxyMode
#### プロキシ サーバーの設定をどのように指定するかを選択する
>Microsoft Edge Update 1.3.21.81 以降

#### 説明
Microsoft Edge Update で使用されるプロキシ サーバーの設定を指定できます。

  このポリシーを有効にした場合、以下のプロキシ サーバーのオプションを選択できます。
   - プロキシ サーバーを使用せず、常に直接接続することを選択した場合、他のオプションはすべて無視されます。
   - システム プロキシ設定を使用するか、プロキシ サーバーの自動検出を選択した場合、他のオプションはすべて無視されます。
   - 固定サーバー プロキシ モードを選択した場合、'[プロキシ サーバーのアドレスまたは URL](#proxyserver)' でさらにオプションを指定できます。
   - .pac プロキシスクリプトを使用する場合は、'[プロキシ .pac ファイルへの URL ](#proxypacurl)' ポリシーでスクリプトの URL を指定する必要があります。

  このポリシーを有効にした場合、組織内のユーザーは Microsoft Edge Update でプロキシ設定を変更できません。

  このポリシーを無効にした場合または構成しなかった場合、プロキシ サーバーの設定は構成されませんが、組織内のユーザーは Microsoft Edge Update で独自のプロキシ設定を選択できます。
#### Windows の情報と設定
##### グループ ポリシー (ADMX) 情報
- GP 固有の名前: ProxyMode
- GP の名前: プロキシ サーバーの設定をどのように指定するかを選択する
- GP パス: 管理用テンプレート/Microsoft Edge Update/プロキシ サーバー
- GP ADMX ファイル名:  msedgeupdate.admx
##### Windows レジストリの設定
- パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 値の名前: ProxyMode
- 値の種類: REG_SZ
##### サンプル値:
```
fixed_servers
```
[ページのトップへ](#microsoft-edge---update-policies)


###  <a name="proxypacurl"></a>ProxyPacUrl
#### プロキシ .pac ファイルへの URL
>Microsoft Edge Update 1.3.21.81 以降

#### 説明
プロキシ自動構成 (PAC) ファイルの URL を指定できます。

  このポリシーを有効にした場合、PAC ファイルの URL を指定して、特定の Web サイトを取得するための適切なプロキシサーバーを Microsoft Edge Update で選択する方法を自動化できます。

  このポリシーは、 '[プロキシサーバー設定の指定方法を選択する](#proxymode)' ポリシーで手動プロキシ設定を指定した場合にのみ適用されます。

  '[プロキシ サーバーの設定をどのように指定するかを選択する](#proxymode)'ポリシーで手動以外のプロキシ設定を選択した場合は、このポリシーを構成しないでください。
#### Windows の情報と設定
##### グループ ポリシー (ADMX) 情報
- GP 固有の名前: ProxyPacUrl
- GP の名前: プロキシ .pac ファイルへの URL
- GP パス: 管理用テンプレート/Microsoft Edge Update/プロキシ サーバー
- GP ADMX ファイル名:  msedgeupdate.admx
##### Windows レジストリの設定
- パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 値の名前: ProxyPacUrl
- 値の種類: REG_SZ
##### サンプル値:
```
https://www.microsoft.com
```
[ページのトップへ](#microsoft-edge---update-policies)


###  <a name="proxyserver"></a>ProxyServer
#### プロキシ サーバーのアドレスまたは URL
>Microsoft Edge Update 1.3.21.81 以降

#### 説明
Microsoft Edge Update で使用するプロキシ サーバーの URL を指定できます。

  このポリシーを有効にした場合、組織内の Microsoft Edge Update が使用するプロキシ サーバーの URL を設定できます。

  このポリシーは、 '[プロキシサーバー設定の指定方法を選択する](#proxymode)' ポリシーで手動プロキシ設定を指定した場合にのみ適用されます。

  '[プロキシ サーバーの設定をどのように指定するかを選択する](#proxymode)'ポリシーで手動以外のプロキシ設定を選択した場合は、このポリシーを構成しないでください。
#### Windows の情報と設定
##### グループ ポリシー (ADMX) 情報
- GP 固有の名前: ProxyServer
- GP の名前: プロキシ サーバーのアドレスまたは URL
- GP パス: 管理用テンプレート/Microsoft Edge Update/プロキシ サーバー
- GP ADMX ファイル名:  msedgeupdate.admx
##### Windows レジストリの設定
- パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 値の名前: ProxyServer
- 値の種類: REG_SZ
##### サンプル値:
```
https://www.microsoft.com
```
[ページのトップへ](#microsoft-edge---update-policies)


##  <a name="microsoft-edge-webview-policies"></a>Microsoft Edge WebView に関するポリシー

[ページのトップへ](#microsoft-edge---update-policies)
###  <a name="install-(webview)"></a>インストール (WebView)
#### インストールを許可する
>Microsoft Edge Update 1.3.127.1 以降

#### 説明
Microsoft Edge Update を使用して Microsoft Edge WebView をインストールできるかどうかを指定します。

  - このポリシーを有効にした場合、ユーザーは Microsoft Edge Update を使用して、Microsoft Edge WebView をインストールできます。
  - このポリシーを無効にした場合、ユーザーは Microsoft Edge Update を使用して Microsoft Edge WebView をインストールできません。
  - このポリシーを構成しなかった場合、"[インストールの既定の動作を許可する](#installdefault)" ポリシーの構成に従って、ユーザーが Microsoft Edge Update を使用して Microsoft Edge WebView をインストールできるかどうかが決まります。
#### Windows の情報と設定
##### グループ ポリシー (ADMX) 情報
- GP 固有の名前: Install
- GP の名前: インストールを許可する
- GP パス: 管理用テンプレート/Microsoft Edge Update/Microsoft Edge WebView
- GP ADMX ファイル名:  msedgeupdate.admx
##### Windows レジストリの設定
- パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- キーの値:  
  - Install{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
- 値の種類: REG_DWORD
##### サンプル値:
```
0x00000001
```
[ページのトップへ](#microsoft-edge---update-policies)


###  <a name="update-(webview)"></a>更新 (WebView)
####  <a name="update"></a>更新ポリシーのオーバーライド
>Microsoft Edge Update 1.3.127.1 以降

#### 説明
Microsoft Edge WebView の自動更新を有効にするかどうかを指定できます。 Microsoft Edge WebView は、アプリケーションが Web コンテンツを表示するために使用するコンポーネントです。
自動更新は、既定で有効になっています。 Microsoft Edge WebView の自動更新を無効にすると、このコンポーネントに依存するアプリケーションで互換性の問題が発生する可能性があります。

  このポリシーを有効にした場合、Microsoft Edge Update では、以下のオプションの構成方法に従って Microsoft Edge WebView の更新プログラムを処理します。
  - [常に更新プログラムを許可する]: 更新プログラムは自動的にダウンロードされ、適用されるます
  - [更新を無効にする]: 更新プログラムはダウンロードまたは適用されません

  このポリシーを有効にしないと、更新プログラムが自動的にダウンロードされ、適用されます。
#### Windows の情報と設定
##### グループ ポリシー (ADMX) 情報
- GP 固有の名前: Update
- GP の名前: 更新ポリシーのオーバーライド
- GP パス: 管理用テンプレート/Microsoft Edge Update/Microsoft Edge WebView
- GP ADMX ファイル名:  msedgeupdate.admx
##### Windows レジストリの設定
- パス: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- キーの値:  
  - Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
- 値の種類: REG_DWORD
##### サンプル値:
```
0x00000001
```
[ページのトップへ](#microsoft-edge---update-policies)


##  <a name="see-also"></a>関連項目
  - [Microsoft Edge の構成](configure-microsoft-edge.md)
  - [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)