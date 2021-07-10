---
title: Microsoft Intune を使って Windows 用の Microsoft Edge ポリシー設定を構成する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Intune を使って Windows 用の Microsoft Edge ポリシー設定を構成します。
ms.openlocfilehash: adcd80f68250a9694b9bbaa21fb7941ebcbaf15a
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641673"
---
# <a name="configure-microsoft-edge-policy-settings-with-microsoft-intune"></a>Microsoft Intune を使って Microsoft Edge ポリシー設定を構成する

この記事では、Microsoft Intune を使って Windows 10 用の Microsoft Edge ポリシー設定を構成する方法について説明します。

> [!NOTE]
> この記事は Microsoft Edge version 77 以降に適用されます。

デバイス構成プロファイルを Microsoft Intune に追加することで、Microsoft Edge のポリシーと設定を構成できます。 Intune を使用してポリシーを管理および適用することは、Active Directory グループ ポリシーを使用するか、ユーザー デバイスでローカルのグループ ポリシー オブジェクト (GPO) 設定を構成することと同じです。

Microsoft Intune を使用して Microsoft Edge ポリシーを管理する方法について詳しくは、「[Microsoft Edge と Microsoft Intune を使用して Web アクセスを管理する](/intune/manage-microsoft-edge)」をご覧ください。ただし、この記事は Microsoft Edge version 45 以前を対象とした内容であるため、Microsoft Edge Enterprise version 77 以降に適用されない情報や参照が含まれていることがあります。

> [!TIP]
> Microsoft Intune を使用して macOS で Microsoft Edge を構成する方法については、[macOS 用の構成](configure-microsoft-edge-on-mac.md)に関する情報をご覧ください。

## <a name="create-a-profile-to-manage-settings-in-microsoft-edge-for-windows-10"></a>プロファイルを作成して Microsoft Edge for Windows 10 の設定を管理する

Microsoft Intune の管理用テンプレートを使用すると、クラウドを使用して Windows 10 デバイス上の Microsoft Edge グループ ポリシーを管理できます。 このセクションでは、Microsoft Edge 固有のアプリケーション設定を構成するためのテンプレートを作成する方法について説明します。 テンプレートを作成すると、デバイス構成プロファイルが作成されます。 このプロファイルは、組織内の Windows 10 デバイスに割り当てることも、展開することもできます。

### <a name="prerequisites"></a>前提条件

- 以下の最小システム要件を満たす Windows 10:
  - Windows 10 Version 1909
  - [KB4512941](https://support.microsoft.com/kb/4512941) をインストール済みの Windows 10 Version 1903
  - [KB4512534](https://support.microsoft.com/kb/4512534) をインストール済みの Windows 10 Version 1809
  - [KB4512509](https://support.microsoft.com/kb/4512509) をインストール済みの Windows 10 Version 1803
  - [KB4516071](https://support.microsoft.com/kb/4516071) をインストール済みの Windows 10 Version 1709

### <a name="use-administrative-templates-to-create-a-policy-for-microsoft-edge"></a>管理用テンプレートを使用して Microsoft Edge のポリシーを作成する

この手順では、Intune に組み込まれた管理用テンプレート (グループポリシーで使い慣れているもの) を使用します。 これらのテンプレートを使用して、事前に構成されたリストから設定を選択することによって、Microsoft Edge のポリシーを作成できます。

1. [Microsoft エンドポイント マネージャー](https://endpoint.microsoft.com/) ポータルにサインインします。
2. ナビゲーション ウィンドウの左側にある [**デバイス**] を選択します。
3. [**Devices**] | [**概要**] で [**構成プロファイル**] を選択します (ポリシーの見出しの下)。
4. 上部のコマンド バーで、**[プロファイルの作成]** を選択します。
5. [**プラットフォーム**] の下にあるドロップダウン リストで、[**Windows 10 以降**] を選択します。
6. [**プロファイル**] の下にあるドロップダウン リストで、[**管理用テンプレート**] を選択して、[**作成**] ボタンをクリックします。 次のスクリーンショットは、プラットフォームとプロファイルの種類を選択できるドロップダウン リストを示しています。

    ![プラットフォームとプロファイルの種類を選択する](./media/configure-edge-with-intune/create-profile-platform.png)

7. [**基本**] タブで、「Microsoft Edge ポリシー」 などのわかりやすい [**名前**] を入力します。 必要に応じて、ポリシーの **説明** を入力します。
次のスクリーンショットでは、[**基本**] タブのフォームを示しています。また、メニューバーにはプロファイルを作成するための次の手順 (灰色表示されているタブ) が表示されます。

   ![名前と説明を入力する](./media/configure-edge-with-intune/create-profile-basics-tab.png)

8. **[次へ]** を選択します。
9. [**構成の設定**] タブで、次のいずれかの場所にある Microsoft Edge フォルダーを選択します。

   - [コンピューターの構成] フォルダーの下
   - [ユーザーの構成] フォルダーの下にあります。

   Microsoft Edge の使用可能な設定が右側のウィンドウに表示されます。 たとえば、次のスクリーンショットに示されているように、*[コンピューターの構成]、[Microsoft Edge]、[ダウンロードの制限を許可する]* などがあります。

   ![[構成設定] タブ](./media/configure-edge-with-intune/create-profile-configuration-settings-tab.png)

   > [!NOTE]
   > Microsoft Edge の使用可能なすべての設定の完全かつ最新のリストについては、「[Microsoft Edge のポリシー](./microsoft-edge-policies.md)」 と 「[Microsoft Edge の更新ポリシー](./microsoft-edge-update-policies.md)」 を参照してください。

10. [検索] フィールドを使用して ("検索してアイテムをフィルター処理します...")、構成する特定の設定を検索します。 この例では、検索文字列は "ホームページ" です。 次のスクリーンショットは、検索結果を示しています。

    ![検索結果](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-search.png)

11. 構成する設定を見つけたら、それを選択して設定できる値を公開します。 次のスクリーンショットでは、例として [ホームページの URL を構成する] を選択しました。

    ![ホーム ページの URL ポリシーを構成する](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-edit-pol.png)

12. 前のスクリーンショットで示すように、ポリシーを有効にして、ホームページの URL に値を入力します。

13. **[OK]** をクリックします。 [状態] 列の設定は、次のスクリーンショットの例のように "有効" と表示されます。

    ![設定の状態が有効になります](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-set-enabled.png)

14. **[次へ]** ボタンをクリックします。

15. [**範囲タグ**] タブで、必要に応じて範囲タグを追加します。それ以外の場合は、[**次へ**] をクリックします。

16. [**割り当て**] タブで、[**含めるグループを選択**] をクリックしてこのポリシーをデバイスを含む Azure Active Directory (Azure AD) グループ、またはこのポリシー設定を受信するユーザーに割り当てます。 Azure AD のユーザーまたはデバイス グループにプロファイルを割り当てる方法については、「[Microsoft Intune でユーザーおよびデバイス プロファイルを割り当てる](/intune/device-profile-assign)」をご覧ください。

    ![含めるグループを選択する](./media/configure-edge-with-intune/create-profile-assignments-tab.png)

17. **[次へ]** ボタンをクリックします。

18. [**確認および作成**] タブで、変更の概要をレビューして、正しいことを確認してから [**作成**] ボタンをクリックします。

19. 新しく作成されたポリシー (Microsoft Edge ポリシー) は、次のスクリーンショットに示されています。

    ![含めるグループを選択する](./media/configure-edge-with-intune/create-profile-new-policy-finished.png)

Windows 10 プロファイルについて詳しくは[、「Windows 10 テンプレートを使用して Microsoft Intune](/intune/administrative-templates-windows)でグループポリシー設定を構成する」を参照してください。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge と Microsoft Intune を使用して Web アクセスを管理する](/intune/manage-microsoft-edge)
- [Windows 10 テンプレートを使用し、Microsoft Intune でグループ ポリシー設定を構成する](/intune/administrative-templates-windows)
- [Microsoft Intune を使用して Microsoft Edge を展開する](/intune/apps/apps-windows-edge/?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)