---
title: Uzaktan hata ayıklayıcı yükleme
description: Uzaktan hata ayıklayıcı için karşıdan yükleme bağlantıları
services: ''
author: mikejo5000
ms.service: ''
ms.topic: include
ms.date: 05/23/2018
ms.author: mikejo
ms.custom: include file
ms.openlocfilehash: 1e90a1d9e03892cf81bd2257d3dcc6e25ab36246
ms.sourcegitcommit: 748d9cd7328a30f8c80ce42198a94a4b5e869f26
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2019
ms.locfileid: "68149191"
---
Uzak cihaz üzerinde hata ayıklamak istediğiniz sunucu yerine veya Visual Studio makinesine, indirin ve aşağıdaki tabloda bağlantıları uzak araçların doğru sürümünü yükleyin.

- Visual Studio sürümünüz için en son uzak Araçlar'ı indirin. En son uzak Araçlar sürümü, önceki Visual Studio sürümleriyle uyumludur, ancak uzak Araçlar sürümlerde daha yeni Visual Studio sürümleriyle uyumlu değil. (Visual Studio 2017'yi kullanıyorsanız, örneğin, Visual Studio 2017 için Uzak Araçlar'ın en son güncelleştirmeyi indirin. Bu senaryoda, uzak araçlar için Visual Studio 2019 yüklemeyin.)
- Üzerinde yüklüyorsanız makine aynı mimarisine sahip uzak Araçları'nı indirin. Örneğin, bir 64-bit işletim sistemi çalıştıran bir uzak bilgisayarda bir 32-bit uygulamanın hatalarını ayıklamak istiyorsanız, 64-bit uzak Araçları'nı yükleme.

::: moniker range=">=vs-2019"

|Sürüm|Bağlantı|Notlar|
|-|-|-|
|Visual Studio 2019|[Uzak Araçlar](https://visualstudio.microsoft.com/downloads#remote-tools-for-visual-studio-2019)|Tüm Visual Studio 2019 sürümlerle uyumludur. Cihaz işletim sisteminiz (x 86, x64 veya ARM64) eşleşen sürümünü indirin. Windows Server'da bkz [dosya indirme engellemesini](../../debugger/remote-debugging-unblock-file-download.md) uzak araçları yükleme konusunda yardım almak için.|
|Visual Studio 2017|[Uzak Araçlar](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202017)|Tüm Visual Studio 2017 sürümleri ile uyumludur. Cihaz işletim sisteminiz (x 86, x64 veya ARM64) eşleşen sürümünü indirin. Windows Server'da bkz [dosya indirme engellemesini](../../debugger/remote-debugging-unblock-file-download.md) uzak araçları yükleme konusunda yardım almak için.|
|Visual Studio 2015|[Uzak Araçlar](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202015)|Visual Studio 2015 için Uzak Araçlar, My.VisualStudio.com kullanılabilir. İstenirse, ücretsiz katılın [Visual Studio Dev Essentials](https://visualstudio.microsoft.com/dev-essentials/) program ya da Visual Studio abonelik kimliğinizle oturum açın. Windows Server'da bkz [dosya indirme engellemesini](../../debugger/remote-debugging-unblock-file-download.md) uzak araçları yükleme konusunda yardım almak için.|
|Visual Studio 2013|[Uzak Araçlar](/previous-versions/visualstudio/visual-studio-2013/bt727f1t(v=vs.120)#installing-the-remote-tools)|Visual Studio 2013 belgeleri sayfasında indirin|
|Visual Studio 2012|[Uzak Araçlar](/previous-versions/visualstudio/visual-studio-2012/bt727f1t(v=vs.110)#installing-the-remote-tools)|Visual Studio 2012 belgeleri sayfasında indirin|

::: moniker-end

::: moniker range="vs-2017"

|Sürüm|Bağlantı|Notlar|
|-|-|-|
|Visual Studio 2017|[Uzak Araçlar](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202017)|Tüm Visual Studio 2017 sürümleri ile uyumludur. Cihaz işletim sisteminiz (x 86, x64 veya ARM64) eşleşen sürümünü indirin. Windows Server'da bkz [dosya indirme engellemesini](../../debugger/remote-debugging-unblock-file-download.md) uzak araçları yükleme konusunda yardım almak için. Uzak Araçlar'ın en son sürümü için açık [Visual Studio 2019 doc](../../debugger/remote-debugging.md?view=vs-2019).|
|Visual Studio 2015|[Uzak Araçlar](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202015)|Visual Studio 2015 için Uzak Araçlar, My.VisualStudio.com kullanılabilir. İstenirse, ücretsiz katılın [Visual Studio Dev Essentials](https://visualstudio.microsoft.com/dev-essentials/) program ya da Visual Studio abonelik kimliğinizle oturum açın. Windows Server'da bkz [dosya indirme engellemesini](../../debugger/remote-debugging-unblock-file-download.md) uzak araçları yükleme konusunda yardım almak için.|
|Visual Studio 2013|[Uzak Araçlar](/previous-versions/visualstudio/visual-studio-2013/bt727f1t(v=vs.120)#installing-the-remote-tools)|Visual Studio 2013 belgeleri sayfasında indirin|
|Visual Studio 2012|[Uzak Araçlar](/previous-versions/visualstudio/visual-studio-2012/bt727f1t(v=vs.110)#installing-the-remote-tools)|Visual Studio 2012 belgeleri sayfasında indirin|

::: moniker-end

Uzaktan hata ayıklayıcı kopyalayarak çalıştırabileceğiniz *msvsmon.exe* uzak araçları yükleme yerine uzak bilgisayar. Ancak, uzaktan hata ayıklayıcı Yapılandırma Sihirbazı'nı (*rdbgwiz.exe*) yalnızca uzak araçları yüklediğinizde kullanılabilir. Uzaktan hata ayıklayıcıyı bir hizmet olarak çalıştırmak istiyorsanız sihirbazın yapılandırmasını kullanmanız gerekebilir. Daha fazla bilgi için [(isteğe bağlı) yapılandırma hizmet olarak uzaktan hata ayıklayıcı](../../debugger/remote-debugging.md#bkmk_configureService).

>[!NOTE]
>- Windows 10 uygulamaları ARM cihazları üzerinde hata ayıklamak için Uzak Araçlar'ın en son sürümüyle kullanılabilir olduğu, ARM64'nı kullanın.
>- Windows 10 uygulamaları Windows RT cihazlarında hata ayıklamak için yalnızca Visual Studio uzak araçları indirmek 2015'te kullanılabilir olan ARM kullanın.
