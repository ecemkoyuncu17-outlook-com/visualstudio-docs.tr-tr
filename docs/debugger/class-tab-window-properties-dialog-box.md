---
title: Sınıf sekmesi, pencere Özellikleri iletişim kutusu | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Window Properties dialog box, Class Tab
ms.assetid: eaec9f07-d580-436d-934d-76c4e59439aa
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0917c9a038b42e6302ec1f1782f095ca397a92ef
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62565019"
---
# <a name="class-tab-window-properties-dialog-box"></a>Sınıf Sekmesi, Pencere Özellikleri İletişim Kutusu
Kullanım **sınıfı** seçilen pencere sınıf üzerinde bilgi göstermek için sekmesinde. Görüntülenecek [pencere Özellikleri iletişim kutusu](../debugger/window-properties-dialog-box.md), odağı Taşı [Windows görünümü](../debugger/windows-view.md) penceresi. Herhangi bir pencere düğüm ağaçta seçin ve ardından **özellikleri** gelen **görünümü** menüsü.

 Aşağıdaki ayarlar kullanılabilir **sınıfı** sekmesinde:

|Giriş|Açıklama|
|-----------|-----------------|
|**Sınıf adı**|Bu pencere sınıfı adı (veya sıra numarası).|
|**Sınıf stilleri**|Sınıf stili kodlarını birleşimi.|
|**Sınıf baytları**|Bu pencere sınıfı ile ilgili uygulamaya özgü veriler.|
|**Sınıf atomu**|Tarafından döndürülen sınıf için atom **RegisterClass** çağırın.|
|**Örnek tanıtıcısını**|Sınıf kayıtlı modül örnek tanıtıcısını. Örnek işler özgü değildir.|
|**Pencere baytları**|Bu sınıfın her bir pencere ile ilgili ek bayt sayısı. Bu bayt anlamını uygulama tarafından belirlenir. Liste kutusu DWORD biçimde bayt değerleri görmek için genişletin.|
|**Pencere işleme**|Geçerli adresi **WndProc** bu sınıfın windows için işlevi. Bu farklıdır **pencere işleme** üzerinde **genel** pencerenin alt sınıflanan, sekme.|
|**Menü adı**|Bu sınıf ("none" menü yok ise), windows ile ilişkili ana menü adı.|
|**Simge tanıtıcı**|Windows, bu sınıfın ("none" herhangi bir simge varsa) ile ilişkili simge tanıtıcı.|
|**İmleç tanıtıcı**|Windows, bu sınıfın ("none" Hiçbir imleç varsa) ile ilişkili imleci için tanıtıcı.|
|**Arka plan Fırçası**|Windows Bu sınıf ya da bir pencere arkaplanı ("none" fırça yok ise) boyama için önceden tanımlanmış COLOR_ * renge ilişkilendirildiği arkaplan Fırçası için tanıtıcı.|