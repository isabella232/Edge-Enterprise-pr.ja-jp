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
ms.openlocfilehash: 527b98b54cf03f6c116624296c63803b57a7f0c4
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642673"
---
# <a name="interrupting-downloads-of-potentially-dangerous-files"></a><span data-ttu-id="1f2e0-103">潜在的に危険なファイルのダウンロードを中断する</span><span class="sxs-lookup"><span data-stu-id="1f2e0-103">Interrupting Downloads of Potentially Dangerous Files</span></span>

<span data-ttu-id="1f2e0-104">Microsoft Edge のファイルの種類のポリシー コンポーネントを使用すると、ファイルを "危険性" のレベルで分類できるため、無害なファイル (`.txt` ファイルなど) を自由にダウンロードできます。また、潜在的に危険なファイル (`.dll` ファイルなど) は、より高度な検査とセキュリティを重視したユーザー エクスペリエンスの対象となります。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-104">Microsoft Edge’s File Type Policies component allows files to be classified by their level of “dangerousness”, such that harmless files (e.g. `.txt` files) can be downloaded freely, whilst potentially-dangerous files (e.g. `.dll` files) are subjected to a higher degree of vetting and a more security-conscious user-experience.</span></span>

## <a name="determining-the-danger-level-of-a-file-type"></a><span data-ttu-id="1f2e0-105">ファイルの種類の危険レベルの決定</span><span class="sxs-lookup"><span data-stu-id="1f2e0-105">Determining the Danger Level of a File Type</span></span>

<span data-ttu-id="1f2e0-106">Microsoft Edge は、ファイルの種類のポリシーをアップストリームの Chromium ブラウザーから継承します。リストの現在の内容は[ここで](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb)確認できます。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-106">Microsoft Edge inherits its file type policies from the upstream Chromium browser; you can view the current contents of the list [here](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb).</span></span> <span data-ttu-id="1f2e0-107">リスト内で、各タイプに、`DANGEROUS`、`NOT_DANGEROUS`、または `ALLOW_ON_USER_GESTURE` の 3 つの値のいずれかの danger_level があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-107">Within the list, you’ll see that each type has a danger_level, which is one of three values: `DANGEROUS`, `NOT_DANGEROUS`, or `ALLOW_ON_USER_GESTURE`.</span></span>

<span data-ttu-id="1f2e0-108">最初の 2 つは単純です。**NOT_DANGEROUS** は、ダウンロードが偶発的であったとしても、ファイルを安全にダウンロードできることを意味します。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-108">The first two are simple: **NOT_DANGEROUS** means that the file is safe to download, even if the download was accidental.</span></span> <span data-ttu-id="1f2e0-109">**DANGEROUS** は、ダウンロードがデバイスに害を及ぼす可能性があることをブラウザーが常にユーザーに警告する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-109">**DANGEROUS** means that the browser should always warn the user that the download may harm their device.</span></span>

<span data-ttu-id="1f2e0-110">3 番目の設定 **ALLOW_ON_USER_GESTURE** はより微妙です。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-110">The third setting **ALLOW_ON_USER_GESTURE** is more subtle.</span></span> <span data-ttu-id="1f2e0-111">このようなファイルは潜在的に危険ですが、ユーザーがダウンロードを要求した場合は、最も無害な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-111">Such files are potentially dangerous, but most likely harmless if the user requested the download.</span></span> <span data-ttu-id="1f2e0-112">Microsoft Edge では、次の 2 つの条件が満たされた場合に、このようなダウンロードを自動的に続行できます。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-112">Microsoft Edge will allow such downloads to proceed automatically if two conditions are met:</span></span>

1. <span data-ttu-id="1f2e0-113">ダウンロードを開始したネットワーク要求に関連付けられた[ユーザー ジェスチャ](https://textslashplain.com/2020/05/18/browser-basics-user-gestures/)があります (たとえば、ユーザーがダウンロードへのリンクをクリックしたなど)。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-113">There is a [user gesture](https://textslashplain.com/2020/05/18/browser-basics-user-gestures/) associated with the network request that initiated the download (e.g., the user clicked a link to the download).</span></span>
2. <span data-ttu-id="1f2e0-114">直近の午前 0 時 (つまり、昨日またはそれ以前) の前に、参照元 (ダウンロードにリンクしているページ) への事前訪問が記録されています。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-114">There is a recorded prior visit to the referring origin (the page linking to the download) prior to the most recent midnight (i.e., yesterday or earlier).</span></span> <span data-ttu-id="1f2e0-115">これは、ユーザーがサイトにアクセスした履歴があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-115">This implies that the user has a history of visiting the site.</span></span>

<span data-ttu-id="1f2e0-116">ユーザーが **[リンクをコンテキスト メニューとして保存]** コマンドを使用して明示的にダウンロードを開始した場合、ダウンロードの URL をブラウザーのアドレス バーに直接入力した場合、または Microsoft Defender SmartScreen がファイルが安全であると示した場合、ダウンロードは自動的に続行されます。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-116">The download will also proceed automatically if the user explicitly initiated it by using the **Save link as** context menu command, entered the download’s URL directly into the browser’s address bar, or if Microsoft Defender SmartScreen indicated that the file is safe.</span></span>

<span data-ttu-id="1f2e0-117">**更新:** バージョン 91 以降、Microsoft Edge は必要なジェスチャが不足しているダウンロードを中断します。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-117">**Update:** Starting in version 91, Microsoft Edge will interrupt downloads that lack the required gesture.</span></span>

## <a name="user-experience-for-downloads-lacking-gestures"></a><span data-ttu-id="1f2e0-118">ジェスチャが不足しているダウンロードのユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="1f2e0-118">User Experience for Downloads Lacking Gestures</span></span>

<span data-ttu-id="1f2e0-119">潜在的に危険な種類のダウンロードが、必要なジェスチャなしで開始された場合、Microsoft Edge にダウンロードが "ブロックされました" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-119">If a download for a potentially dangerous type starts without the required gesture, Microsoft Edge states that the download “was blocked”.</span></span> <span data-ttu-id="1f2e0-120">`Keep` および `Delete` という名前のコマンドは、以下から入手できます...</span><span class="sxs-lookup"><span data-stu-id="1f2e0-120">Commands named `Keep` and `Delete` are available from the …</span></span> <span data-ttu-id="1f2e0-121">ダウンロード アイテムのメニューを使用して、ユーザーがダウンロードを続行またはキャンセルできるようにします。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-121">menu on the download item to allow the user to continue or cancel the download.</span></span>

:::image type="content" source="media/microsoft-edge-security-Download-interruptions/Dowload-was-blocked.png" alt-text="ダウンロードがブロックされました":::

<span data-ttu-id="1f2e0-123">`edge://downloads` ページで、ユーザーには同じオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-123">On the `edge://downloads`, page, the user will see the same options:</span></span>

:::image type="content" source="media/microsoft-edge-security-Download-interruptions/msg-keep-delete-option.png" alt-text="MSG 保持削除オプション":::

## <a name="enterprise-controls"></a><span data-ttu-id="1f2e0-125">エンタープライズ コントロール</span><span class="sxs-lookup"><span data-stu-id="1f2e0-125">Enterprise Controls</span></span>

<span data-ttu-id="1f2e0-126">ユーザーが毎日使用するサイトのダウンロードの中断に遭遇する可能性は低いですが、めったに使用しないサイトの正当なダウンロードの中断に遭遇する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-126">While users are unlikely to encounter download interruptions for sites they use every day, they might encounter them for legitimate downloads on sites that they use rarely.</span></span> <span data-ttu-id="1f2e0-127">企業のユーザー エクスペリエンスを合理化するために、グループ ポリシーを利用できます。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-127">To help streamline the user-experience for Enterprises, a Group Policy is available.</span></span>

<span data-ttu-id="1f2e0-128">企業は、[ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) を使用して、特定のサイトから中断することなくダウンロードできるファイルの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-128">Enterprises can use [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) to specify the filetypes that are allowed to download from specific sites without interruption.</span></span> <span data-ttu-id="1f2e0-129">たとえば、次のポリシーでは、XML ファイルを contoso.com および woodgrovebank.com から中断することなくダウンロードし、MSG ファイルを任意のサイトからダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-129">For instance, the following policy allows XML files to download from contoso.com and woodgrovebank.com without interruption, and MSG files to download from any site.</span></span>

`[{"file_extension":"xml","domains":["contoso.com", "woodgrovebank.com"]},
{"file_extension":"msg", "domains": ["*"]}]`

## <a name="file-types-requiring-a-gesture"></a><span data-ttu-id="1f2e0-130">ジェスチャを必要とするファイルの種類</span><span class="sxs-lookup"><span data-stu-id="1f2e0-130">File Types Requiring a Gesture</span></span>

<span data-ttu-id="1f2e0-131">最新の[ファイルの種類のポリシー](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb)は、Chromium ソース コードで公開されています。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-131">The latest [file types policies](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb) are published in the Chromium source code.</span></span> <span data-ttu-id="1f2e0-132">2021 年 5 月の時点で、少なくとも 1 つの OS プラットフォームで `danger_level` が `ALLOW_ON_USER_GESTURE` のファイルの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-132">As of May 2021, file types with a `danger_level` of `ALLOW_ON_USER_GESTURE` on at least one OS platform include:</span></span>
`crx, pl, py, pyc, pyo, pyw, rb, efi, oxt, msi, msp, mst, ade, adp, mad, maf, mag, mam, maq, mar, mas, mat, mav, maw, mda, mdb, mde, mdt, mdw, mdz, accdb, accde, accdr, accda, ocx, ops, paf, pcd, pif, plg, prf, prg, pst, cpi, partial, xrm-ms, rels, svg, xml, xsl, xsd, ps1, ps1xml, ps2, ps2xml, psc1, psc2, js, jse, vb, vbe, vbs, vbscript, ws, wsc, wsf, wsh, msh, msh1, msh2, mshxml, msh1xml, msh2xml, ad, app, application, appref-ms, asp, asx, bas, bat, chi, chm, cmd, com, cpl, crt, cer, der, eml, exe, fon, fxp, hlp, htt, inf, ins, inx, isu, isp, job, lnk, mau, mht, mhtml, mmc, msc, msg, reg, rgs, scr, sct, search-ms, settingcontent-ms, shb, shs, slk, u3p, vdx, vsx, vtx, vsdx, vssx, vstx, vsdm, vssm, vstm, vsd, vsmacros, vss, vst, vsw, xnk, cdr, dart, dc42, diskcopy42, dmg, dmgpart, dvdr, dylib, img, imgpart, ndif, service, smi, sparsebundle, sparseimage, toast, udif, action, definition, wflow, caction, as, cpgz, command, mpkg, pax, workflow, xip, mobileconfig, configprofile, internetconnect, networkconnect, pkg, deb, pet, pup, rpm, slp, out, run, bash, csh, ksh, sh, shar, tcsh, desktop, dex,apk`

## <a name="danger-level-may-vary-by-operating-system"></a><span data-ttu-id="1f2e0-133">危険レベルはオペレーティング システムによって異なる場合があります</span><span class="sxs-lookup"><span data-stu-id="1f2e0-133">Danger Level May Vary By Operating System</span></span>

<span data-ttu-id="1f2e0-134">ファイルの種類の設定は、クライアントの OS プラットフォームによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-134">File type settings sometimes vary depending on the client OS platform.</span></span> <span data-ttu-id="1f2e0-135">たとえば、`.exe` は Mac では危険ではありませんが、`.applescript` は Windows では無害です。</span><span class="sxs-lookup"><span data-stu-id="1f2e0-135">For instance, an `.exe` is not dangerous on a Mac, while an `.applescript` is harmless on Windows.</span></span>
