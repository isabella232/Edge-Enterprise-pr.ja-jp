---
title: Jamf を使用して macOS 用の Microsoft Edge 展開を自動化する
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Jamf を使用して macOS 用の Microsoft Edge 展開を自動化する方法。
ms.openlocfilehash: 9c8fc0af734d4784ac122602b685bc561aabf340
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642063"
---
# <a name="deploy-to-macos-with-jamf"></a>Jamf による macOS への展開

この記事では、Jamf を使用して macOS 用に Microsoft Edge を展開する方法について説明します。

> [!NOTE]
> この記事は、Microsoft Edge version 77 以降に適用されます。

## <a name="prerequisites"></a>前提条件

Microsoft Edge を展開する前に、次の前提条件を満たしていることを確認してください。

- Microsoft Edge インストール ファイル (**MicrosoftEdgeDev-\<version\>.pkg**) が、ネットワーク上のアクセス可能な場所にあること。 Microsoft Edge Enterprise のインストール ファイルは、[Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)からダウンロードできます。
- インストール ファイルを作成してコンピューターに展開するために必要なレベルのアクセスと権限のある Jamf Cloud アカウントを持っていること。

## <a name="to-deploy-microsoft-edge-using-jamf"></a>Jamf を使用して Microsoft Edge を展開するには:

1. Jamf にサインオンし、**[All Settings]** (すべての設定) に移動します。

    ![すべての設定を開く](./media/mac-deploy/jamf-dash-main-open-settings.png)

2. **[All Settings]** (すべての設定) の **[Computer Management]** (コンピューターの管理) をクリックします。

    ![[Computer Management] (コンピュータの管理) の選択](./media/mac-deploy/jamf-all-settings-computer-mgmt.png)

3. **[Computer Management]** (コンピュータの管理) で、**[Packages]** (パッケージ) をクリックします。

    ![[Packages] (パッケージ) の選択](./media/mac-deploy/jamf-all-settings-computer-mgmt-pkgs.png)

4. **[Packages]** (パッケージ) ページで、**[+ New]** (新規) をクリックして、新しいパッケージを追加します。

    ![[New] (新規) を選択して新しいパートナーシップを追加する](./media/mac-deploy/jamf-all-settings-computer-mgmt-new-pkg.png)

5. **[New Package]** (新しいパッケージ) ページで、パッケージに関する詳細を入力し、**[Save]** (保存) をクリックします。 (たとえば、表示名、情報、メモなど)。

    ![[Save] (保存) を選択してパッケージ情報を保存する](./media/mac-deploy/jamf-all-settings-computer-mgmt-save-pkg-info.png)

6. メニュー バーの **[Computers]** (コンピューター) を選択し、ナビゲーション バーの **[Policies]** (ポリシー) を選択します。

7. **[+ New]** (新規) を選択して、**New Policy** (新しいポリシー) ウィンドウを表示します。

    ![[New] (新規) を選択して新しいポリシーを作成する](./media/mac-deploy/jamf-all-settings-computer-new-policy.png)

8. **[Options]** (オプション) タブの **[General]** (全般) を選択します。

    - **[DISPLAY NAME]** (表示名) に、ポリシーの表示名を入力します。
    - **[Trigger]** (トリガー) で、ポリシーをトリガーするイベントを選択します。 (下の例では、イベントは [Startup] (スタートアップ) です。)

    ![展開情報を入力する](./media/mac-deploy/jamf-all-settings-computer-cfg-policy.png)

9. **[Options]** (オプション) タブで、**[Packages]** (パッケージ) をクリックします。

10. **[Configure Packages]** (パッケージの構成) ポップアップで、**[Configure]** (構成) をクリックします。

    ![パッケージの構成](./media/mac-deploy/jamf-all-settings-computer-policy-pkg-configure.png)

11. 追加したパッケージが **[Packages]** (パッケージ) ウィンドウに表示されます。 **[Add]** (追加) をクリックします。 次のスクリーンショットで、この例のパッケージは "MicrosoftEdgeBeta" です。

    ![パッケージの追加](./media/mac-deploy/jamf-all-settings-computer-policy-pkg-add-beta.png)

12. **[New Policy]** (新しいポリシー) ページで、ドロップダウン リストを使用して、**[DISTRIBUTION POINT]** (配布ポイント) と、ポリシーについて実行する **[ACTION]** (アクション) を選択します。 **[Save]** (保存) をクリックします。 次のスクリーンショットでは、例として [Each computer's default distribution point] (各コンピューターの既定の配布ポイント) と [Install] (インストール) を使用しています。

    ![配布ポイントとアクションの選択](./media/mac-deploy/jamf-all-settings-computer-mgmt-pkg-cfg-distro.png)

13. **[New Policy]** 新しいポリシーページで、**[Scope]** (スコープ) タブを選択します。コンピューターまたはユーザーに基づいて、展開の範囲を管理できます。 この例では、**[TARGET COMPUTERS]** (ターゲット コンピューター) ドロップダウン リストから **[All Computers]** (すべてのコンピューター) を選択し、**[Save]** (保存) をクリックします。

    ![展開の範囲を選択する](./media/mac-deploy/jamf-all-settings-computer-mgmt-add-target.png)

14. この時点で、Microsoft Edge 展開ポリシーを確認できます。 展開オプションが要件を満たしている場合は、**[Done]** (完了) をクリックします。

    ![完了をクリックする](./media/mac-deploy/jamf-all-settings-computer-mgmt-finish-add-deployment.png)

    > [!NOTE]
    > いつでも展開ポリシーに戻って設定を変更できます。

お疲れさまでした。 これで、Jamf を使用して macOS 用に Microsoft Edge を展開するための構成が完了しました。 定義したトリガー条件に合致すると、指定したコンピューターにパッケージが展開されます。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Jamf.com](https://www.jamf.com/)
- [Jamf を Microsoft Intune と統合する](/intune/conditional-access-integrate-jamf)