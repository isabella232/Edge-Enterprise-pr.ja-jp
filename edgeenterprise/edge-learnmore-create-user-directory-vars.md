---
title: Microsoft Edge ユーザー データ ディレクトリ変数を作成する
ms.author: brianalt
author: AndreaLBarr
manager: srugh
ms.date: 04/21/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge ユーザー データ ディレクトリ変数を作成する方法について説明します
ms.openlocfilehash: 5ec78f16c7e5cd43f01845f35b8473494cd0c4bf
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "11618175"
---
# <a name="create-microsoft-edge-user-data-directory-variables"></a>Microsoft Edge ユーザー データ ディレクトリ変数を作成する

この記事では、Microsoft Edge を変更するときにハードコードされたパスを使用する代わりに、データ ディレクトリ変数を使用する方法について説明します。

>[!NOTE]
>この記事は、Microsoft Edge version 77 以降に適用されます。
## <a name="path-variables"></a>パス変数

データ ディレクトリ パスを変更するためのポリシー ([UserDataDir](microsoft-edge-policies.md#userdatadir) や [DownloadDirectory](microsoft-edge-policies.md#downloaddirectory) の構成など) では、変数がサポートされています。 これらのポリシーを構成するときは、ハードコードされたパスではなく、変数を使用できます。 たとえば、既定の場所ではなく、Windows ユーザーの "ローカル アプリケーション データ" にプロファイル データを格納する場合は、 [UserDataDir](microsoft-edge-policies.md#userdatadir) ポリシーを **${local_app_data}\Edge\Profile** に設定します。 ほとんどの Windows 10 インストールでは、このパスが *C:\Users\\&lt;Current-user&gt;\AppData\Local\Microsoft\Edge\Profile* に解決されます。

>[!NOTE]
>現在の**プロファイル パス**を確認するには、**[バージョン情報]** ページを開きます ("edge://version" と入力します)。 **プロファイル パス**には *C:\Users\\&lt;現在のユーザー&gt;\AppData\Local\Microsoft\Edge\User Data\Default* という形式を使用します。

### <a name="guidance-for-using-path-variables"></a>パス変数を使用するためのガイダンス

パスに変数を使用する前に、次のガイダンスをご確認ください。

- Microsoft Edge によってさまざまなデータが格納されるパスを決定するすべてのポリシーは、プラットフォームによって異なります。 これらのポリシーには、特定のプラットフォームでのみ使用できるものと、すべてのプラットフォームで使用できるものがあります。
- さまざまな場所から起動されるアプリケーションによって発生するエラーを回避するには、必ず絶対パスを指定してください。
- 変数はすべて、1 つのパス内で 1 回のみ指定できます。 ほとんどの場合、変数は絶対パスに解決されるため、変数を使用するにはこの方法を使用する必要があります。
- ほとんどのポリシーでは、パスが存在しなければ作成されます (既存の環境で可能な場合)。
- Microsoft Edge のバージョン/チャネルによってフォルダー構造の処理方法が異なるため、ポリシーによっては、ネットワークの場所を使用すると、予期しない結果を招く場合があります。

### <a name="supported-path-variables"></a>サポートされているパス変数

Microsoft Edge では、次のパス変数がサポートされています。

#### <a name="all-platforms"></a>すべてのプラットフォーム

| 変数 | 説明 |
| --- | --- |
| **${user_name}** | Microsoft Edge を使用しているユーザー。 Microsoft Edge では、SUID が考慮されます (実行時には所有者のユーザー ID のセットアップが必要になります)。例: *audreysmall* |
| **${machine_name}** | コンピューター名。ドメイン名を含まれる場合があります。 例: *audreysmall*、*audrey.ex.contoso.com* |

#### <a name="windows-only"></a>Windows のみ

| 変数 | 説明 |
| --- | --- |
| **${documents}** | 現在のユーザーのドキュメント フォルダー。 例: *C:\Users\Administrator\Documents* |
|**${local_app_data}** | 現在のユーザーのアプリケーション データ フォルダー。 例: *C:\Users\Administrator\AppData\Local* |
|**${roaming_app_data}** | 現在のユーザーのローミング アプリケーション データ フォルダー。 例: *C:\Users\Administrator\AppData\Roaming* |
| **${profile}** | 現在のユーザーのホーム フォルダー。 例: *C:\Users\Administrator* |
| **${global_app_data}** | システム全体のアプリケーション データ フォルダー。 例: *C:\AppData* |
| **${program_files}** | 現在のプロセスのプログラム ファイル フォルダー。 このフォルダーは、プロセスが 32 ビットか 64 ビットかによって異なります。 解決例: *C:\Program Files (x86)* |
| **${windows}** | Windows フォルダー。 例: *C:\Windows* |
| **${client_name)** | RDP または Citrix セッションに接続されているクライアント PC の名前。 ローカル セッションで使用する場合、この変数は空になります。 パス内で使用する場合は、プレフィックスとして、空でないと保証されるものを使用します。 例: *C:\edge_profiles\session_${client_name}* は、*C:\edge_profiles\session_&lt;ForlocalSessions&gt;* または *C:\edge_profiles\session_&lt;SomePCname&gt;* (リモート セッションの場合) に解決されます。 |
| **${session_name}** | アクティブなセッションの名前。 この名前を使用して、単一のユーザー プロファイルを使用している、同時に接続された複数のリモートセッションを区別します。 例: *WinSta0* (ローカル デスクトップ セッションの場合) |

#### <a name="macos-only"></a>macOS のみ

| 変数 | 説明 |
| --- | --- |
| **${users}** | ユーザーのプロファイルが格納されるフォルダー。 例: */Users* |
| **${documents}** | 現在のユーザーのドキュメント フォルダー。 例: */Users/audreysmall/Documents* |

## <a name="content-license"></a>コンテンツ ライセンス

>[!NOTE]
>このページの一部の情報は、Chromium.org によって作成および共有されている著作物に基づいており、[Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/) に記載されている条項に従って使用されています。 元のページは[こちら](https://www.chromium.org/administrators/policy-list-3/user-data-directory-variables)です。
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br/>この著作物は、<a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a> に従って使用許諾されています。
## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)