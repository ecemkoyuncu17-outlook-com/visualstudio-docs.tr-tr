---
title: Modüller görünümü - izleme verileri | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Modules view
ms.assetid: 895b9589-1987-4160-916f-53b898a69cf0
caps.latest.revision: 15
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 4455f850ad533f17cd9f6cb33e7e874621d0bb2c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68205898"
---
# <a name="modules-view---instrumentation-data"></a>Modüller Görünümü - İzleme Verileri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Modüller görünümü, profil oluşturma verileri olan modüller tarafından gruplandırılmış performans verilerini görüntüler. Modülündeki işlevlerin modülü düğümün altında listelenir.  
  
## <a name="general"></a>Genel  
 Genel sütunları bir görünüm satır işlevi tanımlar.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Ad**|İşlev veya modül adı.|  
|**İşlevin satır numarası**|Satır numarası kaynak dosyada bu işlevin başlangıcı.|  
|**Çağrı sayısı**|Bu işlev veya modül yapılan çağrıları toplam sayısı.|  
|**Kaynak dosyası**|Bu işlevin tanımını içeren kaynak dosya.|  
|**Modül adı**|İşlevi içeren modül adı.|  
|**Modül yolu**|İşlevi içeren modül yolu.|  
|**İşlem kimliği**|İşlem, profil oluşturma çalışması Kimliğine (PID).|  
|**İşlem adı**|Hangi modülün veya işlevin yürütülmekte olan işlemin adı.|  
|**Zaman dışlamalı araştırma ek yükü**|Bu işlev veya modül nedeniyle izleme için ek yükü süre.|  
|**Zaman kapsamlı araştırma ek yükü**|Zaman ek yükü bu işlev veya modül ve izleme nedeniyle alt işlevleri.|  
  
## <a name="elapsed-inclusive-values"></a>Geçen kapsamlı değerleri  
 Geçen kapsamlı değerleri, çağrı yığınındaki bir işlevi olduğu zamanı gösterir. Saati, harcanan süre alt işlevleri ve bağlam anahtarları ve giriş/çıkış işlemleri gibi işletim sistemi çağrıları içerir.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Geçen kapsamlı süre**|-Bir işlev için işlevde harcanan süre. Alt işlevleri ve işletim sistemi, bağlam anahtarları ve giriş/çıkış işlemleri gibi çağrılarında harcanan süreyi içerir.<br />-Bir modül için modülünde en az bir işlev çağrı yığını üzerinde olduğu zaman.|  
|**Geçen kapsamlı süre yüzdesi**|Toplam geçen kapsamlı süre Bu modülün veya işlevin içinde profil oluşturma, toplam geçen kapsamlı süre yüzdesi harcandığını.|  
|**Geçen ortalama kapsamlı süre**|-Bir işlev için ortalama kapsamlı süre bu işlev çağrısına geçti.<br />-Bir modül için ortalama kapsamlı süre modülündeki işlevleri yapılan tüm çağrıların geçti.|  
|**Geçen maksimum kapsamlı süre**|-Bir işlev için maksimum kapsamlı süre bu işlev çağrısına geçti.<br />-Bir modül için en fazla modülündeki işlevleri yapılan tüm çağrıların kapsamlı süre geçti.|  
|**Geçen minimum kapsamlı süre**|-Bir işlev için en az Bu modülün veya işlevin çağrısına kapsamlı süre geçti.<br />-Bir modül için minimum kapsamlı süre modülündeki işlevleri yapılan tüm çağrıların geçti.|  
  
## <a name="elapsed-exclusive-values"></a>Geçen dışlamalı değerleri  
 Geçen dışlamalı değerleri bir işlev doğrudan çağrı yığınının en üstünde çağırılma yürütüldüğü zaman gösterir. Bağlam geçişleri ve giriş/çıkış işlemleri gibi işletim sistemi çağrılarında harcanan zaman zaman içerir, ancak alt işlevlerde harcanan süreyi içermez.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Geçen dışlamalı süre**|-Bir işlev için modülün veya işlevin harcanan süre. Bu bağlam anahtarları ve giriş/çıkış işlemleri gibi işletim sistemi çağrıları içerir, ancak alt işlevlerde harcanan zamanı dışlar.<br />-Bir modül için modülündeki işlevlerin özel süreleri toplamı geçti.|  
|**Geçen dışlamalı süre yüzdesi**|Toplam geçen dışlamalı süre Bu modülün veya işlevin içinde profil oluşturma, toplam geçen dışlamalı süre yüzdesi harcandığını.|  
|**Geçen ortalama dışlamalı süre**|-Bir işlev için ortalama dışlamalı süre bu işlev çağrısına geçti.<br />-Bir modül için ortalama dışlamalı süre modülündeki işlevleri yapılan tüm çağrıların geçti.|  
|**Geçen maksimum dışlamalı süre**|-Bir işlev için maksimum dışlamalı süre bu işlev çağrısına geçti.<br />-Bir modül için maksimum dışlamalı süre modülündeki işlevleri yapılan tüm çağrıların geçti.|  
|**Geçen minimum dışlamalı süre**|-Bir işlev için minimum dışlamalı süre Bu modülün veya işlevin çağrısına geçti.<br />-Bir modül için minimum dışlamalı süre modülündeki işlevleri yapılan tüm çağrıların geçti.|  
  
## <a name="application-inclusive-values"></a>Uygulama kapsamlı değerlerini  
 Uygulama kapsamlı değerleri, çağrı yığınındaki bir işlevi olduğu zamanı gösterir. Zaman bağlam anahtarları ve giriş/çıkış işlemleri gibi işletim sistemi çağrılarında harcanan süreyi içermez. Ancak, zaman alt işlevlerde harcanan süreyi içermez.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Kapsamlı uygulama süresi**|-Bir işlev için işlev çağrılarında harcanan süre. Bu alt işlevlerde geçen ancak bağlam anahtarları ve giriş/çıkış işlemleri gibi işletim sistemi çağrıları dışlar süreyi içerir.<br />-Bir modül için modülünde en az bir işlev çağrı yığını üzerinde olduğu zaman. Bu, işletim sistemi çağrılarında harcanan süre dahil değildir.|  
|**Kapsamlı uygulama süresi yüzdesi**|Kapsamlı uygulama süresi Bu modülün veya işlevin içinde harcandığını profil oluşturma çalışması toplam geçen kapsamlı süre yüzdesi.|  
|**Ortalama kapsamlı uygulama süresi**|-Bir işlev için bu işlev için bir çağrı, ortalama uygulama kapsamlı süre.<br />-Bir modül için modülündeki işlevleri yapılan tüm çağrıların ortalama uygulama kapsamlı süre.|  
|**Maksimum kapsamlı uygulama süresi**|-Bir işlev için bu işlevi çağrısı, en fazla uygulama kapsamlı süre.<br />-Bir modül için modülündeki işlevleri yapılan tüm çağrıların en fazla uygulama kapsamlı süre.|  
|**Minimum kapsamlı uygulama süresi**|-Bir işlev için yapılan çağrının Bu modülün veya işlevin en düşük uygulama kapsamlı süre.<br />-Bir modül için modülündeki işlevleri yapılan tüm çağrıların en düşük uygulama kapsamlı süre.|  
  
## <a name="application-exclusive-values"></a>Uygulama özel değerler  
 Uygulama özel değerlerini modülün veya işlevin harcanan zamanı gösterir. Bu alt işlevlerde geçen süre ve aynı zamanda bağlam anahtarları ve giriş/çıkış işlemleri gibi işletim sistemi çağrıları hariç süre dahil değildir.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Dışlamalı uygulama süresi**|Bu modülün veya işlevin yapılan tüm çağrıların toplam uygulama dışlamalı süre.|  
|**Dışlamalı uygulama süresi yüzdesi**|Dışlamalı uygulama süresi Bu modülün veya işlevin içinde harcandığını profil oluşturma çalışması toplam geçen dışlamalı süre yüzdesi.|  
|**Ortalama dışlamalı uygulama süresi**|-Bir işlev için bu işlev için bir çağrı, ortalama uygulama dışlamalı süre.<br />-Bir modül için modülündeki işlevleri yapılan tüm çağrıların ortalama uygulama dışlamalı süre.|  
|**Maksimum dışlamalı uygulama süresi**|-Bir işlev için bu işlevi çağrısı, en fazla uygulama dışlamalı süre.<br />-Bir modül için modülündeki işlevleri yapılan tüm çağrıların en fazla uygulama dışlamalı süre.|  
|**Minimum dışlamalı uygulama süresi**|-Bir işlev için yapılan çağrının Bu modülün veya işlevin en düşük uygulama dışlamalı süre.<br />-Bir modül için modülündeki işlevleri yapılan tüm çağrıların en düşük uygulama dışlamalı süre.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Modüller görünümü](../profiling/modules-view-sampling-data.md)   
 [Modüller görünümü - izleme](../profiling/modules-view-dotnet-memory-instrumentation-data.md)   
 [Modüller Görünümü- Örnekleme](../profiling/modules-view-dotnet-memory-sampling-data.md)
