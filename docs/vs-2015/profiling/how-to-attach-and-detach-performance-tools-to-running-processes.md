---
title: 'Nasıl yapılır: Ekleme ve ayırma performans araçlarını çalışan işlemlere | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.attach
helpviewer_keywords:
- performance tools, attach process
- profiling tools, detach process
- profiling tools, attach process
- performance tools, detach process
- profiler
ms.assetid: 56a99c39-e7f6-4f48-ae56-04ab8e022bf7
caps.latest.revision: 35
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 0b8fc664ee47cd34ab984d1ac448b45c2f17c5b0
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63443714"
---
# <a name="how-to-attach-and-detach-performance-tools-to-running-processes"></a>Nasıl yapılır: Ekleme ve ayırma işlemleri çalıştırmak için performans araçları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Profil Oluşturucu ekleme veya örnekleme ve toplar performans verilerini daha kolay hale getirmek için çalışan bir işlemden ayırmak için kullanılabilir. Uygulama yükleme süresi hakkında veri toplama kaçınmak istiyorsanız ya da sonraki bir işlemin performansını izlemek için belirli bir duruma ulaştığında bir işlem profili için bu yöntemi kullanabilirsiniz.  
  
> [!NOTE]
> Ekleme ve ayırma işlemleri içinden aşağıdaki adımları uygulamak [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] tümleşik geliştirme environmnent (IDE). Komut satırı araçlarının nasıl kullanılacağı hakkında daha fazla bilgi için bkz. [komut satırından profil oluşturma](../profiling/using-the-profiling-tools-from-the-command-line.md). Profil hizmetler hakkında daha fazla bilgi için bkz. [profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md).  
  
 Profili için kullanılabilir olan işlemleri, bilgisayarın yönetici tarafından ayarlanan kullanıcı erişimi izinleri bağlıdır. Örneğin, bir kullanıcı hesabı izni aşağıdakilerden herhangi biri olabilir:  
  
- Gelişmiş Özellikler, sürücü ve hizmeti başlatmak için yöneticiniz tarafından belirlenen zaman profil oluşturma.  
  
- Yalnızca (etki alanı kullanıcı) profil oluşturma örneği.  
  
- Herkes için profil oluşturma için erişimi engeller.  
  
  Daha fazla bilgi için [profil oluşturma ve Windows Vista Güvenliği](../profiling/profiling-and-windows-vista-security.md) ve yönetim seçeneklerini [VSPerfCmd](../profiling/vsperfcmd.md).  
  
### <a name="to-attach-to-a-running-process"></a>Çalışan bir işleme iliştirmek için  
  
1. Üzerinde **Çözümle** menüsünde **Profiler** ve ardından **Attach/Detach**.  
  
     \- veya -  
  
     İçinde **performans Gezgini**performans oturumu sağ tıklayın ve ardından **Attach/Detach**.  
  
     **İşleme iliştirmek Profiler** iletişim kutusu görüntülenir.  
  
2. Eklemek istediğiniz işlemin adını tıklayın.  
  
3. Tıklayın **ekleme**.  
  
### <a name="to-detach-from-a-running-process"></a>Çalışan bir işlemden ayırmak için  
  
1. Üzerinde **Çözümle** menüsünde **Profiler** ve ardından **Attach/Detach**.  
  
     \- veya -  
  
     İçinde **performans Gezgini**performans oturumu sağ tıklayın ve ardından **Attach/Detach**.  
  
     **İşleme iliştirmek Profiler** iletişim kutusu görüntülenir.  
  
2. Ayırmak istediğiniz görüntü adına tıklayın.  
  
3. Tıklayın **ayırma**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri toplama denetimi](../profiling/controlling-data-collection.md)   
 [Performans oturumuna genel bakış](../profiling/performance-session-overview.md)   
 [Nasıl yapılır: Başlangıç ve bitiş performans verilerini toplama](../profiling/how-to-start-and-end-performance-data-collection.md)   
 [Profil oluşturma ve Windows Vista güvenliği](../profiling/profiling-and-windows-vista-security.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)
