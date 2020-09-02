---
title: Microsoft Defender SmartScreen の Microsoft Edge サポート
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 04/23/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Defender SmartScreen の Microsoft Edge サポート
ms.openlocfilehash: d27366409d7792784c360cfee10f96ab174aa375
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980544"
---
# <span data-ttu-id="021ef-103">Microsoft Defender SmartScreen の Microsoft Edge サポート</span><span class="sxs-lookup"><span data-stu-id="021ef-103">Microsoft Edge support for Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="021ef-104">この記事では、Microsoft Defender SmartScreen を使用する利点、その機能、およびこの Microsoft Edge 機能の構成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="021ef-104">This article describes the benefits of using Microsoft Defender SmartScreen, explains how it works, and describes how to configure this Microsoft Edge feature.</span></span>

> [!NOTE]
> <span data-ttu-id="021ef-105">この記事は Microsoft Edge version 77 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="021ef-105">This article applies to Microsoft Edge version 77 or later.</span></span>

<span data-ttu-id="021ef-106">Microsoft Defender SmartScreen は、Microsoft Edge が Web の閲覧中に安全を確保するために使用するサービスです。</span><span class="sxs-lookup"><span data-stu-id="021ef-106">Microsoft Defender SmartScreen is a service that Microsoft Edge uses to keep you safe while you browse the web.</span></span> <span data-ttu-id="021ef-107">Microsoft Defender SmartScreen は、フィッシング攻撃に関係している可能性のある Web サイトや、集中的な攻撃によってマルウェアを配布しようとしている Web サイトに対抗する、早期警告システムの提供に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="021ef-107">Microsoft Defender SmartScreen provides an early warning system against websites that might engage in phishing attacks or attempt to distribute malware through a focused attack.</span></span>

> [!NOTE]
> <span data-ttu-id="021ef-108">Windows 10 Version 1703 より前のバージョンでは、この機能がブラウザー内で使われるときは SmartScreen フィルターと呼ばれ、ブラウザーの外部で使われるときは Microsoft SmartScreen と呼ばれていました。</span><span class="sxs-lookup"><span data-stu-id="021ef-108">Before Windows 10, version 1703, this feature was called the SmartScreen filter when used within the browser and Microsoft SmartScreen when used outside of the browser.</span></span>

## <span data-ttu-id="021ef-109">Microsoft Defender SmartScreen の利点</span><span class="sxs-lookup"><span data-stu-id="021ef-109">The benefits of Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="021ef-110">Microsoft Defender SmartScreen にはいくつかの利点があり、それらを以下のリストに要約します。</span><span class="sxs-lookup"><span data-stu-id="021ef-110">Microsoft Defender SmartScreen provides several benefits, which are summarized in the following list.</span></span> <span data-ttu-id="021ef-111">これらの利点については、[ Microsoft Defender SmartScreen のドキュメント](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview#benefits-of-windows-defender-smartscreen)で詳しく説明されています。</span><span class="sxs-lookup"><span data-stu-id="021ef-111">These benefits are described in detail in the [Microsoft Defender SmartScreen documentation](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview#benefits-of-windows-defender-smartscreen).</span></span> <span data-ttu-id="021ef-112">利点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="021ef-112">The benefits are:</span></span>

- <span data-ttu-id="021ef-113">フィッシング詐欺対策およびマルウェア対策のサポート</span><span class="sxs-lookup"><span data-stu-id="021ef-113">Anti-phishing and anti-malware support</span></span>
- <span data-ttu-id="021ef-114">評判ベースの URL とアプリの保護</span><span class="sxs-lookup"><span data-stu-id="021ef-114">Reputation-based URL and app protection</span></span>
- <span data-ttu-id="021ef-115">オペレーティング システムとの統合</span><span class="sxs-lookup"><span data-stu-id="021ef-115">Operating system integration</span></span>
- <span data-ttu-id="021ef-116">強化されたヒューリスティックと診断データ</span><span class="sxs-lookup"><span data-stu-id="021ef-116">Improved heuristics and diagnostic data</span></span>
- <span data-ttu-id="021ef-117">グループ ポリシーと Microsoft Intune による管理</span><span class="sxs-lookup"><span data-stu-id="021ef-117">Management through Group Policy and Microsoft Intune</span></span>
- <span data-ttu-id="021ef-118">望ましくない可能性があるアプリケーションと関連付けられている URL のブロック</span><span class="sxs-lookup"><span data-stu-id="021ef-118">Blocking URLs associated with potentially unwanted applications</span></span>

## <span data-ttu-id="021ef-119">Microsoft Defender SmartScreen の仕組みを理解する</span><span class="sxs-lookup"><span data-stu-id="021ef-119">Understand how Microsoft Defender SmartScreen works</span></span>

<span data-ttu-id="021ef-120">Microsoft Defender SmartScreen の警告には、いくつかの入力が含まれています。</span><span class="sxs-lookup"><span data-stu-id="021ef-120">A number of inputs contribute to Microsoft Defender SmartScreen warnings.</span></span> <span data-ttu-id="021ef-121">データは、ユーザー フィードバック、データ プロバイダー、インテリジェンス モデルなど、多くのソースから受信されます。</span><span class="sxs-lookup"><span data-stu-id="021ef-121">Data is received from many sources, including user feedback, data providers, and intelligence models.</span></span> <span data-ttu-id="021ef-122">このデータは、潜在的に悪意のあるコンテンツを特定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="021ef-122">This data is used to help identify potentially malicious content.</span></span> <span data-ttu-id="021ef-123">Microsoft Defender SmartScreen は、ダウンロードされたアプリまたはアプリ インストーラーをチェックして、それらが悪意のあるものかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="021ef-123">Microsoft Defender SmartScreen also checks downloaded apps or app installers to see if they're malicious.</span></span> <span data-ttu-id="021ef-124">どちらのシナリオでも、Microsoft Defender SmartScreen は不審なコンテンツについてユーザーに適切に警告します。</span><span class="sxs-lookup"><span data-stu-id="021ef-124">In both scenarios, Microsoft Defender SmartScreen warns users appropriately about suspicious content.</span></span>

### <span data-ttu-id="021ef-125">サイト分析</span><span class="sxs-lookup"><span data-stu-id="021ef-125">Site analysis</span></span>

<span data-ttu-id="021ef-126">Microsoft Defender SmartScreen では、サイトに悪意があると考えられるかどうかを次のように判断します:</span><span class="sxs-lookup"><span data-stu-id="021ef-126">Microsoft Defender SmartScreen determines whether a site is potentially malicious by:</span></span>

- <span data-ttu-id="021ef-127">不審な動作の兆候がないか、アクセスした Web ページを分析します。</span><span class="sxs-lookup"><span data-stu-id="021ef-127">Analyzing visited webpages for indications of suspicious behavior.</span></span>
- <span data-ttu-id="021ef-128">アクセスしたサイトを、報告されているフィッシング詐欺サイトの動的な記録と照合します。</span><span class="sxs-lookup"><span data-stu-id="021ef-128">Checking the visited sites against a dynamic record of reported phishing sites.</span></span>

<span data-ttu-id="021ef-129">Microsoft Defender SmartScreen がページが悪意のあるものであると判断した場合、そのサイトが安全でないと報告されていることをユーザーに通知する警告ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="021ef-129">If Microsoft Defender SmartScreen determines that a page is malicious, it will show a warning page to notify the user that that site is reported as unsafe.</span></span> <span data-ttu-id="021ef-130">次のスクリーンショットは、ユーザーが悪意のある Web サイトを開こうとしたときの Microsoft Defender SmartScreen 警告ページの例です。</span><span class="sxs-lookup"><span data-stu-id="021ef-130">The next screenshot shows an example of a Microsoft Defender SmartScreen warning page when a user tries to open a malicious website.</span></span>

![外部サイトへのリンクの Microsoft Defender SmartScreen ブロック ページ](media/microsoft-edge-security-smartscreen/microsoft-edge-smartscreen-warning.png)

<span data-ttu-id="021ef-132">ユーザーには、警告メッセージ内でサイトを安全または危険であると報告するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="021ef-132">Users are given the option of reporting a site as safe or unsafe within the warning message.</span></span> <span data-ttu-id="021ef-133">詳細については、「[サイトの報告方法](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-set-individual-device#how-users-can-report-websites-as-safe-or-unsafe)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="021ef-133">For more information, see [how to report a site](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-set-individual-device#how-users-can-report-websites-as-safe-or-unsafe).</span></span>

### <span data-ttu-id="021ef-134">ファイル分析</span><span class="sxs-lookup"><span data-stu-id="021ef-134">File analysis</span></span>

<span data-ttu-id="021ef-135">Microsoft Defender SmartScreen は、ダウンロード トラフィック、ダウンロード履歴、過去のウイルス対策の結果、URL 評判などの多くの基準に基づいて、ダウンロードされたアプリまたはアプリ インストーラーが悪意のある可能性があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="021ef-135">Microsoft Defender SmartScreen determines whether a downloaded app or app installer is potentially malicious based on many criteria, such as download traffic, download history, past anti-virus results, and URL reputation.</span></span>

- <span data-ttu-id="021ef-136">安全であることがわかっているファイルは、通知なしでダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="021ef-136">Files with a known safe reputation will download without any notification.</span></span>  
- <span data-ttu-id="021ef-137">悪意のあることがわかっているファイルには、ファイルが安全ではなく、悪意があると報告されていることをユーザーに知らせる警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="021ef-137">Files with a known malicious reputation show a warning to let the user know that the file is unsafe and has been reported as malicious.</span></span> <span data-ttu-id="021ef-138">次のスクリーンショットは、悪意のあるファイルに対する警告の例です。</span><span class="sxs-lookup"><span data-stu-id="021ef-138">The next screenshot is an example of a warning for a malicious file.</span></span>

  ![悪意のあることがわかった Microsoft Defender SmartScreen ブロック ページ ファイル](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-known-malicious.png)

- <span data-ttu-id="021ef-140">不明なファイルは、ダウンロードに既知のフットプリントがないことをユーザーに通知し、注意を促す警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="021ef-140">Files that are unknown show a warning to let the user know that the download doesn't have a known footprint and advise caution.</span></span> <span data-ttu-id="021ef-141">次のスクリーンショットは、不明なファイルに対する警告の例です。</span><span class="sxs-lookup"><span data-stu-id="021ef-141">The next screenshot is an example of a warning for an unknown file.</span></span>

  ![悪意のあることがわかった Microsoft Defender SmartScreen ブロック ページ ファイル](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-unknown-malicious.png)

<span data-ttu-id="021ef-143">すべての不明なプログラムが悪意があるとは限りません。不明な警告は、特に警告が予期しないものである場合に、それを必要とするユーザーにコンテキストとガイダンスを提供することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="021ef-143">Not all unknown programs are malicious, and the unknown warning is intended to provide context and guidance for users who need it, especially if the warning is unexpected.</span></span>

  ![悪意のあることがわかったファイルを保持する](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-unknown-malicious-keep.png)

<span data-ttu-id="021ef-145">ただし、ユーザーは **[...]、[保持]、[詳細表示]、[保持]** の順にクリックしてアプリケーションをダウンロードして実行できます。</span><span class="sxs-lookup"><span data-stu-id="021ef-145">However, users can still download and run the application by clicking **... | Keep | Show More | Keep anyway**.</span></span>

> [!TIP]
> **<span data-ttu-id="021ef-146">企業の顧客向けの参考情報です。</span><span class="sxs-lookup"><span data-stu-id="021ef-146">FYI for Enterprise Customers.</span></span>** <span data-ttu-id="021ef-147">既定では、ユーザーが Microsoft Defender SmartScreen の警告をバイパスできるようになっています。</span><span class="sxs-lookup"><span data-stu-id="021ef-147">By default, Microsoft Defender SmartScreen lets users bypass warnings.</span></span> <span data-ttu-id="021ef-148">このユーザー操作は危険を伴う可能性があるため、これらの[推奨されるグループ ポリシー設定](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-available-settings#recommended-group-policy-and-mdm-settings-for-your-organization)を確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="021ef-148">Because this user interaction is potentially risky, we recommend that you review these [recommended group policy settings](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-available-settings#recommended-group-policy-and-mdm-settings-for-your-organization).</span></span>

<span data-ttu-id="021ef-149">Microsoft Defender SmartScreen が、[デモ サイト](https://demo.smartscreen.msft.net/)を使用してさまざまなシナリオにどのように対応するかがわかります。</span><span class="sxs-lookup"><span data-stu-id="021ef-149">You see how Microsoft Defender SmartScreen responds to different scenarios using our [demo site](https://demo.smartscreen.msft.net/).</span></span>

## <span data-ttu-id="021ef-150">Microsoft Defender SmartScreen とユーザーのプライバシー</span><span class="sxs-lookup"><span data-stu-id="021ef-150">Microsoft Defender SmartScreen and user privacy</span></span>

<span data-ttu-id="021ef-151">Microsoft Defender SmartScreen は、評判チェック システムを使用してインターネットを閲覧しているユーザーを保護します。</span><span class="sxs-lookup"><span data-stu-id="021ef-151">Microsoft Defender SmartScreen protects users while they browse the Internet by using a reputation check system.</span></span> <span data-ttu-id="021ef-152">Microsoft Edge は、評判チェックを開始するために、URL またはファイルに関する関連情報を Microsoft Defender SmartScreen サービスに渡します。</span><span class="sxs-lookup"><span data-stu-id="021ef-152">Microsoft Edge passes relevant information about the URL or file to the Microsoft Defender SmartScreen service to start the reputation check.</span></span> <span data-ttu-id="021ef-153">このチェックでは、Web サイトまたはファイルを、危険であることがわかっているサイトおよびファイルの動的リストと比較します。</span><span class="sxs-lookup"><span data-stu-id="021ef-153">The check compares the website or file against dynamic lists of sites and files that are known to be dangerous.</span></span> <span data-ttu-id="021ef-154">Microsoft Defender SmartScreen サービスへのすべての要求は、TLS 暗号化で行われます。</span><span class="sxs-lookup"><span data-stu-id="021ef-154">All requests to the Microsoft Defender SmartScreen service are made with TLS encryption.</span></span> <span data-ttu-id="021ef-155">サービスは評判チェックの結果を返します。これにより、Microsoft Edge がサイトまたはファイルの警告を表示する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="021ef-155">The service returns the results of the reputation check, which might lead to Microsoft Edge showing a warning for the site or file.</span></span> <span data-ttu-id="021ef-156">これらの結果は、デバイスのローカルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="021ef-156">These results are stored locally on the device.</span></span>

<span data-ttu-id="021ef-157">Microsoft Defender SmartScreen サービスは、評判チェックに関するデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="021ef-157">The Microsoft Defender SmartScreen service stores data about reputation checks.</span></span> <span data-ttu-id="021ef-158">新しいサイトが識別されると、サービスは既知の悪意のある URL とファイルの動的データベースに追加します。</span><span class="sxs-lookup"><span data-stu-id="021ef-158">As new sites are identified, the service adds to a dynamic database of known malicious URLs and files.</span></span> <span data-ttu-id="021ef-159">このデータは安全な Microsoft サーバーに保存され、Microsoft セキュリティ サービスでのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="021ef-159">This data is stored on secure Microsoft servers and is only used for Microsoft security services.</span></span> <span data-ttu-id="021ef-160">このデータは、決してユーザーの識別やターゲット設定に使用されることはありません。</span><span class="sxs-lookup"><span data-stu-id="021ef-160">This data will never be used to identify or target users in any way.</span></span> <span data-ttu-id="021ef-161">ブラウジング キャッシュをクリアすると、ローカルに保存されているすべての Microsoft Defender SmartScreen URL データがクリアされます。</span><span class="sxs-lookup"><span data-stu-id="021ef-161">Clearing browsing cache clears all locally stored Microsoft Defender SmartScreen URL data.</span></span> <span data-ttu-id="021ef-162">ダウンロード履歴をクリアすると、ファイルのダウンロードに関するローカルに保存されている SmartScreen データが削除されます。</span><span class="sxs-lookup"><span data-stu-id="021ef-162">Clearing download history will remove any locally stored SmartScreen data about file downloads.</span></span>

<span data-ttu-id="021ef-163">Microsoft Defender SmartScreen と Microsoft Edge でのプラ​​イバシーの詳細については、「[Microsoft Edge プライバシー ホワイトペーパー](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper#smartscreen)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="021ef-163">For more information about Microsoft Defender SmartScreen and privacy on Microsoft Edge, read the [Microsoft Edge Privacy Whitepaper](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper#smartscreen).</span></span>

## <span data-ttu-id="021ef-164">管理者向けの Microsoft Defender SmartScreen セットアップ</span><span class="sxs-lookup"><span data-stu-id="021ef-164">Microsoft Defender SmartScreen setup for admins</span></span>

<span data-ttu-id="021ef-165">管理者は、グループ ポリシー、Microsoft Intune、またはモバイル デバイス管理 (MDM) の設定を使用して、Microsoft Defender SmartScreen を構成できます。</span><span class="sxs-lookup"><span data-stu-id="021ef-165">Admins can configure Microsoft Defender SmartScreen using Group Policy, Microsoft Intune, or mobile device management (MDM) settings.</span></span> <span data-ttu-id="021ef-166">Microsoft Defender SmartScreen をどのように設定するかによって、ユーザーに警告ページを表示してからサイトへのアクセスを許可するか、サイトを完全にブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="021ef-166">Based on how you set up Microsoft Defender SmartScreen, you can show users a warning page and let them continue to the site or block the site entirely.</span></span>

### <span data-ttu-id="021ef-167">グループ ポリシーを使用してセットアップされた Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="021ef-167">Microsoft Defender SmartScreen set up using Group Policy</span></span>

<span data-ttu-id="021ef-168">SmartScreen ポリシーの完全なリストについては、「[Microsoft Defender SmartScreen 設定](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreen-settings)」を参照してください</span><span class="sxs-lookup"><span data-stu-id="021ef-168">For a complete list of SmartScreen policies, see [Microsoft Defender SmartScreen settings](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreen-settings)</span></span>

### <span data-ttu-id="021ef-169">MDM を使用してセットアップされた Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="021ef-169">Microsoft Defender SmartScreen set up using MDM</span></span>

<span data-ttu-id="021ef-170">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="021ef-170">For more information, see:</span></span>

- [<span data-ttu-id="021ef-171">Microsoft Defender SmartScreen の Windows Intune 設定</span><span class="sxs-lookup"><span data-stu-id="021ef-171">Windows Intune settings for Microsoft Defender SmartScreen</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#windows-defender-smartscreen-settings)
- [<span data-ttu-id="021ef-172">MDM ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="021ef-172">MDM policy settings</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#windows-defender-smartscreen-settings)

## <span data-ttu-id="021ef-173">ユーザー向けの Microsoft Defender SmartScreen セットアップ</span><span class="sxs-lookup"><span data-stu-id="021ef-173">Microsoft Defender SmartScreen setup for users</span></span>

<span data-ttu-id="021ef-174">Microsoft Defender SmartScreen は、Microsoft Edge では既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="021ef-174">Microsoft Defender SmartScreen is turned on by default for Microsoft Edge.</span></span> <span data-ttu-id="021ef-175">Microsoft Defender SmartScreen をオフにするには、*edge://settings/privacy > Services > Microsoft Defender SmartScreen* に移動します。</span><span class="sxs-lookup"><span data-stu-id="021ef-175">To turn off Microsoft Defender SmartScreen, go to *edge://settings/privacy > Services > Microsoft Defender SmartScreen*.</span></span> <span data-ttu-id="021ef-176">この設定は、デバイスへの Microsoft Edge のインストールに関連付けられているすべてのプロファイルで同じです。</span><span class="sxs-lookup"><span data-stu-id="021ef-176">This setting is the same for all profiles associated with the installation of Microsoft Edge on a device.</span></span> <span data-ttu-id="021ef-177">この設定はデバイス間で同期されません。</span><span class="sxs-lookup"><span data-stu-id="021ef-177">This setting is not synced across devices.</span></span> <span data-ttu-id="021ef-178">この設定は、InPrivate ブラウズとゲスト モードに適用されます。</span><span class="sxs-lookup"><span data-stu-id="021ef-178">The setting applies to InPrivate browsing and Guest mode.</span></span> <span data-ttu-id="021ef-179">デバイスが組織によって設定されたグループ ポリシーで管理されている場合、この構成は *edge://settings/privacy* に反映されます。</span><span class="sxs-lookup"><span data-stu-id="021ef-179">If a device is managed with group policies set by an organization, this configuration will be reflected in *edge://settings/privacy*.</span></span>

> [!NOTE]
> <span data-ttu-id="021ef-180">ユーザーは、グループ ポリシーまたは MDM がそれを防ぐように構成されていない限り、個々のデバイスに対して Microsoft Defender SmartScreen をセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="021ef-180">Users can set up Microsoft Defender SmartScreen for an individual device unless Group Policy or MDM is configured to prevent it.</span></span> <span data-ttu-id="021ef-181">詳細については、「[個々のデバイスでの Microsoft Defender SmartScreen のセットアップと使用](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-set-individual-device)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="021ef-181">For more information, see [set up and use Microsoft Defender SmartScreen on individual devices](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-set-individual-device).</span></span>

## <span data-ttu-id="021ef-182">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="021ef-182">Frequently asked questions</span></span>

### <span data-ttu-id="021ef-183">評判チェック システムはどのように機能しますか?</span><span class="sxs-lookup"><span data-stu-id="021ef-183">How does the reputation check system work?</span></span>

<span data-ttu-id="021ef-184">Web を閲覧すると、Microsoft Defender SmartScreen は Web サイトとダウンロードを上位トラフィック、危険、または不明として分類します。</span><span class="sxs-lookup"><span data-stu-id="021ef-184">As you browse the web, Microsoft Defender SmartScreen categorizes websites and downloads as top traffic, dangerous, or unknown.</span></span> <span data-ttu-id="021ef-185">上位トラフィックは、Microsoft Defender SmartScreen が信頼できると判断した人気のあるサイトです。</span><span class="sxs-lookup"><span data-stu-id="021ef-185">Top traffic is popular sites that Microsoft Defender SmartScreen has determined are trustworthy.</span></span> <span data-ttu-id="021ef-186">危険とマークされたサイトにアクセスすると、Microsoft Defender SmartScreen はすぐにサイトへのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="021ef-186">If you go to a site marked as dangerous, Microsoft Defender SmartScreen immediately blocks you from accessing the site.</span></span> <span data-ttu-id="021ef-187">不明なサイトにアクセスすると、Microsoft DefenderSmartScreen はその評判をチェックして、サイトにアクセスする必要があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="021ef-187">When you go to an unknown site, Microsoft DefenderSmartScreen checks its reputation to determine if you should access the site.</span></span>

## <span data-ttu-id="021ef-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="021ef-188">See also</span></span>

- [<span data-ttu-id="021ef-189">Microsoft Edge Enterprise ランディング ページ</span><span class="sxs-lookup"><span data-stu-id="021ef-189">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="021ef-190">Microsoft Defender SmartScreen の概要</span><span class="sxs-lookup"><span data-stu-id="021ef-190">Microsoft Defender SmartScreen Overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)
- [<span data-ttu-id="021ef-191">脅威の防止</span><span class="sxs-lookup"><span data-stu-id="021ef-191">Threat protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/index)
- [<span data-ttu-id="021ef-192">望ましくない可能性のあるアプリケーションから保護する</span><span class="sxs-lookup"><span data-stu-id="021ef-192">Protect against potentially unwanted applications</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-potentially-unwanted-apps)