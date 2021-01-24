---
title: Microsoft Edge キオスク モードを構成する
ms.author: aguta
author: aguta
manager: srugh
ms.date: 01/21/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge キオスク モードを構成する
ms.openlocfilehash: be353a0e13e9234de40296a2e8dcc31b1b800f52
ms.sourcegitcommit: 8a88fd38bdb5e132e89bf17dd2b5fb72f5d1b4b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "11297473"
---
# Microsoft Edge キオスク モードを構成する

この記事では、パイロットを実行することができる Microsoft Edge キオスク モードのオプションを構成する方法について説明します。 また、対象としている機能のロードマップも含まれます。

> [!NOTE]
> この記事は Microsoft Edge version 87 以降に適用されます。

## 概要

Microsoft Edge キオスク モードは、ブラウザーの 2 つのロックダウン エクスペリエンスを提供し、組織が顧客に最高のエクスペリエンスを作成し、管理し、提供できるようにします。 次のロックダウン エクスペリエンスを利用できます。  

- **デジタル/対話型サイネージ** エクスペリエンスでは、全画面表示モードで特定のサイトを表示します。
- **パブリック ブラウジング** エクスペリエンスでは、Microsoft Edge の限定的な複数タブのバージョンを実行します。

どちらのエクスペリエンスでも、ユーザー データを保護する Microsoft Edge InPrivate セッションを実行します。

## Microsoft Edge キオスク モードのセットアップ

キオスク モード機能の初期セットが Microsoft Edge Canary チャネルのバージョン 87 でテストに使用できるようになりました。 [Microsoft Edge (Official Stable チャネル)](https://www.microsoft.com/edge) から 最新バージョンをダウンロードできます。

### キオスク モードでサポートされる機能

次の表に、キオスク モードでサポートされている機能を示します。

|機能|デジタル/対話型サイネージ|パブリック ブラウジング|Microsoft Edge のバージョン (以上) で利用可能|
|-|-|-|-|
|InPrivate ナビゲーション。|Y|Y|87|
|非アクティブ時のリセット|Y|Y|87|
|[読み取り専用アドレス バー](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) (ポリシー) |N|Y |87|
|[終了時にダウンロードを削除する](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit) (ポリシー)  | Y|Y |87|
|F11 がブロックされています (全画面に入る/終了する) | Y | Y | 87 |
|F12 がブロックされています (開発者ツールの起動) | Y | Y | 87 |
| 複数タブのサポート | N| Y| 87|
|[セッションの終了] ボタン | N| Y| 88|
|すべての内部 Microsoft Edge URL はブロックされます (ただし、*edge://downloads* および *edge://print*以外) |N|Y|88|
| Ctrl + N がブロックされています (新しいウィンドウを開く) | Y | Y | 89 |
| Ctrl + T ブロックされています (新しいタブを開く) | N | Y | 89 |
|設定と詳細 (...) では、必要なオプションだけが表示されます。  |N |Y |89 |

> [!NOTE]
> キオスク モードの進化に伴い、より多くの機能を使用できるようになります。

## キオスク モードの機能を使用する

Microsoft Edge キオスク モードの機能は、Windows 10 の次のコマンド ライン オプションで起動できます。

- キオスク モードのデジタル/対話型サイネージ: `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen`
- キオスク モードのパブリック ブラウジング: `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing`

### その他のコマンド ライン オプション

- `--no-first-run` : Microsoft Edge の最初の実行エクスペリエンスを無効にします。
- `--kiosk-idle-timeout-minutes` : Microsoft Edge キオスク モードでユーザーのセッションがリセットされる前に、最後のユーザー アクティビティから時間 (分単位) を変更します。 次の値がサポートされています。

  - 既定値
    - 全画面表示 - オフ
    - パブリック ブラウジング - 5 分
  - 指定可能な値
    - 0 - タイマーをオフにします
    - 1 - 1440 分 (アイドル タイマー時のリセット)

## キオスク モードでサポートされているポリシー

以下の表にある Microsoft Edge ポリシーのいずれかを使用して、構成する Microsoft Edge キオスク モードの種類に応じてキオスク エクスペリエンスを強化します。 これらのポリシーの詳細については、「[Microsoft Edge - ブラウザー ポリシー リファレンス](https://docs.microsoft.com/deployedge/microsoft-edge-policies)」を参照してください。

> [!NOTE]
> ポリシーの構成は、次の表に示すポリシーに限定されませんが、キオスク モード機能に悪影響が及びないことを確認するために、追加のポリシーをテストする必要があります。

|グループ ポリシー|デジタル/対話型サイネージ|パブリック ブラウズの単一アプリ|
|--|--|--|
|[印刷](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printing-policies) | Y|Y |
|[HomePageLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#homepagelocation) |N | Y|
|[ShowHomeButton](https://docs.microsoft.com/deployedge/microsoft-edge-policies#showhomebutton) |N | Y|
|[NewTabPageLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagelocation) |N |Y |
|[FavoritesBarEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#favoritesbarenabled) |N |Y |
|[URLAllowlist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlallowlist) |Y |Y |
|[URLBlocklist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlblocklist) |Y | Y|
|[ManagedSearchEngines](https://docs.microsoft.com/deployedge/microsoft-edge-policies#managedsearchengines) |N | Y|
|[UserFeedbackAllowed](https://docs.microsoft.com/deployedge/microsoft-edge-policies#userfeedbackallowed) |N | Y|
|[VerticalTabsAllowed](https://docs.microsoft.com/deployedge/microsoft-edge-policies#verticaltabsallowed) | N|Y |
|[SmartScreen の設定](https://docs.microsoft.com/deployedge/microsoft-edge-policies#smartscreen-settings-policies) |Y |Y |

## 割り当てられたアクセスによる Microsoft Edge の使用

### シングル アプリ キオスク

Microsoft Edge は現在、次のロックダウン エクスペリエンス、つまりデジタル/対話型サイネージ、およびパブリックブラウジングを備えた、単一アプリに割り当てられたアクセス用の同じ Microsoft Edge レガシ キオスク モード タイプのサブセットをサポートしています。  

現在、割り当てられたアクセスによるキオスク モードは、最新の  [Windows 10 Insider Preview ビルド](https://insider.windows.com/) (バージョン 20215 以降) と  [Microsoft Edge Dev チャネル](https://www.microsoftedgeinsider.com/download) (バージョン 87.0.644.4 以降) でテストに使用できます。

**Windows Insiders Preview を入手するにはどうすればよいですか?**

PC に Windows 10 Insider Preview ビルドをインストールするには、「 [Windows 10 Insider Preview ビルドの概要](https://docs.microsoft.com/windows-insider/get-started)」の指示に従います。

### 複数アプリ キオスク

Microsoft Edge は、Windows 10 で[複数アプリの割り当てられたアクセス](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) によって実行できます。これは Microsoft Edge レガシでの "通常の閲覧" タイプのキオスク モードに相当します。 複数アプリの割り当てられたアクセスで Microsoft Edge を構成するには、[複数アプリ キオスクの設定](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)方法の手順に従います。 (Microsoft Edge Stable チャネルの AUMID は **MSEdge** です)。

複数アプリが割り当てられたアクセスで Microsoft Edge を使用する場合は、Microsoft Edge キオスクを構成するには、[Microsoft Edge ブラウザー ポリシー](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies) を使用して、固有の要件を満たすように閲覧エクスペリエンスを構成します。

### Windows の設定を使用して構成する

Windows の設定は、1 つか 2 つのシングル アプリのキオスク デバイスを設定する最も簡単な方法です。 シングル アプリのキオスク コンピューターをセットアップするには、次の手順に従います。

1. 最新の Windows 10 Insider Preview (バージョン 20215 以降) をインストールします。 「[Windows 10 Insider Preview ビルドの概要](https://docs.microsoft.com/windows-insider/get-started)」の指示に従います。
2. [Microsoft Edge Stableチャネル](https://www.microsoft.com/edge)、バージョン 87 以上の最新バージョンをインストールします。  最新の機能をテストするには、最新の [Microsoft Edge 開発チャネル](https://www.microsoftedgeinsider.com/download) (バージョン 89 以上) をダウンロードできます。

   > [!IMPORTANT]
   > デバイス レベルのインストールが必要であるため、Canary 以外のチャネルのみがサポートされています。

3. キオスク コンピューターで、[Windows の設定] を開き、検索フィールドに "キオスク" と入力します。 次のスクリーンショットに表示されている  **[Set up a kiosk (assigned access)]** (キオスク モードを設定する (割り当てられたアクセス)) を選択し、キオスクを作成するダイアログを開きます。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

4. **[Set up a kiosk]**  (キオスク モードを設定する) ページで、 **[開始する]** をクリックします。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="キオスク ページ - 開始する":::

5. 名前を入力して新しいキオスク アカウントを作成するか、または入力されているドロップダウン リストから既存のアカウントを選択して、 **[次へ]** をクリックします。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="キオスク モード - アカウントの作成":::

6. **[キオスク アプリを選ぶ]**  ページで、**[Microsoft Edge]** を選択し、 **[次へ]** をクリックします。

   > [!NOTE]
   > これは、Microsoft Edge Dev、Beta、Stable チャネルにのみ適用されます。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="キオスク モード - アプリを選ぶ":::

7. Microsoft Edge がキオスク モードで実行しているときの表示方法について、次のいずれかのオプションを選びます。

   - デジタル/対話型サイネージ - 全画面表示モードで特定のサイトを表示し、Microsoft Edge を実行します。
   - パブリック ブラウザー - Microsoft Edge の限定的な複数タブのバージョンを実行します。

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="キオスク モードの表示 - 全画面表示デジタル署名":::

8.  **[次へ]** を選択します。
9. キオスクが起動したときに読み込む URL を入力します。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="キオスク モード - URL の入力":::

10. アイドル時間に、既定値の 5 分をそのまま使用するか、独自の値を入力します。

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="キオスク モード - アイドル時間の入力":::

11.  **[次へ]** をクリックします。
12.  **[設定]**  ウィンドウを閉じて、選択内容を保存して適用します。

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="キオスク モード - 設定の終了":::

13. キオスク デバイスからサインオフし、ローカル キオスク アカウントでサインインして、構成を確認します。

## 機能上の制限事項

このキオスク モードのプレビュー版をリリースすることにより、Microsoft は商品の改善と新機能の追加に継続的に取り組んでいます。

次の機能をオフにすることをお勧めします。

- [StartupBoostEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startupboostenabled)
- [InternetExplorerIntegrationLevel](https://docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationlevel)
- [拡張機能](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensions-policies)
- [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)

## ロードマップ

### 2021 年初旬

次のサポートと機能を追加します。

- シングル アプリとして割り当てられたアクセスによる Microsoft Edge キオスク モードの Windows 10 1909 またはそれ以上での一般提供。
- Microsoft Edge 従来版とのパリティのための追加機能。
- キオスク モード プロファイル UX を使用してデバイスを構成するための Intune との統合。
- 追加のキーボード ショートカットはブロックされます。
- ブラウザーからの他のアプリケーションの起動を制限します。

## 関連項目

- [Windows デスクトップ エディションでのキオスクおよびデジタル サイネージの構成](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [Microsoft Edge レガシ キオスク モードの展開](https://aka.ms/edgekioskmode)
- [Microsoft Edge の展開を計画する](deploy-edge-plan-deployment.md)
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
