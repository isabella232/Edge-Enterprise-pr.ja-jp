---
title: Internet Explorer モードとは
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 06/28/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge の Internet Explorer モードが、Internet Explorer 11 を必要とするサイトへのアクセスと最新のサイトへのアクセスをどのように提供するかについて説明します。
ms.openlocfilehash: 7d1d9d201abee9cd9f0d648f2757e3276945d2f4dcf635ea0cd17a64e684aec4
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "11726066"
---
# <a name="what-is-internet-explorer-ie-mode"></a>Internet Explorer (IE) モードとは

>[!Note]
> Internet Explorer 11 デスクトップ アプリケーションは廃止され、2022 年 6 月 15 日にサポートが終了します (スコープ内の一覧については、[FAQ を参照してください](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549))。 現在使用しているものと同じ IE11 アプリとサイトを、Internet Explorer モードの Microsoft Edge で開くことができます。 [こちらをご覧ください](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

既存の Web サイトとの下位互換性のために Internet Explorer 11 が必要であるが、最新のブラウザーも必要な組織向けに、Microsoft Edge で Internet Explorer (IE) モードを作成しました。 この機能により、組織は 1 つのブラウザーを、従来の Web/アプリまたは最新の Web/アプリに簡単に使用できます。 この記事では、IE モードで Microsoft Edge を使用する方法を紹介します。

> [!NOTE]
> この記事は Microsoft Edge バージョン 77 以降に適用されます。

## <a name="what-is-ie-mode"></a>IE モードとは

Microsoft Edge で IE モードを利用すると、組織が必要とするすべてのサイトを 1 つのブラウザーで簡単に使用できます。 これは、最新のサイトには、組み込まれている Chromium エンジンを使用し、従来のサイトには、Internet Explorer 11 (IE11) から Trident MSHTML エンジンを使用します。

サイトが IE モードで読み込まれると、IE ロゴ インジケーターがナビゲーション バーの左側に表示されます。 IE ロゴ インジケーターをクリックすると、以下のように詳細情報を表示できます。

  ![IE ロゴ インジケーター](./media/ie-mode/ie-logo-indicator1.png)

(ポリシー経由で) 個別に構成したサイトのみが IE モードを使用し、他のすべてのサイトは、最新の Web サイトとして表示されます。 サイトで IE モードを使用するには、次の操作を行う必要があります。

- 以下のいずれかのポリシーで定義されているエンタープライズ モード サイト リスト XML で、サイトをリストします。
  - Microsoft Edge 78 以降: "エンタープライズ モード サイト一覧を構成する"
  - Internet Explorer: "エンタープライズ モードの IE Web サイト一覧を使う"
  > [!NOTE]
  > 1 つのエンタープライズ モード サイト リストのみが処理されます。 Microsoft Edge のサイト リストのポリシーは、Internet Explorer のサイト リストのポリシーよりも優先されます。
- **[すべてのイントラネット サイトを Internet Explorer に送る]** グループ ポリシーが有効になっている場合はすべてのイントラネットサイト (Microsoft Edge 77 以降)

### <a name="ie-mode-supports-the-following-internet-explorer-functionality"></a>IE モードでサポートされる Internet Explorer 機能

- すべてのドキュメント モードとエンタープライズ モード
- ActiveX コントロール (Java や Silverlight など)
- ブラウザー ヘルパー オブジェクト 
- セキュリティ ゾーン設定と保護モードに影響を与える Internet Explorer 設定とグループ ポリシー
- [IEChooser](/office/dev/add-ins/testing/debug-add-ins-using-f12-developer-tools-on-windows-10) で起動する場合、IE 用の F12 開発者ツール
- Microsoft Edge の拡張機能 (IE ページのコンテンツを直接操作する拡張機能はサポートされていません)

### <a name="ie-mode-doesnt-support-the-following-internet-explorer-functionality"></a>IE モードでサポートされない Internet Explorer 機能

- Internet Explorer ツール バー
- ナビゲーション メニュー (検索エンジン、ホーム ページなど) に影響する Internet Explorer 設定とグループ ポリシー
- IE11 または Microsoft Edge の F12 開発者ツール

## <a name="prerequisites"></a>前提条件

Microsoft Edge を IE モードで使用する場合は、次の前提条件が適用されます。

> [!IMPORTANT]
> 正常に完了するには、Windows と Microsoft Edge の最新の更新プログラムをインストールしてください。 これを行わないと、IE モードが失敗する可能性があります。

1. 次の表に示すオペレーティング システムの最小システム更新プログラム。

 | オペレーティング システム | バージョン       | 更新プログラム |
 |------------------|---------------|---------|
 | Windows 10       | 1909 以降 |         |
 | Windows 10       | 1903          | [KB4501375](https://support.microsoft.com/help/4501375/windows-10-update-kb4501375) 以降 |
 | Windows Server   | 1903          | [KB4501375](https://support.microsoft.com/help/4501375/windows-10-update-kb4501375) 以降 |
 | Windows 10       | 1809          | [KB4501371](https://support.microsoft.com/help/4501371/windows-10-update-kb4501371) 以降 |
 | Windows Server   | 1809          | [KB4501371](https://support.microsoft.com/help/4501371/windows-10-update-kb4501371) 以降 |
 | Windows Server   | 2019          | [KB4501371](https://support.microsoft.com/help/4501371/windows-10-update-kb4501371) 以降 |
 | Windows 10       | 1803          | [KB4512509](https://support.microsoft.com/help/4512509/windows-10-update-kb4512509) 以降 |
 | Windows 10       | 1709          | [KB4512494](https://support.microsoft.com/help/4512494/windows-10-update-kb4512494) 以降 |
 | Windows 10       | 1607          | [KB4516061](https://support.microsoft.com/help/4516061/windows-10-update-kb4516061) 以降 |
 | Windows Server   | 2016          | [KB4516061](https://support.microsoft.com/help/4516061/windows-10-update-kb4516061) 以降 |
 | Windows 10       | 初期バージョン、2015 年 7 月 | [KB4520011](https://support.microsoft.com/help/4520011/windows-10-update-kb4520011) 以降 |
 | Windows 8       | 8.1              | [KB4507463](https://support.microsoft.com/help/4507463/july-16-2019-kb4507463-os-build-preview-of-monthly-rollup) 以降、または [KB4511872 以降](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) |
 | Windows Server   | 2012 R2       | [KB4507463](https://support.microsoft.com/help/4507463/july-16-2019-kb4507463-os-build-preview-of-monthly-rollup) 以降、または [KB4511872 以降](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) |
 | Windows 8  | 内蔵型            | Internet Explorer 11 にアップグレードするには [KB4492872](https://support.microsoft.com/help/4492872/update-for-internet-explorer-april-16-2019) をインストールして、[KB4507447](https://support.microsoft.com/help/4507447/windows-server-2012-update-kb4507447) 以降または [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) 以降をインストールする |
 | Windows Server   | 2012           | Internet Explorer 11 にアップグレードするには [KB4492872](https://support.microsoft.com/help/4492872/update-for-internet-explorer-april-16-2019) をインストールして、[KB4507447](https://support.microsoft.com/help/4507447/windows-server-2012-update-kb4507447) 以降または [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) 以降をインストールする |
 | Windows 7        |  SP1**        | [KB4507437](https://support.microsoft.com/help/4507437/windows-7-update-kb4507437) 以降、または [](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) KB4511872 以降 |
 | Windows Server   |  2008 R2**    | [KB4507437](https://support.microsoft.com/help/4507437/windows-7-update-kb4507437) 以降、または [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) 以降 |
  > [!IMPORTANT]
  > ** Windows 7 および Windows Server 2008 R2 は、これらのオペレーティング システムのサポートが終了した後でも、Microsoft Edge でサポートされます。 これらのオペレーティング システムで IE モードをサポートするには、デバイスに [Windows 7 の拡張セキュリティ更新プログラム](https://support.microsoft.com/help/4527878/faq-about-extended-security-updates-for-windows-7)が必要になります。 保護された状態を維持するには、サポートされているオペレーティング システムにできるだけ早くアップグレードすることをお勧めします。 拡張セキュリティ更新プログラムによる Microsoft Edge のサポートは、、OS がサポートされた状態に移行するための暫定措置と見なす必要があります。

2. Microsoft Edge 管理用テンプレート。 詳しくは、「[Microsoft Edge を構成する](./configure-microsoft-edge.md)」をご覧ください。
3. Windows の機能で Internet Explorer 11 が有効になっていること。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [その他のエンタープライズ モード情報](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)