---
title: キオスク モードの移行を計画する
ms.author: aguta
author: aguta
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: キオスク モードの移行を計画する
ms.openlocfilehash: 95c50b39eb6e844ae4309b260087931232276d45
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642913"
---
# <a name="plan-your-kiosk-mode-transition"></a>キオスク モードの移行を計画する

この記事では、キオスクを Microsoft Edge 従来版から Microsoft Edge に移行する方法に関するガイダンスを示します。  

> [!NOTE]
> この記事は、Microsoft Edge バージョン 87 (Stable、Beta、および Dev チャネル) 以降に適用されます。

> [!IMPORTANT]
> 2021 年 3 月 9 日にサポートが終了すると、Microsoft Edge 従来版は削除され、4 月の Windows Update の一部として Chromium の Microsoft Edge に置き換わります。 詳細については、[このブログ投稿](https://aka.ms/EdgeLegacyEOS)を参照してください。 ブラウザー ベースのキオスク シナリオを引き続き使用するには、デバイスに Chromium の Microsoft Edge をインストールし、4 月の Windows Update のリリースの前にキオスク モードをセットアップする必要があります。

## <a name="kiosk-setup-steps"></a>キオスクのセットアップ手順

Microsoft Edge でキオスクをセットアップするためのガイドとして、次の手順を使用します。

**手順 1: リリースされている (および今後リリース予定の) キオスク モード機能に対するニーズを評価します。** 次の表に、Chromium の Microsoft Edge と Microsoft Edge 従来版でキオスク モードによってサポートされている機能を示します。 次の表を Microsoft Edge への移行のためのガイドとして使用し、Microsoft Edge の両方のリリースでこれらの機能がどのようにサポートされているかを比較してください。

|機能|デジタル/対話型サイネージ|パブリック ブラウジング|Microsoft Edge のバージョン (以上) で利用可能|Microsoft Edge レガシで使用可能|
|-|-|-|-|-|
|InPrivate ナビゲーション。|Y|Y|89|Y|
|非アクティブ時のリセット|Y|Y|89|Y|
|[読み取り専用アドレス バー](./microsoft-edge-policies.md#kioskaddressbareditingenabled) (ポリシー) |N|Y |89|N|
|[終了時にダウンロードを削除する](./microsoft-edge-policies.md#kioskdeletedownloadsonexit) (ポリシー)  | Y|Y |89|N|
|F11 がブロックされています (全画面に入る/終了する) | Y | Y | 89 |Y|
|F12 がブロックされています (開発者ツールの起動) | Y | Y | 89 |Y|
| 複数タブのサポート | N| Y| 89|Y|
|[URL のサポートを許可する](./microsoft-edge-policies.md#urlallowlist) (ポリシー)|Y|Y|89|N|
|[URL のサポートをブロックする](./microsoft-edge-policies.md#urlblocklist) (ポリシー)|Y|Y|89|N|
|[[ホーム] ボタンを表示する](./microsoft-edge-policies.md#showhomebutton) (ポリシー)|N|Y|89|Y|
|[お気に入りを管理する](./microsoft-edge-policies.md#managedfavorites) (ポリシー)|N|Y|89|Y|
|[プリンターを有効化](./microsoft-edge-policies.md#printingenabled) (ポリシー)|Y|Y|89|Y|
|[新しいタブ ページの URLを構成する](./microsoft-edge-policies.md#newtabpagelocation) (ポリシー)|N|Y|89|Y|
|[セッションの終了] ボタン | N| Y| 89|Y|
|すべての内部 Microsoft Edge URL はブロックされます (*edge://downloads* および *edge://print* を除く) |N|Y|89|Y|
| Ctrl + N がブロックされています (新しいウィンドウを開く) | Y | Y | 89 |Y|
| Ctrl + T がブロックされています (新しいタブを開く) |Y | Y | 89 |Y|
|設定と詳細 (...) では、必要なオプションだけが表示されます。  |Y |Y |89 |Y|
|ブラウザーからの他のアプリケーションの起動を制限する|Y|Y|90|Y|
|UI 印刷設定のロックダウン|Y|Y|90|Y|
|[新しいタブ ページをホーム ページとして設定する](./microsoft-edge-policies.md#homepageisnewtabpage) (ポリシー)|N|Y|90|Y|

> [!NOTE]
> Microsoft Edge のリリース スケジュールについては、「[Microsoft Edge リリース スケジュール](microsoft-edge-release-schedule.md)」を参照してください。

**手順 2: Microsoft Edge で新しいキオスクをテストします。** Microsoft Edge で、キオスク モードの設定をテストすることをお勧めします。 キオスク モードをすばやく簡単にテストする方法は、次に説明するように、Windows の設定を使ってシングル アプリとして割り当てられたアクセスを構成することです。

1. 次の表に示すオペレーティング システムの最小システム更新プログラム。

|オペレーティング システム|バージョン|更新プログラム|
|--|--|--|
|Windows 10 | 2004 以降|[KB4601382 以降](https://support.microsoft.com/topic/february-24-2021-kb4601382-os-builds-19041-844-and-19042-844-preview-1a7ed2b4-017d-2644-a1e8-dd6bf14cba76) |
|Windows 10| 1909| [KB4601380 以降](https://support.microsoft.com/topic/february-16-2021-kb4601380-os-build-18363-1411-preview-2e3c38e1-a947-1033-8006-a30f3806da18)|

2. 最新の機能をテストするには、最新の [Microsoft Edge 安定チャネル](https://www.microsoftedgeinsider.com/download) (バージョン 89 以上) をダウンロードできます。

   > [!IMPORTANT]
   > デバイス レベルのインストールが必要であるため、Canary チャネルはサポートされていません。

3. キオスク コンピューターで [Windows の設定] を開き、検索フィールドに「キオスク」と入力します。 次のスクリーンショットに表示されている  **[Set up a kiosk (assigned access)]** (キオスク モードを設定する (割り当てられたアクセス)) を選択し、キオスクを作成するダイアログを開きます。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="割り当てられたアクセスによるキオスクの設定":::

4. **[Set up a kiosk]**  (キオスク モードを設定する) ページで、 **[開始する]** をクリックします。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="キオスク ページ - 開始する":::

5. 名前を入力して新しいキオスク アカウントを作成するか、または入力されているドロップダウン リストから既存のアカウントを選択して、 **[次へ]** をクリックします。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="キオスク モード - アカウントの作成":::

6. **[キオスク アプリを選ぶ]**  ページで、**[Microsoft Edge]** を選択し、 **[次へ]** をクリックします。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5c-choose-a-kiosk-app.png" alt-text="キオスクを選択する - 画面全体のデジタル記号":::

7. Microsoft Edge がキオスク モードで実行しているときの表示方法について、次のいずれかのオプションを選択します。

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

13. キオスク デバイスからサインアウトし、ローカル キオスク アカウントでサインインして、構成を確認します。

**手順 3: 移行計画を作成します。** 2021 年 3 月 9 日に Microsoft Edge 従来版のサポートが終了する前に、テストと組織のニーズに基づいて移行計画を作成して、Chromium の Microsoft Edge に移行することをお勧めします。

## <a name="additional-scenarios-that-require-you-to-recreate-an-existing-kiosk-mode"></a>既存のキオスク モードを再作成する必要があるその他のシナリオ

Windows 10 バージョン 20H2 に更新すると、Chromium の Microsoft Edge がインストールされ、Microsoft Edge 従来版が非表示になります。 この場合、Chromium の Microsoft Edge でキオスク モードを再度設定する必要があります。

## <a name="how-to-get-help"></a>ヘルプを入手する方法

キオスク モードがお客様の日々の業務において重要な要素である可能性を考え、Microsoft はこの移行を可能な限りスムーズにし、中断を回避したいと考えています。 お客様のビジネスで Chromium の Microsoft Edge に移行する際にサポートが必要な場合:

- [サポート](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=a77ee9b7-b6b6-aa08-d7b9-887ebe228207)が Microsoft から提供されています。 
- [FastTrack のサポート](https://www.microsoft.com/fasttrack/microsoft-365/microsoft-edge?rtc=1)は、Windows 10 Enterprise の有料シートを 150 シート以上お持ちのお客様に無料で提供されています。
- [App Assure](https://www.microsoft.com/en-us/fasttrack/microsoft-365/app-assure) は、サイトまたはアプリの互換性の問題が発生した場合に利用できます。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [4 月の Windows 10 Update Tuesday リリースで Microsoft Edge 従来版が新しい Microsoft Edge に置き換わります](https://techcommunity.microsoft.com/t5/microsoft-365-blog/new-microsoft-edge-to-replace-microsoft-edge-legacy-with-april-s/ba-p/2114224)