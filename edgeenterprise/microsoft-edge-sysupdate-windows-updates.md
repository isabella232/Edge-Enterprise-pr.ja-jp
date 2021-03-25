---
title: Microsoft Edge 用 Windows 更新プログラム
ms.author: jtkim
author: dan-wesley
manager: srugh
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 用 Windows 更新プログラム。
ms.openlocfilehash: 880e5a591ee23ff852981e73fe4fc4cd815be9ad
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447151"
---
# <a name="windows-updates-to-support-the-next-version-of-microsoft-edge"></a>次のバージョンの Microsoft Edge をサポートする Windows 更新プログラム

この記事では、次のバージョンの Microsoft Edge をサポートするために Windows がどのように更新されるかについて説明します。

> [!IMPORTANT]
> Microsoft Edge 従来版のサービス終了については、Microsoft Edge 製品チームの[ブログ記事](https://aka.ms/EdgeLegacyEOS)を参照してください。

> [!NOTE]
> この記事は、Microsoft Edge Stable チャネルに適用されます。

## <a name="microsoft-edge-and-the-windows-release-cycle"></a>Microsoft Edge と Windows のリリース サイクル

次のバージョンの Microsoft Edge では、より柔軟で頻度の高い更新の機能が提供されます。 ブラウザーのリリースは Windows のメジャー リリースにバインドされていないため、次のバージョンの Microsoft Edge が Windows にシームレスに適合するように、オペレーティング システムに変更が加えられます。 その結果、機能の更新プログラムは約 6 週間のサイクルでリリースされます。 セキュリティと互換性の更新プログラムは、必要に応じて出荷されます。

## <a name="updates-and-the-user-experience"></a>更新プログラムとユーザー エクスペリエンス

次のバージョンの Microsoft Edge の Stable チャネルがインストールされるまで、更新プログラムによるユーザー エクスペリエンスの変更はありません。 Microsoft Edge Beta、Dev、または Canary をインストールしても、Windows での変更はトリガーされません。 これらのブラウザー リリースは、既存のブラウザーと並行してインストールされます。

すべての更新が適用され、次のバージョンの Microsoft Edge の Stable チャネルがシステムレベルでインストールされると、以下の変更がシステムで有効になります。

- 現在のバージョンの Microsoft Edge に対応するスタート メニューのピン留め、タイル、およびショートカットはすべて、次のバージョンの Microsoft Edge に移行されます。
- 現在のバージョンの Microsoft Edge に対応するタスク バーのピン留めおよびショートカットはすべて、次のバージョンの Microsoft Edge に移行されます。
- 次のバージョンの Microsoft Edge は、タスク バーにピン留めされます。 現在のバージョンの Microsoft Edge が既にピン留めされている場合は、置き換えられます。
- 次のバージョンの Microsoft Edge により、デスクトップにショートカットが追加されます。 現在のバージョンの Microsoft Edge のショートカットが既に存在する場合は、置き換えられます。
- Microsoft Edge が既定で処理するほとんどのプロトコルは、次のバージョンの Microsoft Edge に移行されます。
- 現在の Microsoft Edge は、設定、すべてのアプリ、ファイルまたはプロトコルのサポート ダイアログなど、OS 内のすべての UX サーフェイスで非表示になります。
- 現在のバージョンの Microsoft Edge を起動する試行はすべて、次のバージョンの Microsoft Edge にリダイレクトされます。

  > [!NOTE]
  > ユーザーレベルのインストールでは、これらの動作はトリガーされません。

前の変更と共に、次のバージョンの Microsoft Edge の Stable チャネルがインストールされているかどうかに関係なく行われる変更があります。

- Microsoft Edge は、次のバージョンの Microsoft Edge がサポートしていない書籍および XML プロトコルの登録を解除します。 これらのプロトコルをユーザーが開こうとすると、既定のアプリを選択するように求めるダイアログが表示されます。 書籍のサポートに関する変更については、「[電子書籍の利用を続けるには、ePub アプリをダウンロードしてください](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fsupport.microsoft.com%2Fhelp%2F4517840&data=02%7C01%7Cv-danwes%40microsoft.com%7Cc9f8571b880549c30fcf08d72be5eaf9%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637026138803983526&sdata=qtb3DvVZQ6H%2FFXnBievkl%2B%2BngAQXwl340PcH8kRc3y4%3D&reserved=0)」をご覧ください。

## <a name="timeline"></a>タイムライン

ここに記載されているエクスペリエンスをサポートするために必要な変更は、Windows のさまざまなバージョンに対して 3 つの更新プログラムで提供されます。

### <a name="windows-versions-1903-and-1909"></a>Windows Version 1903、1909

- 2019 年 8 月セキュリティ更新プログラムで提供される、2019 年 7 月の更新 (オプション) に含まれる最初の変更セット。
- 2019 年 9 月セキュリティ更新プログラムで提供される、2019 年 8 月の更新 (オプション) に含まれる 2 番目の変更セット。

  > [!NOTE]
  > これは、Microsoft Edge が XML プロトコルの登録を解除する更新プログラムです。

- 2019 年 10 月セキュリティ更新プログラムで提供される、2019 年 9 月の更新 (オプション) に含まれる 3 番目の変更セット。

  > [!NOTE]
  > これは Microsoft Edge で電子ブックのサポートが終了する更新プログラムです。

### <a name="windows-versions-1709-1803-and-1809"></a>Windows Version 1709、1803、1809

- 2019 年 9 月セキュリティ更新プログラムで提供される、2019 年 8 月の更新 (オプション) に含まれる最初の変更セット。
- 2019 年 10 月セキュリティ更新プログラムで提供される、2019 年 9 月の更新 (オプション) に含まれる 2 番目の変更セット。

  > [!NOTE]
  > これは、Microsoft Edge が XML プロトコルの登録を解除する更新プログラムです。

- 2019 年 11 月セキュリティ更新プログラムで提供される、2019 年 10 月の更新 (オプション) に含まれる 3 番目の変更セット。

  > [!NOTE]
  > これは Microsoft Edge で電子ブックのサポートが終了する更新プログラムです。

次の表に、各変更セットに含まれる更新プログラムの詳細を示します。

| Windows 10 | 詳細情報 | 必要なダウンロード |
|--|--|--|
| Version 1709 | [KB4525241](https://support.microsoft.com/help/4525241/windows-10-update-kb4525241) | [Windows 10 Version 1709 用の累積的な更新プログラム](https://www.catalog.update.microsoft.com/Search.aspx?q=4525241) |
| Version 1803  | [KB4525237](https://support.microsoft.com/help/4525237/windows-10-update-kb4525237) | [Windows 10 Version 1803 用の累積的な更新プログラム](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4525237) |
| Version 1809  | [KB4523205](https://support.microsoft.com/help/4523205/windows-10-update-kb4523205) | [Windows 10 Version 1809 用の累積的な更新プログラム](https://www.catalog.update.microsoft.com/Search.aspx?q=4523205) |
| Version 1903、1909 |[KB4517389](https://support.microsoft.com/help/4517389/windows-10-update-kb4517389)  | [Windows 10 Version 1903 および 1909 用の累積的な更新プログラム ](https://www.catalog.update.microsoft.com/Search.aspx?q=4517389) |

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge ドキュメント](./index.yml)