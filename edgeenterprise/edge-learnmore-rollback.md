---
title: 企業向け Microsoft Edge ロールバック
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 02/04/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge を以前のバージョンにロールバックする方法
ms.openlocfilehash: 38954f4b293470758b5484591779a3af52c6992c
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617377"
---
# <a name="how-to-roll-back-microsoft-edge-to-a-previous-version"></a>Microsoft Edge を以前のバージョンにロールバックする方法

この記事では、ロールバック機能を使用して、Microsoft Edge の以前のバージョンにロールバックする方法について説明します。 この機能の詳細については、「[ビデオ: Microsoft Edge バージョンのロールバック](microsoft-edge-video-version-rollback.md)」をご覧ください。

>[!NOTE]
>この記事は、Microsoft Edge バージョン 86 以降に適用されます。

## <a name="introduction-to-rollback"></a>ロールバックの概要

ロールバックすると、Microsoft Edge ブラウザーのバージョンを以前のものに置換えることができます。 この機能は、Microsoft Edge を展開する企業のためのセーフティネットとして設計されています。 Microsoft Edge の問題をトラブルシューティングする方法を提供します。 ロールバックの利点は、簡単かつ迅速に以前のブラウザのバージョンに戻すことができることです。 ロールバックすることで、Microsoft Edge の問題が業務に与える潜在的な影響を軽減することができます。

## <a name="before-you-begin"></a>始める前に

Microsoft Edge 環境にロールバック機能がインストールされているしくみを理解しておくことが重要です。 ロールバックの展開には、MSI を使って手動で行う方法と、Microsoft Edge 更新プログラムおよびグループ ポリシーを使って行う方法の2つの方法があります。 また、よりスムーズに展開するために、グループ ポリシーを選択して使用することをお勧めします。

### <a name="recommendations"></a>推奨事項

ロールバック機能は、Microsoft Edge ブラウザーの更新プログラムで発生する問題を一時的に修正するためのものです。 最新のセキュリティ更新プログラムによって提供される保護機能を使用するには、Microsoft Edge ブラウザーの最新バージョンをインストールすることをお勧めします。 以前のバージョンにロールバックすると、既知のセキュリティ問題にさらされるリスクがあります。

ブラウザーのバージョンを一時的にロールバックする前に、組織内のすべてのユーザーの同期を有効にすることを強くお勧めします。 同期を有効にしない場合、閲覧データが永久に失われる危険性があります。 同期の詳細については、「[Microsoft Edge を同期する](microsoft-edge-enterprise-sync.md)」 を参照してください。

> [!CAUTION]
> 常にデータ損失のリスクがあるため、ロールバックは必要な場合のみ使用してください。

## <a name="enable-rollback-manually-with-an-msi"></a>MSI を使用して、手動でのロールバックを有効にする

MSI を使用して手動でロールバックするには、次の手順を使用します。

1. Microsoft Edge 更新プログラムを無効にします。

   > [!NOTE]
   > 最新の管理用テンプレートをインストールすることをお勧めします。 詳細については、「[Microsoft Edge 管理用テンプレートをダウンロードしてインストールする](./configure-microsoft-edge.md#1-download-and-install-the-microsoft-edge-administrative-template)」 を参照してください。

   - ローカル グループ ポリシー エディターを開き、 *[コンピューターの構成]、[管理用テンプレート]、[Microsoft Edge 更新プログラム]、[アプリケーション]、[Microsoft Edge]* の順に移動します。
   - [**更新ポリシーの上書き**] を選択し、[**有効にする**] を選択します。
   - [**オプション**] で、[ポリシー] ドロップダウンリストから [**無効にする**] を選びます。

2. MSI を入手します。

   - ロールバックするバージョン用の MSI をダウンロードするのは [こちら](https://www.microsoft.com/edge/business/download)。
   - MSI をデスクトップに保存します。

3. ロールバック コマンドを実行します。

   - **[管理者として実行]** を使用して Windows コマンド プロンプトを開きます。
   - 次のコマンドを入力します。 *C:\Users\username\Desktop\test* は、ダウンロードした MSI のパスで、ファイル名は .msi ファイルの名前です。<br>
 `C:\Users\username\Desktop\test>msiexec /I FileName.msi /qn ALLOWDOWNGRADE=1`<br>
     > [!NOTE]
     > msiexec の詳細については、「[msiexec](/windows-server/administration/windows-commands/msiexec)」 を参照してください。
   - Microsoft Edge を終了して再起動し、ロールバックが正常に機能したことを確認します。 [**設定およびその他**] (ALT + F) から [**設定**] に移動し、[**Microsoft Edge について**] を選択します。

## <a name="enable-rollback-with-microsoft-edge-update-and-group-policy"></a>Microsoft Edge 更新プログラムとグループポリシーを使用してロールバックを有効にする

Microsoft Edge 更新プログラムとグループポリシーでロールバックを有効にするには、次の手順を使用します。

1. ローカル グループ ポリシー エディターを開き、 *[コンピューターの構成]、[管理用テンプレート]、[Microsoft Edge 更新プログラム]、[アプリケーション]、[Microsoft Edge]* の順に移動します。
2. [**対象バージョンにロールバック**]、[**有効にする**] の順に選択します。
3. [**対象バージョンの上書き**] を選び、ロールバック先のブラウザー バージョンを選択します。
4. [**更新ポリシーの上書き**] を選択し、[**有効にする**] を選択します。 [**オプション**] 下の [ポリシー] ドロップダウンリストから次のオプションのいずれかを選択します ([**更新を無効にする**] の場合を除く）。

   - 常に更新プログラムを許可する
   - 自動サイレント更新に限る

     > [!NOTE]
     > グループポリシーの更新を実施するには、Windows 管理者のコマンドプロンプトで `gpupdate /force`を 入力します (管理者として実行します)。

5. **[OK]** をクリックして、ポリシー設定を保存します。 ロールバックは、次回 Microsoft Edge Update が更新プログラムをチェックするときに実行されます。 更新が早く実施されるようにしたい場合は、Microsoft Edge Update のポーリング間隔を変更するか、MSI を使用してロールバックを有効にする必要があります。

### <a name="common-rollback-errors"></a>一般的なロールバック エラー

ロールバックできなくなるエラーには、次のようなものがあります。

- 入力がサポートされていない対象バージョンである
- 入力が存在しない対象バージョンである
- 入力のフォーマットが無効である

### <a name="recommended-group-policies"></a>推奨されるグループポリシー

ロールバックを使用するには、次のグループポリシーと設定が強く推奨されます。

#### <a name="sync-group-policies"></a>グループ ポリシーを同期する

- ForceSync。 ForceSync を有効にします。 このポリシーによって、すべての Azure Active Directory (Azure AD) ユーザーの同期の有効化が強制されます。 このポリシーは、Microsoft Edge versions 86 以降でのみ有効です。
- *同期ポリシーから除外する種類のリストを構成する* により、管理者はユーザーが同期できるデータを制御できます。

#### <a name="browser-restart-group-policies"></a>ブラウザーの再起動グループポリシー

ロールバックを有効にした後、ユーザーに強制的に再起動させることをお勧めします。

- [*保留中の更新についてブラウザーの再起動が推奨されている、または必要であることをユーザーに通知する*] を有効にします。 [オプション] で [**必須**] を選択します。
- [*更新通知の期間を設定する*] を有効にしてから、希望する時間をミリ秒単位で設定します。

## <a name="snapshot"></a>スナップショット

スナップショットは、ユーザーデータフォルダーのバージョン付きのコピーです。 バージョンアップグレード中、以前のバージョンのスナップショットが作成され、スナップショットフォルダーに格納されます。 ロールバックが完了すると、バージョン一致のスナップショットが新しいユーザーデータフォルダーにコピーされて、スナップショットフォルダーから削除されます。 ダウングレード時にバージョン一致スナップショットが使用できない場合、ロールバックは同期を使用して、新しい Microsoft Edge バージョンにユーザーデータを入力します。

[UserDataSnapshotRetentionLimit](./microsoft-edge-policies.md#userdatasnapshotretentionlimit) グループ ポリシーを使用すると、一定時間に保持できるスナップショットの数に制限を設定できます。 既定では、3つのスナップショットが保持されます。 ユーザーは、保持するスナップショットの数を0から5の間で構成できます。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="manual-msi-rollback"></a>手動での MSI ロールバック

#### <a name="what-generic-msi-failures-that-can-happen"></a>起こりうる一般的な MSI の問題には何がありますか?

1. [更新グループポリシーのインストール] が無効になっている場合、ロールバックは行われません。

   - ロールバックを使用するには、インストールが [**有効**] に設定されていることを確認します。 このポリシーを無効にすると、Microsoft Edge チャネルがインストールされなくなります。 詳細については、「[インストール](./microsoft-edge-update-policies.md#install)」 を参照してください。

2. 啓蒙更新プログラムが存在しない場合は、[*Microsoft Edge でのブラウザーの同時実行エクスペリエンスを許可する*] が有効になっていない限り Microsoft Edge のインストールがブロックされます。

   - Windows Version 1903、1909 では、最終更新が2019年10月以前の場合、この問題が発生する可能性があります。
   - Windows Version 1709、1803、1809 では、最終更新が2019年11月以前の場合、この問題が発生する可能性があります。<br>
詳しくは、「[次のバージョンの Microsoft Edge をサポートする Windows 更新プログラム](./microsoft-edge-sysupdate-windows-updates.md)」 をご覧ください。

#### <a name="the-following-error-message-was-shown-after-using-the-command-prompt-and-rollback-didnt-occur-whats-wrong"></a>コマンド プロンプトを使用してもロールバックが発生せず、以下のようなエラーメッセージが表示されました。 何が問題なのですか?

![ロールバック ステータス メッセージ](./media/edge-learnmore-rollback/edge-rollback-cmd-flag-error.png)

*ALLOWDOWNGRADE=1* は実行されませんでした。

### <a name="microsoft-edge-update-and-group-policy-rollback"></a>Microsoft Edge 更新プログラムとグループポリシーのロールバック

#### <a name="i-set-rollback-to-target-version-enabled-update-policy-override-input-my-desired-browser-version-for-target-version-override-but-the-browser-version-wasnt-what-i-expected-whats-wrong"></a>*対象バージョンにロールバック* を設定し、*更新ポリシーの上書き* を有効にして *対象バージョンの上書き* 用に希望するブラウザーのバージョンを入力しましたが、ブラウザーのバージョンは期待したものではありませんでした。 何が問題なのですか?

ロールバックを妨げる一般的なエラーは、次のとおりです。

- 対象バージョンへのロールバックが設定されていない場合、ロールバックは実行されません。
- 対象バージョンの上書き設定には、次のいずれかの問題があります。

  - 対象バージョンの上書きが、サポートされていない対象バージョンに設定されています。
  - 対象バージョンの上書きが、存在しない対象バージョンに設定されています。
  - 対象バージョンの上書きの入力形式が正しくありません。

- 更新ポリシーの上書きが [更新を無効にする] に設定されている場合、Microsoft Edge Update は更新を受け入れず、ロールバックは実行されません。

### <a name="i-set-all-the-group-policies-correctly-but-rollback-didnt-execute-what-happened"></a>すべてのグループポリシーを正しく設定しましたが、ロールバックが実行されません。 何が問題なのですか?

Microsoft Edge Update では、更新プログラムの確認がまだ行われていません。 既定では、自動更新チェックにより 10 時間ごとに更新が確認されます。 この問題を解決するには、自動更新のチェック期間の上書きグループポリシーで Microsoft Edge 更新プログラムのポーリング間隔を変更します。 詳細については、[AutoUpdateCheckPeriodMinutes](./microsoft-edge-update-policies.md#autoupdatecheckperiodminutes) ポリシーを参照してください。

### <a name="as-an-it-admin-i-followed-all-the-steps-for-rollback-correctly-only-a-portion-of-my-user-group-was-rolled-back-why-havent-the-other-users-been-rolled-back-yet"></a>IT 管理者の場合、正常にロールバックするためのすべての手順に従います。 ユーザーグループの一部しかロールバックされませんでした。 他のユーザーが、まだロールバックされていないのはなぜですか?

グループポリシー設定が、まだすべてのクライアントに同期されていません。 管理者がグループポリシーを設定した場合、クライアントがこれらの設定を即座に受け取ることはありません。 [リモートグループポリシーの更新](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/jj134201(v=ws.11))を実行できます。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [ビデオ: Microsoft Edge バージョンのロールバック](microsoft-edge-video-version-rollback.md)