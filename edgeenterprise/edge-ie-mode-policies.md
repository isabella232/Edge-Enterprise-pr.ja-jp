---
title: IE モード ポリシーの構成
ms.author: collw
author: AndreaLBarr
manager: srugh
ms.date: 07/23/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: IE モード ポリシーの構成
ms.openlocfilehash: 7ca8dffb0bc20acf954cf0f272f3894b39355846
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "11980126"
---
# <a name="configure-ie-mode-policies"></a>IE モード ポリシーの構成

>[!Note]
> Internet Explorer 11 デスクトップ アプリケーションは廃止され、2022 年 6 月 15 日にサポートが終了します (スコープ内の一覧については、[FAQ を参照してください](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549))。 現在使用しているものと同じ IE11 アプリとサイトを、Internet Explorer モードの Microsoft Edge で開くことができます。 [こちらをご覧ください](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

この記事では、IE モード ポリシーの構成方法について説明します。

> [!NOTE]
> この記事は、Microsoft Edge version 77 (**Stable**、**Beta**、および **Dev** チャネル) 以降に適用されます。

IE モードを構成するには、次の3つの手順を実行する必要があります。

1. [Internet Explorer 統合を構成する](#configure-internet-explorer-integration)
2. [サイトを Microsoft Edge から IE モードにリダイレクトする](#redirect-sites-from-microsoft-edge-to-ie-mode)
3. (省略可能) [サイトを IE から Microsoft Edge にリダイレクトする](#redirect-sites-from-ie-to-microsoft-edge)

    1. IE11 アプリを無効にする準備ができている場合は、「[Internet Explorer 11 を無効にする](/deployedge/edge-ie-disable-ie11)」の手順に従います
    2. それ以外の場合は、「[サイトを IE から Microsoft Edge にリダイレクトする](/deployedge/edge-ie-mode-policies#redirect-sites-from-ie-to-microsoft-edge)」の残りの手順に従います

> [!NOTE]
> IE モードを有効にするポリシーは、Intune を使用して構成できます。 詳しくは、「[Microsoft Edge for Windows 10 を Microsoft Intune に追加する](/intune/apps/apps-windows-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)」および「[Microsoft Intune を使って Microsoft Edge ポリシー設定を構成する](./configure-edge-with-intune.md)」をご覧ください。

## <a name="configure-internet-explorer-integration"></a>Internet Explorer 統合を構成する

Microsoft Edge (IE モード) 内で直接開くように、Internet Explorer を構成できます。 スタンドアロンの Internet Explorer 11 ウィンドウで開くように、Internet Explorer を構成することもできます。 ほとんどのユーザーは、Microsoft Edge の IE モードでサイトを直接開くことを希望します。

### <a name="enable-internet-explorer-integration-using-group-policy"></a>グループ ポリシーを使用して Internet Explorer 統合を有効にする

1. 最新の [Microsoft Edge ポリシー テンプレート](https://www.microsoft.com/en-us/edge/business/download)をダウンロードして使用します。
2. グループ ポリシー エディターを開きます。
3. **[ユーザーの構成/コンピューターの構成]** > **[管理用テンプレート]** > **[Microsoft Edge]** をクリックします。
4. **[Internet Explorer 統合を構成する]** をダブルクリックします。
5. **[有効]** を選択します。
6. **[オプション]** で、ドロップダウンの値を次のように設定します。
   -  **[Internet Explorer モード]**: サイトを Microsoft Edge の IE モードで開く場合
   -  **Internet Explorer 11** のスタンドアロン Internet Explorer 11 ウィンドウでサイトを開く場合 (このオプションは、Internet Explorer 11 デスクトップ アプリケーションが廃止され、サポートが終了する 2022 年 6 月 15 日以降はサポートされません。  IE11 が使用できなくなった 2022 年 6 月 15 日以降、このオプションは Internet Explorer **モード オプションと同じように動作** します)。  
   -  **[なし]**: ユーザーが edge://flags またはコマンド ラインを使用して Internet Explorer モードを構成できないようにする場合

   > [!NOTE]
   > このポリシーを **[無効]** に設定することは、IE モードがポリシーによって無効になることを意味していますが、IE モードは edge://flags またはコマンド ライン オプションを使用して設定することもできます。
7. **[OK]** または **[適用]** をクリックして、このポリシー設定を保存します。

## <a name="redirect-sites-from-microsoft-edge-to-ie-mode"></a>サイトを Microsoft Edge から IE モードにリダイレクトする

IE モードで開くサイトを識別するには、次の2つのオプションがあります。

- (推奨) [エンタープライズ サイト一覧のサイトを構成する](#configure-sites-on-the-enterprise-site-list)
- [すべてのイントラネット サイトを構成する](#configure-all-intranet-sites)

### <a name="configure-sites-on-the-enterprise-site-list"></a>エンタープライズ サイト一覧のサイトを構成する

特定のサイトを IE モードで開くには、次のグループ ポリシーを使用して構成できます。

- [エンタープライズ モードの IE Web サイト一覧を使う](#configure-using-the-use-the-enterprise-mode-ie-website-list-policy) (Internet Explorer)
- [エンタープライズ モード サイト一覧を構成する](#configure-using-the-configure-the-enterprise-mode-site-list-policy) (Microsoft Edge version 78 以降)<br/>このポリシーでは、Microsoft Edge に対して別個のエンタープライズ モード サイト リストを作成できます。 このポリシーを有効にすると、[Internet Explorer 統合を構成する] が有効になっている場合に [エンタープライズ モードの IE Web サイト一覧を使う] ポリシーの設定がオーバーライドされます。 このポリシーを無効にした場合または構成しなかった場合、[Internet Explorer 統合を構成する] ポリシーの既定の動作には影響しません。
    > [!NOTE]
    > Microsoft Edge ポリシーの構成は必須ではありません。 多くの組織では、これをオーバーライドとして使用します。これにより、最新のサイト リストで IE ポリシーが有効なすべてのユーザーを対象とし、より簡単に更新バージョンを対象として Microsoft Edge ポリシーの使用をパイロットすることができます。

ユーザー モード サイト リストのEnterprise詳細については[、「Use the site List Manager」をEnterprise参照してください](/deployedge/edge-ie-mode-site-list-manager)。


### <a name="configure-using-the-use-the-enterprise-mode-ie-website-list-policy"></a>[エンタープライズ モードの IE Web サイト一覧を使う] ポリシーの使用を構成する

IE モードでは、Internet Explorer のエンタープライズ サイト リストを構成する既存のポリシーを使用して、単一のリストを作成し、管理することができます。

1. サイト リスト XML を作成または再利用します。
    1. 要素 _\<open-in\>IE11\</open-in\>_ が含まれているすべてのサイトが IE モードで開くようになります。
2. グループ ポリシー エディターを開きます。
3. **[ユーザーの構成/コンピューターの構成]** > **[管理用テンプレート]** > **[Windows コンポーネント]** > **[Internet Explorer]** をクリックします。
4. **[エンタープライズ モードの IE Web サイト一覧を使う]** をダブルクリックします。
5. **[有効]** を選択します。
6. **[オプション]** で、Web サイト一覧の場所を入力します。 次のいずれかの場所を使用できます。
    - (推奨) HTTPS の場所: **https**:**//iemode/sites.xml**
    - ローカル ネットワーク ファイル: **\\\network\shares\sites.xml**
    - ローカル ファイル: **file:///c:/Users/\<user\>/Documents/sites.xml**
7. **[OK]** または **[適用]** をクリックして、これらの設定を保存します。

### <a name="configure-using-the-configure-the-enterprise-mode-site-list-policy"></a>[エンタープライズ モード サイト リストを構成する] ポリシーの使用を構成する

Microsoft Edge に対して別個のポリシーを使用して IE モードを構成することもできます。 この追加のポリシーを使用すると、IE サイト リストをオーバーライドできます。 たとえば、一部の組織は、生産サイト リストの対象をすべてのユーザーにします。 その後、このポリシーを使用して、パイロット サイト リストを少数のユーザー グループに展開することができます。

1. サイト リスト XML を作成または再利用します。
    1. 要素 _\<open-in\>IE11\</open-in\>_ が含まれているすべてのサイトが IE モードで開くようになります。
2. グループ ポリシー エディターを開きます。
3. **[ユーザーの構成/コンピューターの構成]** > **[管理用テンプレート]** > **[Microsoft Edge]** をクリックします。
4. **[エンタープライズ モード サイト一覧を構成する]** をダブルクリックします。
5. **[有効]** を選択します。
6. **[オプション]** で、Web サイト一覧の場所を入力します。 次のいずれかの場所を使用できます。
    - (推奨) HTTPS の場所: **https**:**//iemode/sites.xml** <!--Trying to keep this from being an active link in MD -->
    - ローカル ネットワーク ファイル: **\\\network\shares\sites.xml**
    - ローカル ファイル: **file:///c:/Users/\<user\>/Documents/sites.xml**
7. **[OK]** または **[適用]** をクリックして、これらの設定を保存します。

### <a name="configure-all-intranet-sites"></a>すべてのイントラネット サイトを構成する

IE モードは、ローカル イントラネット ゾーンのすべてのサイトに対して構成できます。 エンタープライズ モード サイト リストを使用して、個々のサイトを IE モードから削除できます。

>[!NOTE]
>
> ローカル イントラネット ゾーンには明示的に追加されたサイトが含まれますが、ヒューリスティックを使用してサイトをこのゾーンに割り当てます。 これには、ドットなしのホスト名 (**https**:**//payroll** など) や、プロキシ構成スクリプトでプロキシをバイパスするように構成されているサイトが含まれます。 外部関係者が DNS またはプロキシを制御している場合、Web サイトを強制的に IE モードにする可能性があります。

1. ローカル グループ ポリシー エディターを開きます。
2. **[ユーザーの構成/コンピューターの構成]** > **[管理用テンプレート]** > **[Microsoft Edge]** をクリックします。
3. **[すべてのイントラネット サイトを Internet Explorer に送る]** をダブルクリックします。
4. **[有効]** を選択し、**[OK]** または **[適用]** をクリックしてポリシー設定を保存します。

## <a name="redirect-sites-from-ie-to-microsoft-edge"></a>サイトを IE から Microsoft Edge にリダイレクトする

Internet Explorer を必要としないサイトで、ユーザーが Internet Explorer を使用できないようにすることができます。 サイト リストにないサイトの場合、Internet Explorer ではそのサイトを自動的に Microsoft Edge にリダイレクトできます。

1. グループ ポリシー エディターを開きます。
2. **[ユーザーの構成/コンピューターの構成]** > **[管理用ツール]** > **[Windows コンポーネント]** > **[Internet Explorer]** をクリックします。
3. **[エンタープライズ モード サイト一覧に含まれていないすべてのサイトを Microsoft Edge に送信します]** をダブルクリックします。
4. **[有効]** を選択します。
5. **[OK]** または **[適用]** をクリックして、これらの設定を保存します。
6. **[リダイレクトされたサイトを開くときに使用する Microsoft Edge のチャネルを構成する]** をダブルクリックします。
7. **[有効]** を選択します。
8. **[オプション]** で、使用する上位 3 つのチャネルを選択します。Internet Explorer では、ユーザーがデバイスにインストールした、最も高くランク付けされたチャネルにリダイレクトします。
   - Microsoft Edge Stable
   - Microsoft Edge Beta バージョン 77 以降
   - Microsoft Edge Dev バージョン 77 以降
   - Microsoft Edge Canary バージョン 77 以降
   - Microsoft Edge バージョン 45 以前
9. **[OK]** または **[適用]** をクリックして、これらの設定を保存します。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [IE モードの概要](./edge-ie-mode.md)
- [その他のエンタープライズ モード情報](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
