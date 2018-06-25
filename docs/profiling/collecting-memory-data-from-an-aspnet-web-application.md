---
title: Profil oluşturucu komut satırını kullanarak bir ASP.NET Web uygulamasından bellek verileri toplama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- .NET memory profiling method
- profiling tools,.NET memory method
ms.assetid: 57acf2b0-327a-4c0e-8078-ac2f6d99457d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 64dd2704891594b5d23eb4a536ee3ddf2ce9be98
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34262697"
---
# <a name="collect-memory-data-from-an-aspnet-web-application-by-using-the-profiler-command-line"></a>Profil oluşturucu komut satırını kullanarak bir ASP.NET web uygulamasından bellek verileri toplama
Bu bölümdeki yordamları ve kullanarak bir ASP.NET Web uygulaması için bellek ayırma ve nesne yaşam verisi toplama için seçenekleri açıklar **VSPerfCmd** komut satırı aracı.  
  
> [!NOTE]
>  **VSPerfCmd** aracı duraklatma ve sürdürme profil oluşturma ve ek veri işlemci ve Windows performans sayaçlarını toplama dahil olmak üzere profil oluşturma araçları işlevine tam erişimi olan, sağlar. Aynı zamanda **VSPerfASPNETCmd** bu işlevselliği gerekmediğinde komut satırı aracı. İle karşılaştırılan [VSPerfCmd](../profiling/vsperfcmd.md) komut satırı aracı, ortam değişkenleri ayarlanmış olması gerekir ve bilgisayar yeniden başlatıldığı gerekli değildir. Daha fazla bilgi için bkz: [VSPerfASPNETCmd ile hızlı web sitesi profili oluşturma](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md).  
  
## <a name="common-tasks"></a>Ortak görevler
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Çalışan bir ASP.NET uygulamasına profil oluşturucu ekleme**|-   [Nasıl yapılır: bellek verileri toplamak için bir ASP.NET web uygulamasına profil oluşturucu ekleme](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-memory-data-by-using-the-command-line.md)|  
|**Statik olarak derlenmiş gereç ikili dosyalar**|-   [Nasıl yapılır: statik olarak derlenmiş bir ASP.NET uygulamasını izleme ve bellek verileri toplama](../profiling/how-to-instrument-a-statically-compiled-aspnet-web-application-and-collect-memory-data-by-using-the-profiler-command-line.md)|  
|**Dinamik olarak derlenmiş gereç ikili dosyalar**|-   [Nasıl yapılır: dinamik olarak derlenmiş bir ASP.NET uygulamasını izleme ve bellek verileri toplama](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-memory-data.md)|  
  
## <a name="related-tasks"></a>İlişkili görevler
  
### <a name="profile-aspnet-web-applications"></a>Profil ASP.NET web uygulamaları  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Örnekleme yöntemini kullanarak profil**|-   [Örnekleme kullanarak uygulama istatistikleri toplama](../profiling/collecting-application-statistics-for-aspnet-using-the-profiler-sampling-method.md)|  
|**İzleme metodunu kullanarak profil**|-   [İzleme kullanarak ayrıntılı zamanlama verileri toplama](../profiling/collecting-detailed-timing-data-aspnet-profiler-instrumentation-method.md)|  
|**Kaynak çakışması ve iş parçacığı etkinliği profil**|-   [Eşzamanlılık verileri toplama](../profiling/collecting-concurrency-data-for-an-aspnet-web-application.md)|  
  
### <a name="profile-net-framework-memory-data"></a>.NET Framework bellek verileri profil  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Profil tek başına (istemci) uygulamaları**|-   [.NET Framework bellek verileri toplama](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications.md)|  
|**Profil Hizmetleri**|-   [.NET bellek verileri toplama](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
  
### <a name="analyze-net-memory-data-views-and-reports"></a>.NET bellek verisi görünümleri ve raporları analiz eder.  
 [.NET bellek verisi görünümleri](../profiling/dotnet-memory-data-views.md)  
  
## <a name="reference"></a>Başvuru  
 [Komut satırı profil oluşturma araçları başvurusu](../profiling/command-line-profiling-tools-reference.md)