---
title: Windows 用に Microsoft Edge を構成する
ms.author: brianalt
author: kelleyvice-msft
manager: laurawi
ms.date: 06/28/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Windows デバイスで Microsoft Edge ポリシー設定を構成する
ms.openlocfilehash: a962a42c8dc40589c9275625007827ec2f76450002115a0c6d8c9e2d733df2e8
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "11725258"
---
# <a name="configure-microsoft-edge-policy-settings-on-windows"></a>Windows で Microsoft Edge ポリシー設定を構成する

Windows デバイスで Microsoft Edge ポリシー設定を構成するには、次の情報を参照してください。

> [!NOTE]
> この記事は、Microsoft Edge version 77 以降に適用されます。

## <a name="configure-policy-settings-on-windows"></a>Windows でポリシー設定を構成する

Windows のすべてのバージョンで Microsoft Edge および管理された Microsoft Edge 更新プログラムのポリシー設定を構成するには、_グループ ポリシー オブジェクト (GPO)_ を使用できます。 また、Microsoft Active Directory ドメインに参加している Windows デバイスのレジストリか、Microsoft Intune でデバイス管理用に登録されている Windows 10 Pro または Enterprise インスタンスを通じて、ポリシーをプロビジョニングすることもできます。 グループ ポリシー オブジェクトを使用して Microsoft Edge を構成するには、Active Directory ドメイン内のグループ ポリシー中央ストアまたは各コンピューター上のポリシー定義テンプレート フォルダーに Microsoft Edge の規則と設定を追加するための_管理用テンプレート_をインストールし、設定する特定のポリシーを構成します。

ドメイン レベルでポリシーを管理する場合は、Active Directory グループ ポリシーを使用して Microsoft Edge ポリシー設定を構成できます。 これにより、ポリシー設定をグローバルに管理することも、特定の OU に対して異なるポリシー設定を適用することもできます。また、WMI フィルターを使用して、特定のクエリによって返されたユーザーまたはコンピューターにのみ設定を適用することもできます。 個々のコンピューターでポリシーを構成する場合は、ターゲット コンピューターのローカル グループ ポリシー エディターを使用して、ローカル デバイスのみに影響するポリシー設定を適用できます。

Microsoft Edge では、_必須_および_推奨_のポリシーがどちらもサポートされています。 必須ポリシーはユーザー基本設定を上書きし、ユーザーによる変更ができません。推奨ポリシーは既定の設定を提供し、ユーザーはこれを上書きできます。 ほとんどのポリシーは必須のみです。サブセットは必須または推奨です。 両方のバージョンのポリシーが設定されている場合は、必須の設定が優先されます。 推奨ポリシーは、ユーザーが設定を変更していない場合にのみ有効になります。

>[!TIP]
> Microsoft Edge ポリシー設定は、Microsoft Intune を使用して構成できます。 詳しくは、「[Microsoft Intune を使用して Microsoft Edge を構成する](configure-edge-with-intune.md)」をご覧ください。

Microsoft Edge には 2 つの管理用テンプレートがあり、どちらもコンピューターまたは Active Directory ドメインのレベルで適用できます。

- *msedge.admx*: [Microsoft Edge 設定を構成する](microsoft-edge-policies.md)場合に使用。
- *msedgeupdate.admx*: [manage Microsoft Edge 更新プログラムを管理する](microsoft-edge-update-policies.md)場合に使用。

開始するには、Microsoft Edge 管理用テンプレートをダウンロードしてインストールします。

### <a name="1-download-and-install-the-microsoft-edge-administrative-template"></a>1. Microsoft Edge 管理用テンプレートをダウンロードしてインストールする

Active Directory で Microsoft Edge ポリシー設定を構成する場合は、リモートサーバー管理ツール (RSAT) がインストールされているドメイン コントローラーまたはワークステーションからアクセスできるネットワーク上の場所にファイルをダウンロードします。 個々のコンピューターで構成を行う場合は、そのコンピューターにファイルをダウンロードします。

管理用テンプレート ファイルを適切な場所に追加すると、グループ ポリシー エディターで Microsoft Edge ポリシー設定をすぐに使用できるようになります。

[Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)に移動して、Microsoft Edge ポリシー テンプレートフ ァイル (*MicrosoftEdgePolicyTemplates.cab*) をダウンロードし、内容を展開します。

#### <a name="add-the-administrative-template-to-active-directory"></a>管理用テンプレートを Active Directory に追加する

1. RSAT がインストールされているドメイン コントローラーまたはワークステーションで、ドメインの任意のドメイン コントローラー上 **PolicyDefinition** フォルダー (_中央ストア_とも呼ばれます) を参照します。 以前のバージョンの Windows Server では、PolicyDefinition フォルダーの作成が必要になる場合があります。 詳しくは、「[Windows でグループ ポリシー管理用テンプレート用のセントラル ストアを作成および管理する方法](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)」をご覧ください。
2. *MicrosoftEdgePolicyTemplates* を開き、**windows** > **admx** に移動します。
3. *msedge.admx* ファイルを PolicyDefinition フォルダーにコピーします。 (例: %systemroot%\sysvol\domain\policies\PolicyDefinitions)
4. *admx* フォルダーで、適切な言語フォルダーを開きます。 たとえば米国内にいる場合は、**en-US** フォルダーを開きます。
5. PolicyDefinition フォルダー内にある、一致する言語のフォルダーに、*msedge.adml* ファイルをコピーします。 フォルダーが存在しない場合は作成します。 (例: %systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US)
6. ドメインに複数のドメイン コントローラーがある場合、新しい ADMX ファイルは、次回のドメイン レプリケーション時にレプリケートされます。
7. ファイルが正しく読み込まれたことを確認するには、Windows 管理ツールで**グループ ポリシー管理エディター**を開き、**[コンピューターの構成]** > **[ポリシー]** > **[管理用テンプレート]** > **[Microsoft Edge]** の順に展開します。 次の図のように、1 つ以上の Microsoft Edge ノードが表示されます。

    ![Microsoft Edge ポリシー](./media/configure-microsoft-edge/edge-gpo-policies.png)

#### <a name="add-the-administrative-template-to-an-individual-computer"></a>管理用テンプレートを個々のコンピューターに追加する

1. ターゲット コンピューターで、*MicrosoftEdgePolicyTemplates* を開き、**windows** > **admx** に移動します。
2. *msedge.admx* ファイルをポリシー定義テンプレート フォルダーにコピーします。 (例: C:\Windows\PolicyDefinitions)
3. *admx* フォルダーで、適切な言語フォルダーを開きます。 たとえば米国内にいる場合は、**en-US** フォルダーを開きます。
4. ポリシー定義フォルダー内にある、一致する言語のフォルダーに、*msedge.adml* ファイルをコピーします。 (例: C:\Windows\PolicyDefinitions\en-US)
5. ファイルが正しく読み込まれたことを確認するには、直接ローカル グループ ポリシー エディターを開くか (Windows キー + R を押して「gpedit.msc」と入力します)、MMC を開いてローカル グループ ポリシー エディター スナップインを読み込みます。 エラーが発生した場合は通常、ファイルの場所が正しくないことが原因です。

### <a name="2-set-mandatory-or-recommended-policies"></a>2. 必須または推奨のポリシーを設定する

Active Directory の場合も個々のコンピューターの場合も、グループ ポリシー エディターを使用して、必須または推奨のポリシーを設定して Microsoft Edge を構成できます。 次の説明に従って適切なノードを選択することによって、ポリシー設定のスコープを **[コンピューターの構成]** または **[ユーザーの構成]** に指定できます。

- 必須ポリシーを構成するには、グループ ポリシー エディターを開き、(**[コンピューターの構成]** または **[ユーザーの構成]**) > **[ポリシー]** > **[管理用テンプレート]** > **[Microsoft Edge]** に移動します。
- 推奨ポリシーを構成するには、グループ ポリシー エディターを開き、(**[コンピューターの構成]** または **[ユーザーの構成]**) > **[ポリシー]** > **[管理用テンプレート]** > **[Microsoft Edge – 規定の設定 (ユーザーはオーバーライドできます)]** に移動します。

  ![グループ ポリシー エディターを開きます。](./media/configure-microsoft-edge/edge-ad-policy.png)

### <a name="3-test-your-policies"></a>3. ポリシーをテストする

対象のクライアント デバイスで、Microsoft Edge を開き、**edge://policy** に移動して、適用されているすべてのポリシーを表示します。 ポリシー設定をローカル コンピューターに適用した場合は、ポリシーがすぐに表示されます。 ポリシー設定の構成時に Microsoft Edge を開いていた場合は、一度閉じてから再度開く必要があります。

![ブラウザーで構成済みのポリシーの確認](./media/configure-microsoft-edge/edge-gpEdit.png)

Active Directory グループ ポリシー設定では、ドメイン管理者によって定義された一定の間隔でポリシー設定がドメイン コンピューターに伝達され、ターゲット コンピューターには、すぐにポリシーの更新が届かない場合があります。 ターゲット コンピューターの Active Directory グループ ポリシー設定を手動で更新するには、ターゲット コンピューターのコマンド プロンプトまたは PowerShell セッションから次のコマンドを実行します。

``` powershell
gpupdate /force
```

新しいポリシーを表示するには、Microsoft Edge を閉じてから再度開く必要があります。

ターゲット コンピューターで REGEDIT.exe を使用して、グループ ポリシー設定を保存するレジストリ設定を表示することもできます。 これらの設定は、レジストリ パス **HKLM\SOFTWARE\Policies\Microsoft\Edge** にあります。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Intune で Windows 用に構成する](configure-edge-with-intune.md)
- [macOS 用に構成する](configure-microsoft-edge-on-mac.md)
- [Microsoft Edge エンタープライズ ポリシーを参照する](microsoft-edge-policies.md)


