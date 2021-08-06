---
title: 潜在的に危険なファイルのダウンロードを中断する
ms.author: kvice
author: AndreaLBarr
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 潜在的に危険なファイルのダウンロードを中断する
ms.openlocfilehash: 2c2827185cad83b3878139ee82dcbc8407a2a6eebcf73f69a9481430c29f3db9
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "11727252"
---
# <a name="interrupting-downloads-of-potentially-dangerous-files"></a>潜在的に危険なファイルのダウンロードを中断する

Microsoft Edge のファイルの種類のポリシー コンポーネントを使用すると、ファイルを "危険性" のレベルで分類できるため、無害なファイル (`.txt` ファイルなど) を自由にダウンロードできます。また、潜在的に危険なファイル (`.dll` ファイルなど) は、より高度な検査とセキュリティを重視したユーザー エクスペリエンスの対象となります。

## <a name="determining-the-danger-level-of-a-file-type"></a>ファイルの種類の危険レベルの決定

Microsoft Edge は、ファイルの種類のポリシーをアップストリームの Chromium ブラウザーから継承します。リストの現在の内容は[ここで](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb)確認できます。 リスト内で、各タイプに、`DANGEROUS`、`NOT_DANGEROUS`、または `ALLOW_ON_USER_GESTURE` の 3 つの値のいずれかの danger_level があることがわかります。

最初の 2 つは単純です。**NOT_DANGEROUS** は、ダウンロードが偶発的であったとしても、ファイルを安全にダウンロードできることを意味します。 **DANGEROUS** は、ダウンロードがデバイスに害を及ぼす可能性があることをブラウザーが常にユーザーに警告する必要があることを意味します。

3 番目の設定 **ALLOW_ON_USER_GESTURE** はより微妙です。 このようなファイルは潜在的に危険ですが、ユーザーがダウンロードを要求した場合は、最も無害な可能性があります。 Microsoft Edge では、次の 2 つの条件が満たされた場合に、このようなダウンロードを自動的に続行できます。

1. ダウンロードを開始したネットワーク要求に関連付けられた[ユーザー ジェスチャ](https://textslashplain.com/2020/05/18/browser-basics-user-gestures/)があります (たとえば、ユーザーがダウンロードへのリンクをクリックしたなど)。
2. 直近の午前 0 時 (つまり、昨日またはそれ以前) の前に、参照元 (ダウンロードにリンクしているページ) への事前訪問が記録されています。 これは、ユーザーがサイトにアクセスした履歴があることを意味します。

ユーザーが **[リンクをコンテキスト メニューとして保存]** コマンドを使用して明示的にダウンロードを開始した場合、ダウンロードの URL をブラウザーのアドレス バーに直接入力した場合、または Microsoft Defender SmartScreen がファイルが安全であると示した場合、ダウンロードは自動的に続行されます。

**更新:** バージョン 91 以降、Microsoft Edge は必要なジェスチャが不足しているダウンロードを中断します。

## <a name="user-experience-for-downloads-lacking-gestures"></a>ジェスチャが不足しているダウンロードのユーザー エクスペリエンス

潜在的に危険な種類のダウンロードが、必要なジェスチャなしで開始された場合、Microsoft Edge にダウンロードが "ブロックされました" と表示されます。 `Keep` および `Delete` という名前のコマンドは、以下から入手できます... ダウンロード アイテムのメニューを使用して、ユーザーがダウンロードを続行またはキャンセルできるようにします。

:::image type="content" source="media/microsoft-edge-security-Download-interruptions/Dowload-was-blocked.png" alt-text="ダウンロードがブロックされました":::

`edge://downloads` ページで、ユーザーには同じオプションが表示されます。

:::image type="content" source="media/microsoft-edge-security-Download-interruptions/msg-keep-delete-option.png" alt-text="MSG 保持削除オプション":::

## <a name="enterprise-controls"></a>エンタープライズ コントロール

ユーザーが毎日使用するサイトのダウンロードの中断に遭遇する可能性は低いですが、めったに使用しないサイトの正当なダウンロードの中断に遭遇する可能性があります。 企業のユーザー エクスペリエンスを合理化するために、グループ ポリシーを利用できます。

企業は、[ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) を使用して、特定のサイトから中断することなくダウンロードできるファイルの種類を指定できます。 たとえば、次のポリシーでは、XML ファイルを contoso.com および woodgrovebank.com から中断することなくダウンロードし、MSG ファイルを任意のサイトからダウンロードすることができます。

`[{"file_extension":"xml","domains":["contoso.com", "woodgrovebank.com"]},
{"file_extension":"msg", "domains": ["*"]}]`

## <a name="file-types-requiring-a-gesture"></a>ジェスチャを必要とするファイルの種類

最新の[ファイルの種類のポリシー](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb)は、Chromium ソース コードで公開されています。 2021 年 5 月の時点で、少なくとも 1 つの OS プラットフォームで `danger_level` が `ALLOW_ON_USER_GESTURE` のファイルの種類は次のとおりです。
`crx, pl, py, pyc, pyo, pyw, rb, efi, oxt, msi, msp, mst, ade, adp, mad, maf, mag, mam, maq, mar, mas, mat, mav, maw, mda, mdb, mde, mdt, mdw, mdz, accdb, accde, accdr, accda, ocx, ops, paf, pcd, pif, plg, prf, prg, pst, cpi, partial, xrm-ms, rels, svg, xml, xsl, xsd, ps1, ps1xml, ps2, ps2xml, psc1, psc2, js, jse, vb, vbe, vbs, vbscript, ws, wsc, wsf, wsh, msh, msh1, msh2, mshxml, msh1xml, msh2xml, ad, app, application, appref-ms, asp, asx, bas, bat, chi, chm, cmd, com, cpl, crt, cer, der, eml, exe, fon, fxp, hlp, htt, inf, ins, inx, isu, isp, job, lnk, mau, mht, mhtml, mmc, msc, msg, reg, rgs, scr, sct, search-ms, settingcontent-ms, shb, shs, slk, u3p, vdx, vsx, vtx, vsdx, vssx, vstx, vsdm, vssm, vstm, vsd, vsmacros, vss, vst, vsw, xnk, cdr, dart, dc42, diskcopy42, dmg, dmgpart, dvdr, dylib, img, imgpart, ndif, service, smi, sparsebundle, sparseimage, toast, udif, action, definition, wflow, caction, as, cpgz, command, mpkg, pax, workflow, xip, mobileconfig, configprofile, internetconnect, networkconnect, pkg, deb, pet, pup, rpm, slp, out, run, bash, csh, ksh, sh, shar, tcsh, desktop, dex,apk`

## <a name="danger-level-may-vary-by-operating-system"></a>危険レベルはオペレーティング システムによって異なる場合があります

ファイルの種類の設定は、クライアントの OS プラットフォームによって異なる場合があります。 たとえば、`.exe` は Mac では危険ではありませんが、`.applescript` は Windows では無害です。
