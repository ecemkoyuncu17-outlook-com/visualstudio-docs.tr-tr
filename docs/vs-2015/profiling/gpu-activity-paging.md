---
title: GPU etkinliği (disk belleği) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.gpuactivity
- vs.cv.threads.timeline.gpupaging
ms.assetid: 95284ac5-3492-4f7b-a79f-7d2840a07679
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5979ccf8cafedb849b7ae9f7af6b0b35096e624f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62434169"
---
# <a name="gpu-activity-paging"></a>GPU Etkinliği (Disk Belleği)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**GPU etkinliği (disk belleği)** segmentleri iş parçacıkları sekmesinde zaman GPU işleme sayfalandırma istekleri bir kez temsil eder.  Bir segmenti uzunluğunu GPU doğrudan bellek erişimi (DMA) disk belleği paket işliyordu süreyi temsil eder. Genellikle, disk belleği paketleri bellek CPU ve GPU arasında aktarımı ile ilişkilidir.  
  
 Seçtiğinizde, bir GPU sayfalama segment, rapor üzerinde **geçerli** sekmesini işlenmiş DMA paket hakkında bilgileri görüntüler. Bu, DirectX altyapısı, DMA paket gönderilen işlem ve paket işlemek için gerekli olan zamanı ile ilişkili donanım kuyruğundaki, beklenen süre miktarını içerir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanım Görünümü](../profiling/utilization-view.md)
