---
title: Visual Studio 2017 ' de hata ayıklayıcıdaki yenilikler | Microsoft Docs
titleSuffix: ''
ms.date: 01/22/2018
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, what's new
- what's new [debugger]
- debugging [Visual Studio], what's new
- what's new [Visual Studio], debugging
ms.assetid: 2aed9caa-2384-4e49-8595-82d8b06cf271
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
monikerRange: vs-2017
ms.openlocfilehash: 523867a8f9aa074e9122c74deb8bcd91cddd8bee
ms.sourcegitcommit: 9a66f1c31cc9eba0b5231af72da1d18761a9c56a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/14/2020
ms.locfileid: "75944224"
---
# <a name="whats-new-for-the-debugger-in-visual-studio-2017"></a>Visual Studio 2017 ' de hata ayıklayıcıdaki yenilikler

Hata ayıklayıcı şu yeni özellikleri içerir:

- Sürüm 15,5 ' deki yenilikler **Snapshot Debugger** , çalışırken ilgilendiğiniz kod olduğunda üretim içi uygulamalarınızın anlık görüntüsünü alır. Bir anlık görüntüsünü almak için hata ayıklayıcı açmasını sağlamak için anlık görüntü noktaları ve günlüğe kaydetme noktaları kodunuzda ayarlayın. Hata ayıklayıcı, tam olarak üretim uygulamanızın trafiğini etkilemeden, çıktığına görmenizi sağlar. Snapshot Debugger, üretim ortamlarında ortaya çıkan sorunları çözmek için gereken süreyi ciddi ölçüde azaltmaya yardımcı olabilir.

    Anlık görüntü koleksiyonunu, Azure App Service'te çalışan aşağıdaki web uygulamaları için kullanılabilir:

  * .NET Framework 4.6.1 üzerinde çalışan ASP.NET uygulamalarından veya üzeri.
  * .NET Core 2.0 veya daha sonra Windows üzerinde çalışan ASP.NET Core uygulamaları.

    Daha fazla bilgi için bkz. [Snapshot Debugger kullanarak canlı ASP.NET uygulamalarında hata ayıklama](../debugger/debug-live-azure-applications.md).

- Sürüm 15,5 ' deki yenilikler yalnızca Visual Studio Enterprise sürümünde, **IntelliTrace adım geri** otomatik olarak her kesme noktası ve hata ayıklayıcı adım olayında uygulamanızın anlık görüntüsünü alır. Kaydedilen anlık görüntü, önceki kesme noktaları veya adımlara geri dönün ve daha önce olduğu gibi uygulama durumunu görüntülemek etkinleştirin. IntelliTrace geri adım atma önceki uygulama durumu görmek istiyorsanız ancak hata ayıklamayı yeniden başlatın veya istenen uygulama durumu yeniden istemediğiniz durumlarda size zaman kazandırabilir.

    Hata ayıklama araç çubuğundaki **geri** ve **adım ileri** düğmelerini kullanarak anlık görüntülerle gezinerek görüntüleyebilirsiniz. Bu düğmeler **Tanılama araçları** penceresindeki **Olaylar** sekmesinde görüntülenen olaylara gider.

    ![Geri adımla ve Ilet düğmeleri](../debugger/media/intellitrace-step-back-icons-description.png  "Geri adımla ve Ilet düğmeleri")

    Daha fazla bilgi için bkz. [IntelliTrace kullanarak önceki uygulama durumlarını İnceleme](view-historical-application-state.md) sayfası.

- **Özel** durum Yardımcısı özel durum yardımcısını değiştirir ve hatanın gerçekleştiği kalıcı olmayan bir iletişim kutusunda görünür. **Özel durum Yardımcısı** , tüm iç özel durumlara daha hızlı erişim sağlar, hata ayıklayıcı tarafından ek analizler (varsa) ve özel durum **ayarlarına** anında erişin. Özel durum Yardımcısı, görmeniz gereken bir şeyi engelliyorsa, bir kayan görünüme de sürüklenebilir.

    Örneğin, bir **NullReferenceException** artık null başvurusu olan değişkeni gösterir (ek bilgi).

    ![Hata ayıklayıcının özel durum Yardımcısı](../debugger/media/dbg-exception-helper.png "DbgExceptionHelper")

    Daha fazla bilgi için bkz. [Visual Studio 'Da yeni özel durum yardımcısını kullanma](https://devblogs.microsoft.com/devops/using-the-new-exception-helper-in-visual-studio-15-preview/) blog gönderisi.

- Şimdi, **yürütmeyi buraya kadar Çalıştır** yeşil ok simgesine seçerek hata ayıklayıcıda duraklayana bir kod satırına çalıştırabilirsiniz (bir kod satırının üzerine gelindiğinde simgeyi görürsünüz). Bu, geçici kesme noktaları ayarlama gereksinimini ortadan kaldırır.

    ![Hata ayıklayıcının tıklama için Çalıştır](../debugger/media/dbg-run-to-click.png "DbgRunToClick")

- Özel durum **ayarları** iletişim kutusunda özel durumlar için koşullar ayarlayabilirsiniz (özel durum ayarları iletişim kutusundaki **koşulu Düzenle** simgesini veya özel durum üzerinde sağ tıklama menüsünü kullanarak bunu yapabilirsiniz.) Şu anda desteklenen koşullar, özel durum için dahil edilecek veya hariç tutulacak modül adlarını içerir.

    ![Özel durum koşulları](../debugger/media/dbg-conditional-exception.png "DbgConditionalException")

- Işleme İliştir iletişim kutusu, iliştirilebilmeniz gereken işlemi daha hızlı tanımanıza yardımcı olabilecek yeni bir arama özelliği içerir.

    ![Işleme Iliştir içinde ara](../debugger/media/dbg-attach-to-process-search.png "DbgAttachToProcessSearch")

Bu yeni özellikler hakkında daha fazla bilgi için, [[!include[vs_dev15](../misc/includes/vs_dev15_md.md)]Için sürüm notlarına ](/visualstudio/releasenotes/vs2017-relnotes)bakın.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio’da hata ayıklama](../debugger/index.yml)
- [Hata ayıklayıcıya ilk bakış](../debugger/debugger-feature-tour.md)