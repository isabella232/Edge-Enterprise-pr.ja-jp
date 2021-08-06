---
title: Internet Explorer モードでページ内ナビゲーションを保持する
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Internet Explorer モードでページ内ナビゲーションを保持する
ms.openlocfilehash: f1c40977ba07f0a85bc64aab8e609163f9a68dd2eb7487adff6b6a1fcbd110f2
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "11724292"
---
# <a name="keep-in-page-navigation-in-internet-explorer-mode"></a>Internet Explorer モードでページ内ナビゲーションを保持する

このポリシーは、Internet Explorer モード (IE モード) サイトからのすべてのページ内ナビゲーションを強制的に IE モードにするための一時的なソリューションとして使用できます。

ページ内ナビゲーションは、現在のページのリンク、スクリプト、またはフォームから開始されます。 また、前回のページ内ナビゲーションの試行のサーバー側リダイレクトにもなります。 逆に、ユーザーはブラウザーの制御で、現在のページから独立したページ内ではないナビゲーションを開始することができます。 たとえば、アドレス バー、[戻る] ボタン、またはお気に入りリンクを使用する場合です。

>[!NOTE]
>この記事は、Microsoft Edge version 81 以降に適用されます。

## <a name="prerequisites"></a>前提条件

このポリシーには、次の Windows 更新プログラムが必要です。

- Windows 10 Version 1909 と 1903、Windows Server Version 1909 と 1903 ([KB4532695](https://support.microsoft.com/help/4532695))
- Windows 10 Version 1809、Windows Server Version 1809、Windows Server 2019 ([KB4534321](https://support.microsoft.com/help/4534321))
- Windows 10 Version 1803 ([KB4534308](https://support.microsoft.com/help/4534308))
- Windows 10 Version 1709 ([KB4534318](https://support.microsoft.com/help/4534318))


## <a name="about-this-policy"></a>このポリシーの詳細

このポリシーにより、IE モード サイトで使用されるすべての認証サーバーを識別して構成する時間が与えられます。 ただし、このポリシーを使用すると、一部のサイトが IE モードで表示されたり、Microsoft Edge モードで表示されたりする、一貫性のない閲覧エクスペリエンスが発生する可能性があります。 このエクスペリエンスは、サイトへのナビゲーションが IE モード ページから開始されたかどうかによって異なります。 特定のレンダリング エンジンで開くように明示的に構成されていないサイトはすべて、この矛盾の影響を受けます。

このポリシーを有効にする場合は、すべての認証サーバーを識別し、それらをニュートラルとしてサイト リストに追加した後で、このポリシーを無効にすることを推奨します。 このアクションにより、最新のサイトが不注意に IE モードで表示されなくなります。

## <a name="keep-in-page-navigation-in-ie-mode"></a>IE モードでページ内ナビゲーションを保持する

Internet Explorer モードで、自動またはすべてのページ内ナビゲーションを保持するには、次の手順を実行します。

1. ローカル グループ ポリシー エディターを開きます。
2. **[コンピューターの構成]** > **[管理用テンプレート]** > **[Microsoft Edge]** をクリックします。
3. [**設定**] で、[**Internet Explorer モード ページから起動したときに未構成サイトへの「ページ内」ナビゲーションの動作を指定する**] をダブルクリックします。

   ![ページ内ポリシーの設定](media/edge-learnmore-inpage-nav/learnmore-in-page-nav-settings.png)

4. [**有効**] を選択します。 

   ![ページ内ポリシーを有効にする](media/edge-learnmore-inpage-nav/learnmore-in-page-nav-enable.png)

5. ドロップダウン リストから、次のいずれかのオプションを選択します。

   - **既定** - Internet Explorer モードで開くように構成されたサイトのみが、そのモードで開きます。 Internet Explorer モードで開くように構成されていないサイトは、Microsoft Edge にリダイレクトされます。
   - **Internet Explorer モードで自動ナビゲーションのみを保持する** - 未構成サイトへのすべての自動ナビゲーション （302 リダイレクトなど） が Internet Explorer モードで保持されることを除いて、既定のエクスペリエンスが必要な場合は、このオプションを使用します。
   - **すべてのページ**内ナビゲーションを Internet Explorer モード (最小推奨 **_)_** に保持する - IE モードで読み込まれたページから未構成のサイトへのすべてのナビゲーションは、Internet Explorer モードで保持されます。

6. [**OK**] または [**適用**] をクリックして、このポリシー設定を保存します。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
