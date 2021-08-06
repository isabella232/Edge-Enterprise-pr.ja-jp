---
title: System Center Configuration Manager を使用して Microsoft Edge を展開する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: System Center Configuration Manager (SCCM) を使用して Microsoft Edge を展開する方法について説明します。
ms.openlocfilehash: 0e3011178853a13562bd41a1f149975ab10317d07a48b5e19c3d6cf9d791a48e
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "11726514"
---
# <a name="deploy-microsoft-edge-using-system-center-configuration-manager"></a>System Center Configuration Manager を使用して Microsoft Edge を展開する

この記事では、System Center Configuration Manager (SCCM) を使用して Microsoft Edge の展開を自動化する方法について説明します。

>[!NOTE]
>この記事は、Microsoft Edge version 77 以降に適用されます。

## <a name="before-you-begin"></a>開始する前に

「[Configuration Manager でのアプリケーション管理の概要](/sccm/apps/understand/introduction-to-application-management)」の情報をご確認ください。 アプリケーション管理に関する記事は、、サイトでアプリケーションのインストールを準備するためのガイドであり、この記事で使用する用語の理解に役立ちます。

[Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)から、Microsoft Edge Enterprise インストール ファイル (**MicrosoftEdgeDevEnterpriseX64.msi**、**MicrosoftEdgeDevEnterpriseX86.msi**) をダウンロードします。

Microsoft Edge インストール ファイルは、ネットワーク上のアクセス可能な場所に保存してください。

## <a name="create-the-application"></a>アプリケーションを作成する

Configuration Manager ウィザードを使用してアプリケーションを作成します。

### <a name="start-the-create-application-wizard-and-create-the-application"></a>アプリケーションの作成ウィザードを起動してアプリケーションを作成する  

1. Configuration Manager コンソールで、**[ソフトウェア ライブラリ]** > **[アプリケーション管理]** > **[アプリケーション]** の順にクリックします。  

2. **[ホーム]** タブの **[作成]** グループで、**[アプリケーションの作成]** をクリックします。 または、ナビゲーション バーで **[アプリケーション]** を右クリックし、**[アプリケーションの作成]** をクリックします。

    ![アプリケーションの作成](./media/edge-ent-deployment-sccm/edge-ent-create-app-1.png)

3. **アプリケーションの作成ウィザード**の **[全般]** ページで、**[このアプリケーションの情報をインストール ファイルから自動的に検出する]** を選択します。 これにより、インストール用 .msi ファイルから抽出された情報を使用して、ウィザードに情報の一部が事前入力されます。 次の情報を指定します。  

   - **種類**: **[Windows インストーラー (\*.msi ファイル)]** を選択します。  

   - **場所**: インストール ファイル **MicrosoftEdgeDevEnterpriseX64.msi** または **MicrosoftEdgeDevEnterpriseX86.msi** の場所を入力 (または、**[参照]** をクリックして場所を選択) します。 Configuration Manager にインストール ファイルを指定するには、場所を *\\\Server\Share\File* の形式で指定する必要があります。  

   **[このアプリケーションの設定の指定]** ページは、次の例のようになります。  

    ![このアプリケーションの設定の指定](./media/edge-ent-deployment-sccm/edge-ent-create-app-2.png)

4. **[次へ]** をクリックします。 **[インポートした情報の表示]** ページの **[詳細] ** に、アプリケーションおよびインポートされた関連ファイルに関する情報が表示されます。 **[次へ]** をクリックして、ウィザードを続行します。  

    ![インポートした情報の表示](./media/edge-ent-deployment-sccm/edge-ent-create-app-3.png)

5. **[一般情報]** ページでは、アプリケーションに関する詳細情報を追加できます。 たとえば、ソフトウェアのバージョン、管理者のコメント、発行元などです。 この情報をに使用すると、Configuration Manager コンソールでアプリケーションを分類または検索する際に役立ちます。

   **[インストール プログラム]** フィールドを使用して、PC にアプリケーションをインストールするために使用する完全なコマンド ラインを指定することもできます。 これを編集して、独自のプロパティ (たとえば、無人インストール用の **/q** など) を追加できます。

   次のスクリーンショットは、**[このアプリケーションの情報の指定]** フィールドの使用例を示しています。

   ![アプリケーションのメタデータの指定](./media/edge-ent-deployment-sccm/edge-ent-create-app-5.png)

6. **[次へ]** をクリックします。
7. **[概要]** ページの **[詳細]** でアプリケーションの設定を確認して、ウィザードの使用を終了できます。 **[次へ]** をクリックします。  

    ![アプリケーション設定の詳細](./media/edge-ent-deployment-sccm/edge-ent-create-app-6.png)

8. **[完了]** ページで、**[閉じる]** をクリックします。

    ![成功ダイアログ](./media/edge-ent-deployment-sccm/edge-ent-create-app-7.png)

アプリケーションの作成が完了しました。 Configuration Manager に表示するには、次の手順を実行します。

- **[ソフトウェア ライブラリ]** ワークスペースを選択します。
- **[アプリケーション管理]** を展開します。
- **[アプリケーション]** をクリックします。

次のスクリーンショットは、この記事で使用した例を示しています。  

![アプリケーション](./media/edge-ent-deployment-sccm/edge-ent-create-app-8.png)

## <a name="change-application-properties-and-deployment-settings"></a>アプリケーションのプロパティと展開の設定を変更する

アプリケーションを作成した後、必要に応じてアプリケーションの設定を調整できます。 アプリケーションのプロパティを確認するには:

- アプリケーションを選択します。
- **[ホーム]**>**[プロパティ]** の **[プロパティ]** をクリックします。  

   ![アプリケーションのプロパティを構成する](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-1.png)

 **[<アプリケーション名\> アプリケーションのプロパティ]** ダイアログ ページには、アプリケーションの動作を変更するために構成できる項目のタブ付きのビューが表示されます。 構成可能な設定について詳しくは、[アプリケーションの作成に関するページ](/sccm/apps/deploy-use/create-applications)をご覧ください。

この例では、アプリケーションの展開の種類のプロパティをいくつか変更します。 展開のプロパティを変更するには:

1. **[展開の種類]** タブをクリックします。
2. **[展開の種類]** で、アプリケーションの **[名前]** を選択します。
3. **[編集]** をクリックします。

   ![展開の種類を編集する](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-2.png)

### <a name="add-a-requirement-to-the-deployment-type"></a>展開の種類に要件を追加する

 要件には、デバイスにアプリケーションをインストールする前に満たす必要がある条件を指定します。 組み込みの要件から選択することも、独自の要件を作成することもできます。 たとえば、インストール ファイルのターゲット プロセッサ アーキテクチャに応じて、Windows 10 **x86** または **x64** を実行している PC にのみアプリケーションがインストールされるという要件を追加できます。 この例では Windows 10 **x86** を指定します。

1. 開いた展開の種類のプロパティ ページで、**[要件]** タブをクリックします。

2. **[追加]** をクリックし、**[要件の作成]** ダイアログを開きます。

    ![要件の作成](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-3.png)

3. **[要件の作成]** ダイアログ ボックスで、次の項目を指定します。

    - **カテゴリ**: **デバイス**  

    - **条件**: **オペレーティング システム**  

    - **規則の種類**: **値**  

    - **演算子**: **次のいずれか**  

    - オペレーティング システムの一覧から、**[Windows 10]** > **[すべての Windows 10 (32 ビット)]** を選択します。  

    完了すると、ダイアログは次のスクリーンショット例のようになります。

    ![要件を追加する](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-4.png)

4. **[OK]** をクリックして、開いている各プロパティ ページを閉じ、Configuration Manager コンソールの **[アプリケーション]** 一覧に戻ります。  

## <a name="add-the-application-content-to-a-distribution-point"></a>アプリケーション コンテンツを配布ポイントに追加する  

更新されたアプリケーションを PC に展開するには、アプリケーションのコンテンツが配布ポイントにコピーされていることを確認してください。 PC は、配布ポイントにアクセスしてアプリケーションをインストールします。  

>[!TIP]
>Configuration Manager の配布ポイントとコンテンツ管理について詳しくは、 「[System Center Configuration Manager でのコンテンツの展開および管理](/sccm/core/servers/deploy/configure/deploy-and-manage-content)」をご覧ください。  

1. Configuration Manager コンソールで、**[ソフトウェア ライブラリ]** をクリックします。  

2. **[ソフトウェア ライブラリ]** ワークスペースで **[アプリケーション]** を展開します。 アプリケーションの一覧から、作成したアプリケーションを選択します。

3. **[ホーム]** タブの **[展開]** グループで、**[コンテンツの配布]** をクリックします。  

4. **コンテンツの配布ウィザード**の **[全般]** ページで、アプリケーションの名前が正しいことを確認し、**[次へ]** をクリックします。  

5. **[コンテンツ]** ページで、配布ポイントにコピーされる情報を確認し、**[次へ]** をクリックします。  

6. **[コンテンツの配布先]** ページで **[追加]** をクリックし、アプリケーション コンテンツのインストール先として 1 つ以上のコレクション、配布ポイント、または配布ポイント グループを選択します。

7. ウィザードを完了します。

アプリケーション コンテンツが配布ポイントに正しくコピーされたかどうかを確認するには、**[監視]** ワークスペースの **[配布ステータス]** > **[コンテンツのステータス]** に移動します。  

## <a name="deploy-the-application"></a>アプリケーションを展開する  

次に、階層内のデバイス コレクションにアプリケーションを展開します。 この例では、アプリケーションを **[すべてのシステム]** デバイス コレクションに展開します。  

>[!TIP]
>前の手順で選択した要件により、指定されたプロセッサ アーキテクチャの Windows 10 コンピューターのみでアプリケーションがインストールされることに注意してください。  

1. Configuration Manager コンソールで、**[ソフトウェア ライブラリ]** > **[アプリケーション管理]** > **[アプリケーション]** の順にクリックします。

2. アプリケーションの一覧から、既に作成したアプリケーションを選択します。 次に、**[ホーム]** タブの **[展開]** グループで **[展開]** をクリックするか、アプリケーションを右クリックして **[展開]** を選択します。

    ![アプリケーションを展開する](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-1.png)

3. **ソフトウェアの展開ウィザード**の **[全般]** ページで **[参照]** をクリックし、アプリケーションの展開先としてデバイス コレクションを選択します。

    ![インストール ファイルを参照する](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-2.png)

4. **[コンテンツ]** ページで、PC からアプリケーションをインストールする際に使用する配布ポイントが選択されていることを確認します。

    ![配布ポイントを指定する](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-6.png)

5. **[展開設定]** ページで、展開アクションが **[インストール]** に設定され、展開の目的が **[必須]** に設定されていることを確認します。

    ![展開設定を構成する](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-8.png)

    >[!TIP]
    >展開の目的を **[必須]** に設定すると、設定した要件を満たす PC にアプリケーションがインストールされるようになります。 この値を **[使用可能]** に設定した場合、ユーザーはソフトウェア センターから必要に応じてアプリケーションをインストールできます。  

6. **[スケジュール]** ページでは、アプリケーションをいつインストールするかを構成できます。 この例では、**[使用可能な時間後直ちに]** を選択します。

    ![展開のスケジュール設定](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-9.png)

7. **[ユーザー エクスペリエンス]** ページで、ニーズに応じた値を選択し、**[次へ]** をクリックします。

    ![ユーザー エクスペリエンスを指定する](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-10.png)

8. ニーズに応じたアラート オプションを指定し、**[次へ]** をクリックします。

    ![アラート設定を指定する](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-11.png)

9. ウィザードを完了します。

アプリケーションの展開の状態を確認するには、次の「**アプリケーションを監視する**」セクションの情報を使用します。  

## <a name="monitor-the-application"></a>アプリケーションを監視する

 このセクションでは、展開したアプリケーションの展開状態を簡単に確認します。  

### <a name="to-review-the-deployment-status"></a>展開状態を確認するには  

1. Configuration Manager コンソールで、 **[監視]** > **[展開]** をクリックします。  

2. 展開の一覧から、アプリケーションを選択します。

    ![展開を監視する](./media/edge-ent-deployment-sccm/edge-ent-monitor-deployment.png)

3. **[ホーム]** タブの **[展開]** グループで、**[ステータスの表示]** をクリックします。  

4. 次のいずれかのタブを選択して、アプリケーションの展開に関する状態の最新情報を確認します。  

    - **成功**: 指定された PC にアプリケーションが正常にインストールされました。  

    - **処理中**: アプリケーションのインストールはまだ完了していません。  

    - **エラー**: 指定された PC にアプリケーションをインストール中にエラーが発生しました。 エラーに関する詳細情報も表示されます。  

    - **要件が満たされていません**: 構成された要件を満たしていないため、指定のデバイスでインストールが行われませんでした (この例では、指定のデバイスで Windows 10 が実行されていないため)。

    - **不明**: Configuration Manager は、展開の状態を報告できませんでした。 後でもう一度確認してしてください。  

    >[!TIP]
    >アプリケーションの展開を監視するには、複数の方法があります。 詳しくは、「[System Center Configuration Manager コンソールからアプリケーションを監視する](/sccm/apps/deploy-use/monitor-applications-from-the-console)」をご覧ください。  

## <a name="end-user-experience"></a>エンドユーザー エクスペリエンス  

Configuration Manager によって管理され、指定されたプロセッサ アーキテクチャの Windows 10 を実行する PC を使用しているユーザーには、Microsoft Edge Dev アプリケーションをインストールする必要があることを示すメッセージが表示されます。 このインストール オプションを受け入れると、アプリケーションがインストールされます。  

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [System Center Configuration Manager でアプリケーションを作成および展開する](/sccm/apps/get-started/create-and-deploy-an-application)