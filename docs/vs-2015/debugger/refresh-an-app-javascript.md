---
title: Uygulamayı yenileme (JavaScript) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- JavaScript debugging, refreshing pages [Windows Store apps]
- debugging, refreshing pages [Windows Store apps]
- DOM Explorer, Refresh [Windows Store apps]
- Refresh [Windows Store apps]
ms.assetid: fd99ee60-fa94-46df-8b17-369f60bfd908
caps.latest.revision: 23
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b5b8be97212f4510002a78e6565fc9884930db89
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63446094"
---
# <a name="refresh-an-app-javascript"></a>Uygulamayı yenileme (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Windows ve Windows Phone için geçerlidir] (.. /Image/windows_and_phone_content.png "windows_and_phone_content")  
  
 Hata ayıklama ve ardından seçerek JavaScript kullanarak bir Store uygulaması yenileme sırasında kodunuzda değişiklikler yapabilirsiniz **Yenile Windows uygulama** düğmesini **hata ayıklama** araç çubuğu. Bu düğmeyi seçerek uygulama hata ayıklayıcıyı durdurup yeniden olmadan yeniden yükler. Yenileme özelliği, HTML, CSS ve JavaScript kodu Değiştir ve hızlı bir şekilde sonuçları görmek sağlar. Bu özellik, Windows Store hem de Windows Phone Store uygulamaları için desteklenir.  
  
 Yenileme değil, uygulama durumunu korumak veya uygulamanız için aşağıdaki değişiklikleri yansıtacak:  
  
- Görüntü paketi bildiriminde belirtilen değişiklikler de dahil olmak üzere paket bildirim dosyası değişiklikler.  
  
- Başvuru ekleme veya bir SDK başvurusu kaldırma gibi değiştirir veya Windows çalışma zamanı bileşenleri (.winmd dosyaları) değiştirir.  
  
- Kaynak dizeleri .resjson dosyalardaki değişiklikler gibi değiştirir.  
  
- Proje dosyası yolu adı değişiklikleri, yeni proje dosyaları ya da silinen dosyaları ile sonuçlanan değiştirir.  
  
- Proje ve öğe özellik değişiklikleri seçili hata ayıklama cihazı değişiklikleri gibi veya paket eylemi (Özellikler penceresinde) bir dosya için değişiklikler.  
  
> [!IMPORTANT]
> Başvuruları değiştirme, paket bildirimini değiştirmek veya önceki listesinde belirtilen diğer değişiklikleri yapın, HTML, CSS ve JavaScript kaynak dosyalarını güncelleştirmek için hata ayıklayıcıyı yeniden başlatın ve durdurun gerekir.  
  
### <a name="to-refresh-an-app"></a>Bir uygulamayı yenilemek için  
  
1. Visual Studio'da gezinti uygulaması proje şablonunu kullanarak yeni bir proje oluşturun.  
  
     Bu, Windows Store uygulaması, Windows Phone Store uygulaması veya bir evrensel uygulama olabilir.  
  
2. Şablon ile Visual Studio'da açın, hata ayıklama hedefi seçin.  
  
     Bir Windows Phone projesi geçerli başlangıç projeniz varsa, hata ayıklama hedefi için bir Windows Phone öykünücüsü seçin. Aksi takdirde seçin **simülatör** veya **yerel makine**.  
  
     ![Select hata ayıklama hedef liste](../debugger/media/js-select-target.png "JS_Select_Target")  
  
3. Uygulamayı hata ayıklama modunda çalıştırmak için F5 tuşuna basın.  
  
4. Visual Studio'ya geçiş yapın. (F12 tuşuna basın.)  
  
5. İçinde **Çözüm Gezgini**, **sayfaları** > **giriş** klasör, açık home.html.  
  
6. Sayfa başlığı metni değiştirme  
  
    ```html  
    Welcome to yourAppName!  
    ```  
  
     başka bir şeye şöyle:  
  
    ```html  
    Hello!  
    ```  
  
7. Tıklayın **Yenile Windows uygulama** şuna benzeyen düğmesi: ![Windows uygulama düğmesine Yenile](../debugger/media/js-refresh.png "JS_Refresh"). (Veya F4 tuşuna basın.)  
  
8. Uygulamasına geçin. Uygulamayı yeniden başlatmayı hata ayıklayıcı olmadan yüklenir ve yeni sayfa başlığı görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlı Başlangıç: HTML ve CSS hatalarını ayıklama](../debugger/quickstart-debug-html-and-css.md)
