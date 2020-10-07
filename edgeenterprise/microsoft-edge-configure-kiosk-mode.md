---
title: Microsoft Edge キオスク モードを構成する
ms.author: aguta
author: aguta
manager: srugh
ms.date: 10/05/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge キオスク モードを構成する
ms.openlocfilehash: 799b3dd4b7fc96f0b8e5cb718bca98fd4f38ec15
ms.sourcegitcommit: 78905f66f4a6590a57c8f2bf808af92106b62996
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2020
ms.locfileid: "11094864"
---
# Microsoft Edge キオスク モードを構成する

この記事では、パイロットを実行することができる Microsoft Edge キオスク モードのオプションを構成する方法について説明します。 また、予定されている機能のロードマップも含まれます。

> [!NOTE]
> この記事は Microsoft Edge version 87 以降に適用されます。

## 概要

Microsoft Edge キオスク モードは、ブラウザーの 2 つのロックダウン エクスペリエンスを提供し、組織が顧客に最高のエクスペリエンスを作成し、管理し、提供できるようにします。 次のロックダウン エクスペリエンスを利用できます。  

- デジタル/対話型サイネージ エクスペリエンスでは、全画面表示モードで特定のサイトを表示します。
- パブリック ブラウジング エクスペリエンスでは、Microsoft Edge の限定的な複数タブのバージョンを実行します。

どちらのエクスペリエンスでも、ユーザー データを保護する Microsoft Edge InPrivate セッションを実行します。

## Microsoft Edge キオスク モードのセットアップ

キオスク モード機能の初期セットが Microsoft Edge Canary チャネルのバージョン 87 でテストに使用できるようになりました。 Microsoft Edge Canary は、[Microsoft Edge Insider Channels](https://www.microsoftedgeinsider.com/download) ページからダウンロードできます。

### キオスク モードの機能

次の機能を使用できます。

- InPrivate ナビゲーションは、セッションの終了時にブラウザー データとダウンロードを削除することにより、ユーザー データを保護します。
- 終了時のダウンロード削除を構成するためのポリシー。
- 非アクティブ状態が一定期間続いた後に、ユーザー セッションをリセットするオプション。
- ロックダウン機能の初期セット。 次の機能を使用できます。

  - マウスのコンテキスト メニュー
  - F12 開発者ツール
  - F11 全画面表示の終了 (全画面表示モードのとき)
  - *Edge://* ページの初期セットのブロック

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

## 割り当てられたアクセスによる Microsoft Edge の使用

### シングル アプリ キオスク

Microsoft Edge は現在、次のロックダウン エクスペリエンス、デジタル/対話型サイネージ、およびパブリックブラウジングを備えた、単一アプリに割り当てられたアクセス用の同じ Microsoft Edge レガシ キオスク モード タイプのサブセットをサポートしています。  

現在、割り当てられたアクセスによるキオスク モードは、最新の  [Windows 10 Insider Preview ビルド](https://insider.windows.com/) (バージョン 20215 以降) と  [Microsoft Edge Dev チャネル](https://www.microsoftedgeinsider.com/download) (バージョン 87.0.644.4 以降) でテストに使用できます。

**Windows Insiders Preview を入手するにはどうすればよいですか?**

PC に Windows 10 Insider Preview ビルドをインストールするには、「 [Windows 10 Insider Preview ビルドの概要](https://docs.microsoft.com/windows-insider/get-started)」の指示に従います。

### 複数アプリ キオスク

Microsoft Edge は、Windows 10 で[複数アプリの割り当てられたアクセス](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) によって実行できます。これは Microsoft Edge レガシでの "通常の閲覧" タイプのキオスク モードに相当します。 複数アプリの割り当てられたアクセスで Microsoft Edge を構成するには、[複数アプリ キオスクの設定](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)方法の手順に従います。 (Microsoft Edge Stable チャネルの AUMID は **MSEdge** です)。

Microsoft Edge キオスク モードを構成する複数アプリが割り当てられたアクセスで Microsoft Edge を使用する場合は、[Microsoft Edge ブラウザー ポリシー](https://review.docs.microsoft.com/en-us/DeployEdge/microsoft-edge-policies) を使用して、固有の要件を満たすように閲覧エクスペリエンスを構成できます。

### Windows の設定を使用して構成する

Windows の設定は、1 つか 2 つのシングル アプリのキオスク デバイスを設定する最も簡単な方法です。 シングル アプリのキオスク コンピューターをセットアップするには、次の手順に従います。

1. 最新の Windows 10 Insider Preview (バージョン 20215 以降) をインストールします。 「[Windows 10 Insider Preview ビルドの概要](https://docs.microsoft.com/windows-insider/get-started)」の指示に従います。
2. 最新の [Microsoft Edge Dev チャネル](https://www.microsoftedgeinsider.com/download) (87.0.644.4 以降) をインストールします。

   > [!IMPORTANT]
   > デバイス レベルのインストールが必要であるため、Canary 以外のチャネルのみがサポートされています。

3. キオスク コンピューターで、[Windows の設定] を開き、検索フィールドに "キオスク" と入力します。 次のスクリーンショットに表示されている  **[Set up a kiosk (assigned access)]** (キオスク モードを設定する (割り当てられたアクセス)) を選択し、キオスクを作成するダイアログを開きます。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

4. **[Set up a kiosk]**  (キオスク モードを設定する) ページで、 **[開始する]** をクリックします。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

5. 名前を入力して新しいキオスク アカウントを作成するか、または入力されているドロップダウン リストから既存のアカウントを選択して、 **[次へ]** をクリックします。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

6. **[キオスク アプリを選ぶ]**  ページで、**[Microsoft Edge]** を選択し、 **[次へ]** をクリックします。

   > [!NOTE]
   > これは、Microsoft Edge Dev、Beta、Stable チャネルにのみ適用されます。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

7. Microsoft Edge がキオスク モードで実行しているときの表示方法について、次のいずれかのオプションを選びます。

   - デジタル/対話型サイネージ - 全画面表示モードで特定のサイトを表示し、Microsoft Edge を実行します。
   - パブリック ブラウザー - Microsoft Edge の限定的な複数タブのバージョンを実行します。

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

8.  **[次へ]** を選択します。
9. キオスクが起動したときに読み込む URL を入力します。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

10. アイドル時間に、既定値の 5 分をそのまま使用するか、独自の値を入力します。

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

11.  **[次へ]** をクリックします。
12.  **[設定]**  ウィンドウを閉じて、選択内容を保存して適用します。

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

13. キオスク デバイスからサインオフし、ローカル キオスク アカウントでサインインして、構成を確認します。

## 機能上の制限事項

このキオスク モードのプレビュー版をリリースすることにより、Microsoft は商品の改善と新機能の追加に継続的に取り組んでいます。

現在、キオスク モードで次の機能はサポートされていませんが、次の機能を導入するための作業が進行中です。

- コレクション
- 拡張機能
- Internet Explorer モード
- Windows Defender Application Guard (WDAG)

## ロードマップ

### 今年の後半 (2020)

次の機能を追加します。

- [セッションの終了] ボタン
- 読み取り専用アドレス バー  
  - グループ ポリシーで構成可能
  - 有効にすると、ユーザーはアドレス バーを編集したり別のページに移動したりできなくなります。

- その他のロックダウン機能:

  - 追加のアクセラレータがブロックされます (Ctrl+N など)
  - [...] 設定メニューで必須オプション (印刷、ヘルプ、フィードバック、音声読み上げなど) のみが有効になります
  - 追加の *edge://* ページ ロックダウン (*edge://settings* など)
  - 印刷オプション UI の構成
  - エクスプローラーをダウンロード フォルダーのみに制限します。

### 2021 年初旬

次のサポートと機能を追加します。

- シングル アプリとして割り当てられたアクセスによる Microsoft Edge キオスク モードの Windows での一般提供。
- Microsoft Edge 従来版とのパリティのための追加機能。
- キオスク モード プロファイル UX を使用してデバイスを構成するための Intune との統合。

## 関連項目

- [Windows デスクトップ エディションでのキオスクおよびデジタル サイネージの構成](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [Microsoft Edge レガシ キオスク モードの展開](https://aka.ms/edgekioskmode)
- [Microsoft Edge の展開を計画する](deploy-edge-plan-deployment.md)
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
