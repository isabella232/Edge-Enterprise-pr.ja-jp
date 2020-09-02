---
title: エンタープライズ環境の Edge に関してよく寄せられる質問
ms.author: jwhit
author: jwhit-MSFT
manager: laurawi
ms.date: 08/03/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: エンタープライズ環境での Microsoft Edge の展開についてよく寄せられる質問
ms.openlocfilehash: 0f6891f4f7187b23f6e3d4e7880fdafa49def351
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980435"
---
# エンタープライズ環境の Microsoft Edge についてよく寄せられる質問

> [!NOTE]
> この記事は Microsoft Edge version 77 以降に適用されます。

## 所有している Microsoft Edge のバージョンを確認する方法を教えてください。

Microsoft Edge の右上隅の省略記号アイコン (**...**) をクリックして、**[設定]** をクリックします。 **[Microsoft Edge について]** を選択して、Microsoft Edge のバージョンを確認します。

## Internet Explorer 11 の更新プログラムは引き続き提供されますか?

Internet Explorer は、信頼できる安全なブラウザーとしてサポートされています。 Internet Explorer が Windows のコンポーネントであることに変わりはなく、サポートは、インストールされている OS のサポート ライフサイクルに従って行われます。 詳しくは、「[ライフサイクルに関する FAQ - Internet Explorer](https://support.microsoft.com/help/17454/)」をご覧ください。 Internet Explorer のサポートと更新は引き続き行われますが、最新の機能更新プログラムとプラットフォーム更新プログラムは Microsoft Edge のみで利用可能になります。

## 新しいバージョンを試しつつ、現在のバージョンの Microsoft Edge (Microsoft Edge レガシ) を並行して実行できますか?

できます。 2020 年 1 月 15 日以降、Windows 10 Version 1803 以降を実行している Home および Pro エディションのデバイスには、Microsoft Edge の新しいバージョン (Chromium ベース) が配布されます。 ドメインに参加しているデバイスは、この更新から除外されます。 詳しくは、[Microsoft Edge 更新プログラムの概要](https://docs.microsoft.com/deployedge/microsoft-edge-blocker-toolkit#overview)をご覧ください。 Microsoft Edge の次のバージョンを評価する際には、Microsoft Edge レガシの並行インストールを使用できます。 詳しくは、「[旧バージョンの Microsoft Edge にアクセスする方法](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-access-old-edge)」をご覧ください。 さらに、新しい各 Microsoft Edge チャネルでも、並行インストールトがサポートされます。 詳しくは、「[Microsoft Edge チャネルの概要](https://docs.microsoft.com/deployedge/microsoft-edge-channels)」をご覧ください。

## Microsoft Edge (Chromium ベース) では、ActiveX コントロールや、Silverlight や Java などの BHO をサポートしていますか。

いいえ、そうではありません。 Microsoft Edge (Chromium ベース) では、ActiveX コントロールや、Silverlight や Java などの BHO をサポートしていません。 ただし、ActiveX コントロール、BHO、または従来のドキュメント モードを使用する Web アプリを Internet Explorer 11 上で実行している場合には、新しい Microsoft Edge 上で IE モードを実行するように構成できます。 詳しくは、「[Microsoft Edge で IE モードを設定する](https://docs.microsoft.com/DeployEdge/edge-ie-mode)」をご覧ください。

## お気に入りは、現在のバージョンの Microsoft Edge から移植できますか? それとも、自分でもう一度追加する必要がありますか?

現時点では、Microsoft Edge では、Microsoft Edge、Chrome、Internet Explorer、Firefox (Win10) の既存のインストールからのインポートがサポートされています。 インポートでは、ブックマーク、履歴、パスワード、オートフィル (支払い、住所、汎用フォーム) の設定がサポートされています。 インポートは、最初の実行エクスペリエンスで実行するか、ブラウザーの設定を使用して実行するかを選択できます。  

## チャネル/ビルドは Stable、Beta、Dev、Canary でどのように違いますか?

Microsoft Edge の次のバージョンの Stable チャネルは、最も安定したプレビュー チャネルであり、組織全体での[パイロットと評価](https://aka.ms/EdgeEnterprise)用にエンタープライズ対応の機能が用意されています。 Beta チャネルを使用すると、代表的なユーザーのグループにより次の Stable リリースを検証できます。 Stable チャネルおよび Beta チャネルは、約 6 週間に 1 回更新されます。 Dev チャネルは毎週、Canary チャネルは毎日更新されます。 オフライン インストーラー (MSI および PKG ファイル) は、Stable チャネル、Beta チャネル、Dev チャネルでのみ利用できます。 詳しくは、「[Microsoft Edge チャネルの概要](https://docs.microsoft.com/deployedge/microsoft-edge-channels)」をご覧ください。

## 新しいバージョンの Microsoft Edge では、どのような拡張機能がサポートされていますか?

Microsoft Edge では、[Microsoft Edge Insider Addons](https://go.microsoft.com/fwlink/?linkid=2081222) および [Chrome ウェブストア](https://go.microsoft.com/fwlink/?linkid=2072338)にある拡張機能がサポートされています。

## モバイル デバイス管理 (MDM) と Microsoft Intune はサポートされていますか?

はい、できます。 Microsoft Intune とモバイル デバイス管理 (MDM) を使用した Windows 10 での Microsoft Edge の構成がサポートされるようになりました。 詳しくは、「[Microsoft Intune を使用して Microsoft Edge を構成する](configure-edge-with-intune.md)」と「[モバイル デバイス管理を使用して Microsoft Edge を構成する](configure-edge-with-mdm.md)」をご覧ください。

## WSUS は、新しい Microsoft Edge の初期展開をサポートしていますか?

いいえ、そうではありません。 WSUS は、既存の Microsoft Edge の MSI インストールを更新することができますが、初期展開には使用できません。 WSUS を介して更新プログラムを完全に管理する必要がある場合は、[ConfigMgr](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json) などの管理ツールを使用して初期展開を実行できます。

## 関連項目

- [Microsoft Edge ドキュメント ランディング ページ](https://docs.microsoft.com/DeployEdge/)
- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
