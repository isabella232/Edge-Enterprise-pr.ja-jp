---
title: Windows 10 更新プログラムを適用した Microsoft Edge の展開
ms.author: ryhecht
author: RyanHechtMSFT
manager: tinad
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Windows 10 更新プログラムを適用した Microsoft Edge の展開
ms.openlocfilehash: c8ea65f6c452b52b01c00d8fca418fe59db801b1
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447381"
---
# <a name="deploy-microsoft-edge-with-windows-10-updates"></a>Windows 10 更新プログラムを適用した Microsoft Edge の展開

この記事では、Windows 10 更新プログラムを使用して Microsoft Edge を展開しているユーザー向け情報を提供します。

## <a name="for-windows-10-release-20h2"></a>Windows 10 リリース 20H2 の場合

Windows 10 バージョン 20H2 には、Microsoft Edge が既定のブラウザーとして既にインストールされています。

## <a name="for-windows-10-releases-rs4-through-20h1"></a>Windows 10 の場合、RS4 から 20H1 をリリースします

Windows Server Update Services (WSUS) には、Microsoft Edge レガシ デスクトップ アプリを削除して Microsoft Edge に置き換える、RS4 から 20H1 への Windows 10 の各バージョンの更新プログラムが含まれています。 詳しくは、[このサポート記事](https://support.microsoft.com/topic/update-in-wsus-for-the-new-microsoft-edge-for-windows-10-version-1809-1903-1909-and-2004-october-29-2020-b4980418-4ec4-dee7-3b17-1c6499bd127c)を参照して、Windows バージョンに最適な WSUS 更新プログラムを確認してください。

## <a name="for-windows-10-releases-prior-to-rs4-and-windows-7-81-and-earlier"></a>RS4 より前の Windows 10 リリース (および Windows 7、8.1 以前) の場合

Microsoft Edge をインストールする Windows 更新プログラムは、これらのバージョンでは利用できません。 [Configuration Manager](/configmgr/apps/deploy-use/deploy-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json) や[ Intune](/intune/apps/apps-windows-edge/?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json) など、これらのデバイスに Microsoft Edge を展開するためのその他のオプションを検討します。

## <a name="see-also"></a>関連項目

- [Microsoft Edge Enterprise ランディング ページ](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge の展開を計画する](deploy-edge-plan-deployment.md)