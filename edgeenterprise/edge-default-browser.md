---
title: Windows および macOS で Microsoft Edge を既定のブラウザーとして設定する
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 1/15/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge を既定のブラウザーとして設定する方法について説明します
ms.openlocfilehash: 9151294c34cb2252a7fb32e660c1e3d9e64b5f76
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447761"
---
# <a name="set-microsoft-edge-as-the-default-browser"></a>Microsoft Edge を既定のブラウザーとして設定する

この記事では、Windows および macOS で Microsoft Edge を既定のブラウザーとして設定する方法について説明します。

> [!NOTE]
> この記事は、Windows 8 および Windows 10 の Microsoft Edge version 77 以降に適用されます。 Windows 7 および macOS の場合は、「[Microsoft Edge を既定のブラウザーとして設定する](./microsoft-edge-policies.md#defaultbrowsersettingenabled)」のポリシーをご覧ください。

## <a name="introduction"></a>はじめに

Microsoft Edge を組織の既定ブラウザーとして設定するには、**[既定の関連付け構成ファイルの設定]** グループ ポリシーまたは [DefaultAssociationsConfiguration](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) モバイル デバイス管理設定を使用します。

html ファイル、http/https リンク、および PDF ファイル用の既定ブラウザーとして Microsoft Edge Stable を設定するには、次のアプリケーション関連付けファイルの例を使用します。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<DefaultAssociations> 
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".html"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".htm"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="http"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="https"/>  
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgePDF" Identifier=".pdf"/>
</DefaultAssociations>
```

> [!NOTE]
> Microsoft Edge Beta を既定ブラウザーとして設定するには、**ApplicationName** を "Microsoft Edge Beta"、**ProgId** を "MSEdgeBHTML" に設定します。 Microsoft Edge Dev を既定ブラウザーとして設定するには、**ApplicationName** を "Microsoft Edge Dev"、**ProgId** を "MSEdgeDHTML" に設定します。


> [!NOTE]
> ターゲット デバイスに Microsoft Edge がインストールされていない場合、既定のファイル関連付けは適用されません。 このシナリオでは、ユーザーがリンクまたは htm/html ファイルを開くときに、既定のアプリケーションを選択するように求められます。

## <a name="set-microsoft-edge-as-the-default-browser-on-domain-joined-devices"></a>ドメインに参加しているデバイスで Microsoft Edge を既定のブラウザーとして設定する

ドメインに参加しているデバイスで Microsoft Edge を既定のブラウザーとして設定するには、**[既定の関連付け構成ファイルの設定]** グループ ポリシーを構成します。 このグループ ポリシーを有効にした場合は、既定の関連付け構成ファイルを作成し、保存する必要があります。 このファイルは、ローカルまたはネットワーク共有に保存されます。 このファイルの作成方法について詳しくは、「[既定のアプリケーションの関連付けのエクスポートまたはインポート](/windows-hardware/manufacture/desktop/export-or-import-default-application-associations)」をご覧ください。

### <a name="to-configure-the-group-policy-for-a-default-file-type-and-protocol-associations-configuration-file"></a>ファイルの種類とプロトコルの既定の関連付け構成ファイルに関するグループ ポリシーを構成するには:

1. グループ ポリシー エディターを開き、**[コンピューターの構成]\[管理用テンプレート]\[Windows コンポーネント]\[エクスプローラー]** の順に移動します。
2. **[既定の関連付け構成ファイルの設定]** を選択します。
3. **[ポリシー設定]** をクリックしてから、**[有効]** をクリックします。
4. **[オプション]** で、既定の関連付け構成ファイルの場所を入力します。
5. **[OK]** をクリックして、ポリシー設定を保存します。

次のスクリーンショットの例は、ターゲット デバイスからアクセス可能なネットワーク共有にある *appassoc.xml* という関連付けファイルを示しています。

   ![グループ ポリシーでファイルの関連付けを有効にする](./media/edge-learnmore-make-edge-default-browser/edge-learnmore-app-associations.png)

   > [!NOTE]
   > この設定が有効で、ユーザーのデバイスがドメインに参加している場合は、次回ユーザーがサインオンすると関連付け構成ファイルが処理されます。

## <a name="set-microsoft-edge-as-the-default-browser-on-azure-active-directory-joined-devices"></a>Azure Active Directory に参加しているデバイスで Microsoft Edge を既定のブラウザーとして設定する

Azure Active Directory に参加しているデバイスで Microsoft Edge を既定のブラウザーとして設定するには、例として次のアプリケーション関連付けファイルを使用して、[DefaultAssociationsConfiguration](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) モバイル デバイス管理設定の手順に従います。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<DefaultAssociations>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".html"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".htm"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="http"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="https"/>  
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgePDF" Identifier=".pdf"/>
</DefaultAssociations>
```

> [!NOTE]
> Microsoft Edge Beta を既定ブラウザーとして設定するには、**ApplicationName** を "Microsoft Edge Beta"、**ProgId** を "MSEdgeBHTML" に設定します。 Microsoft Edge Dev を既定ブラウザーとして設定するには、**ApplicationName** を "Microsoft Edge Dev"、**ProgId** を "MSEdgeDHTML" に設定します。

## <a name="set-microsoft-edge-as-the-default-browser-on-macos"></a>macOS で Microsoft Edge を既定のブラウザーとして設定する

macOS でプログラムによって既定のブラウザーを設定しようとすると、エンド ユーザーに対してプロンプトが表示されます。 このプロンプトは、AppleScript によってのみ自動化できる macOS のセキュリティ機能です。

この制限により、macOS で Microsoft Edge を既定のブラウザーとして設定するための主要な方法は 2 つあります。 最初の方法は、Microsoft Edge が既に既定のブラウザーとして設定されている macOS のイメージを使用してデバイスをフラッシュする方法です。 もう 1 つの方法は、 [Microsoft Edge を既定のブラウザーとして設定する](./microsoft-edge-policies.md#defaultbrowsersettingenabled) ポリシーを使用する方法です。このポリシーでは、ユーザーに対して Microsoft Edge を既定のブラウザーとして設定するように求めます。

どちらの方法を使用する場合でも、ユーザーは既定のブラウザーを変更できます。 これは、既定のブラウザーの設定をプログラムではブロックできないというセキュリティ上の理由によります。 このため、Microsoft Edge が既定のブラウザーとして設定されているイメージを作成する場合でも、**Microsoft Edge を既定のブラウザーとして設定する** ポリシー展開することをお勧めします。 このポリシーが設定されている場合、次回 Microsoft Edge を開いたときに、ユーザーが Microsoft Edge から既定のブラウザーを変更すると、Microsoft Edge を既定として設定するように求められます。

## <a name="see-also"></a>関連項目

- [Microsoft Edge の展開を計画する](./deploy-edge-plan-deployment.md)
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge を既定のブラウザーとして設定する (Windows 7、macOS)](./microsoft-edge-policies.md#defaultbrowsersettingenabled)
- [Windows 10 – ファイルの関連付けを構成する方法 (IT 担当者向け)](/archive/blogs/windowsinternals/windows-10-how-to-configure-file-associations-for-it-pros)
- [既定のアプリケーションの関連付けのエクスポートまたはインポート](/windows-hardware/manufacture/desktop/export-or-import-default-application-associations)
  - [DISM の概要](/windows-hardware/manufacture/desktop/what-is-dism)
  - [DISM - 展開イメージのサービスと管理](/windows-hardware/manufacture/desktop/dism---deployment-image-servicing-and-management-technical-reference-for-windows)