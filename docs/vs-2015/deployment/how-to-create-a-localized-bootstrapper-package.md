---
title: 'Nasıl yapılır: Yerelleştirilmiş önyükleyici paketi oluşturma | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
helpviewer_keywords:
- localized bootstrapper packages
- dependencies, creating localized bootstrapper packages
- prerequisites, creating localized bootstrapper packages
ms.assetid: 66a1bc7e-6540-4164-963d-557196a69d8a
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5ec3cd1365826c1a06b2d0f7bd6da377c8dc4d46
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63440664"
---
# <a name="how-to-create-a-localized-bootstrapper-package"></a>Nasıl yapılır: Yerelleştirilmiş önyükleyici paketi oluşturma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bir önyükleyici paketi oluşturduktan sonra her yerel ayar için iki daha fazla dosya oluşturarak yerelleştirilmiş önyükleyici paketi sürümlerini oluşturabilirsiniz: dosya (örneğin, bir eula.rtf) ve bir paket bildirimi (package.xml) bir yazılım lisans koşulları.  
  
 Varsayılan olarak, Visual Studio 2010 yalnızca .NET Framework 4 için .NET Framework 4 istemci profili, yerelleştirilmiş önyükleyici paketleri içerir F# çalışma zamanı 2.0 ve F# çalışma zamanı 4.0. Yerelleştirilmiş paketler, diğer önyükleyiciler için üç adımları izleyerek oluşturabilirsiniz.  
  
1. Yerel adı \Program SDKs\Windows\v7.0A\Bootstrapper\Packages sonra adlı bir klasör oluşturun\\*BootstrapperPackageName*.  
  
2. Önyükleyici paketini Yazılım Lisans Koşulları'nı içeren bir dosya oluşturun ve yeni klasöre yerleştirin.  
  
3. Package.xml adlı paket bildirimi oluşturma, güncelleştirme dizeleri ve kültür ve dosyanın yeni klasöre yerleştirin. Visual Studio'nun bir önyükleyici hedef dilde zaten oluşturduysanız, Visual Studio package.xml dosyasını kopyalayıp, bu adımda değiştirebilirsiniz.  
  
> [!NOTE]
> Uygulamaları dağıtmak için bir kurulum projesi kullanıyorsanız değiştirerek, uygulamanızın yerelleştirebilirsiniz **yerelleştirme** özelliği.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-localized-bootstrapper-package"></a>Yerelleştirilmiş önyükleyici paketi oluşturmak için  
  
1. Yerel ayar adından sonra adlı bir klasör oluşturun.  
  
     32-bit bilgisayarlarda, klasör \Program Files\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages oluşturun\\*BootstrapperPackageName*\ klasör.  
  
     64-bit bilgisayarlarda, klasör \Program dosyaları (86) \Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages oluşturun.\\*BootstrapperPackageName*\ klasör.  
  
     Aşağıdaki tabloda, bir yerel ayar eşleştirmek için kullanabileceğiniz klasör adlarını gösterir.  
  
    |Yerel Ayar|Klasör adı|  
    |------------|-----------------|  
    |ve|zh-Hans|  
    |seçenekleri yerine|zh-Hant|  
    |Çekçe|cs|  
    |Almanca|de|  
    |İngilizce|tr|  
    |İspanyolca|ES|  
    |Fransızca|FR|  
    |İtalyanca|Bunu|  
    |Korece|Ko|  
    |Japonca|ja|  
    |Lehçe|PL|  
    |Portekizce (Brezilya)|pt-BR|  
    |Rusça|RU|  
    |Türkçe|tr|  
  
2. Önyükleyici paketini Yazılım Lisans Koşulları'nı içeren bir dosya oluşturun ve yeni klasöre yerleştirin.  
  
3. Package.xml adlı paket bildirimi oluşturma ve yeni klasöre yerleştirin. Daha fazla bilgi için [nasıl yapılır: Paket bildirimi oluşturma](../deployment/how-to-create-a-package-manifest.md).  
  
4. Güncelleştirme `<Strings>` paketin bölümünü bildirim yerel ayarı için doğru dilde dizelerdir.  
  
5. Değişiklik `<String Name="Culture">` klasör adı eşleşecek değer.  
  
6. Package.xml dosyayı kaydedin.  
  
### <a name="to-create-a-bootstrapper-package-for-net-framework-35-service-pack-1-localized-in-french"></a>.NET Framework 3.5 Service Pack 1'de Fransızca yerelleştirilmiş önyükleyici paketi oluşturmak için  
  
1. Fr adlı bir klasör oluşturun. Klasör adı, yerel ayar adı eşleşmelidir.  
  
     32-bit bilgisayarlarda, klasör \Program SDKs\Windows\v7.0A\Bootstrapper\Packages\DotNetFX35SP1\ klasöründe oluşturun.  
  
     64-bit bilgisayarlarda, klasör \Program Files (86) \Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\DotNetFX35SP1\ klasöründe oluşturun.  
  
2. Yazılım Lisans Koşulları'nı yerelleştirilmiş bir sürümünü, fr klasöre koyun.  
  
3. Fr klasörü \Program dosyaları (x86) \Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\DotNetFX35SP1\en\package.xml dosya kopyalayın ve dosyayı XML Tasarımcısı'nda açın.  
  
4. Güncelleştirme `<Strings>` paketin bölümünü bildiriminin Fransızca hata dizelerdir.  
  
5. Değişiklik `<String Name="Culture">` fr değeri.  
  
6. Package.xml dosyayı kaydedin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Önyükleyici paketleri oluşturma](../deployment/creating-bootstrapper-packages.md)   
 [Uygulama dağıtımının önkoşulları](../deployment/application-deployment-prerequisites.md)   
 [Nasıl yapılır: Paket Bildirimi Oluşturma](../deployment/how-to-create-a-package-manifest.md)
