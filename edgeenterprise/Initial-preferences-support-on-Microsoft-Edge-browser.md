---
title: ブラウザーでの初期の基本設定Microsoft Edgeサポート
ms.author: collw
author: AndreaLBarr
manager: srugh
ms.date: 07/27/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 最初の基本設定は、Microsoft Edgeでサポートされます。
ms.openlocfilehash: 39af88d21107ad548166c749c3ba765754270b48
ms.sourcegitcommit: 715cb8c8101a6daed48563f33d2bc40ee7109e0e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "11882263"
---
# <a name="configure-microsoft-edge-using-initial-preferences-settings-for-the-first-run"></a>初回実行時のユーザー設定を使用して Microsoft Edge を構成する

次の情報を使用して、デバイスMicrosoft Edge初期設定を構成Windowsします。

> [!Note]
> この記事は、バージョン 93 以降Microsoft Edgeに適用されます。

## <a name="configure-policy-settings-on-windows"></a>Windows でポリシー設定を構成する

Microsoft Microsoft Edgeリリース 93 から、管理者が最初の実行用にブラウザーを構成するのに役立つ、限られた数の初期基本設定 (以前は "Master Preferences") がサポートされています。以下のサポートされている設定の一覧を参照してください。  

展開すると、初期基本設定は管理対象デバイスの既定のブラウザー設定として機能します。これらは、管理者が既定として使用する設定ですが、ユーザーが変更したり、Active Directory ® ドメインに参加していないデバイスで使用できない設定です。

Intial Preferences 設定の例としては、既定のホームページの初期構成や、特定の URL を含むタブがあります。

基本設定は、initial_preferencesファイルから一度だけコピーされ、構成後にこのファイルに対して行われた変更は尊重されません。 設定がポリシーによって管理され、Microsoft Edge [](/deployedge/microsoft-edge-policies) initial_preferences ファイルで構成されている場合、ポリシーは常に優先されます。

以下は、ユーザーが現在サポートしている基本設定の一覧Microsoft Edge。

| 基本設定カテゴリ | 設定 |
| - | - |
| Bookmark_bar | show_apps_shortcut<br>show_managed_bookmarks<br>show_on_all_tabs |
| Bookmarks | editing_enabled |
| ブラウザー/clear_data | browsing_history<br>browsing_history_basic"<br>キャッシュ<br>cache_basic<br>Cookie<br>download_history<br>form_data<br>パスワード |
| 履歴 | browsing_history<br>キャッシュ<br>Cookie<br>download_history<br>form_data<br>hosted_apps_data<br>パスワード<br>site_settings |
| Browser | first_run_tabs<br>dark_theme<br>show_toolbar_bookmarks_button<br>show_toolbar_collections_butto<br>show_toolbar_downloads_button<br>show_home_button<br>show_prompt_before_closing_tabs<br>show_toolbar_history_button |
| default_search_provider | [default_search_provider] 有効 |
| 全画面表示 | 許可されます |
| ホーム ページ | Homepage_url |
| homepage_is_newtabpage | homepage_is_newtabpage |
| セッション | restore_on_startup<br>startup_urls |
| 拡張機能 | 拡張機能 : 設定 |

## <a name="1-download-an-example-initial_preferences-file"></a>1: ファイルの例をinitial_preferencesする

開始するには、この場所にあるファイル*形式のinitial_preferences*をダウンロードし、Microsoft Edge Enterprise手順[](https://www.microsoft.com/edge/business/download)**** に従います。

## <a name="2-customize-and-validate-the-initial_preferences-file"></a>2: ファイルのカスタマイズとinitial_preferencesする

ダウンロードしたファイルの基本設定をinitial_preferences *し* 、JSON コードにエラーが発生しなかからず変更を検証します。 エラーが見つかった場合は、initial_preferences ファイルの構文と構造を確認し *、修正* を行い、もう一度検証します。 JSON、Online [JSON Tools、](https://jsonformatter.org/)または[JSON](https://code.visualstudio.com/docs/languages/json)編集を検証するためのツールの例Visual Studio Code。

## <a name="3-deploy-preferences-to-users-computer"></a>3: ユーザーのコンピューターに基本設定を展開する

initial_preferences ** Microsoft Edge ブラウザーが展開されているのと同時に、initial_preferences ファイルをユーザーのデバイスに展開し、デバイス上の次の場所にファイルを配置します。

### <a name="windows-amd64-and-arm64"></a>Windows (AMD64 および ARM64)

| チャネル | Location |
| - | - |
| Stable | `"C:\Program Files (x86)\Microsoft\Edge\Application"` |
| Beta | `"C:\Program Files (x86)\Microsoft\Edge Beta\Application"` |
|Canary | `"%LOCALAPPDATA%\Microsoft\Edge SxS\Application"` |
| Dev | `"C:\Program Files (x86)\Microsoft\Edge Dev\Application"` |

**注**: *initial_preferencesファイル*は、ユーザーのコンピューター上の msedge.exe ファイルと同じフォルダーにWindowsがあります。  

### <a name="macos"></a>macOS

| チャネル | Location |
| - | - |
| Stable | `"~/Library/Application Support/Microsoft Edge/Microsoft Edge Initial Preferences"` |
| Beta | `“~/Library/Application Support/Microsoft Edge Beta/Microsoft Edge Initial Preferences"` |
| Canary | `“~/Library/Application Support/Microsoft Edge Canary/Microsoft Edge Initial Preferences"` |
| Dev | `"~/Library/Application Support/Microsoft Edge Dev/Microsoft Edge Initial Preferences"` |

## <a name="important-notes-msi--pkg-deployment-and-initial_preferences-interaction"></a>重要な注意事項: MSI / Pkg の展開 *と* initial_preferences操作

初期の基本設定は、エンド ユーザーがブラウザーをinitial_preferencesする前に、ファイルが展開されている場合にのみ有効になります。  

## <a name="see-also"></a>関連項目

- [次 *initial_prefrences* テンプレート ファイルの例](https://www.microsoft.com/edge/business/download)
