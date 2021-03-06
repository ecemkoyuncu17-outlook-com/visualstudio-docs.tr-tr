---
title: 'Nasıl yapılır: özel başlangıç sayfası yükseltme | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
ms.assetid: 78342ce6-36c8-485b-a5f6-760e7a420a26
caps.latest.revision: 8
manager: jillfra
ms.openlocfilehash: a7854de705a961463b1e8435e7340548cfc23bf3
ms.sourcegitcommit: bad28e99214cf62cfbd1222e8cb5ded1997d7ff0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74293370"
---
# <a name="how-to-upgrade-a-visual-studio-custom-start-page"></a>Nasıl yapılır: Visual Studio özel başlangıç sayfası yükseltme
Visual Studio 2010 yükseltebilir veya Visual Studio 2012 özel başlangıç sayfasına Visual Studio 2015 için aşağıda listelenen adımları izleyin.

> [!WARNING]
> Bu yordamda yükseltilen özel başlangıç sayfası, Visual Studio galerisindeki [özel başlangıç sayfası](https://marketplace.visualstudio.com/items?itemName=VisualStudioProductTeam.CustomStartPageProjectTemplate) şablonuyla oluşturulmuş olan bir şablondur. Başlangıç sayfanızı yükseltilmesi gereken diğer özelliklerini olabilir.

### <a name="to-upgrade-a-custom-start-page-to-visual-studio-2015"></a>Özel başlangıç sayfası, Visual Studio 2015'e yükseltmek için

1. Visual Studio 2015 ve Visual Studio 2015 SDK yüklü olduğundan emin olun. VSSDK 'yi [Microsoft Visual Studio 2013 SDK](https://my.visualstudio.com/Downloads?pid=1436)'dan indirebilirsiniz.

2. Özel şablon projenizi açın. Yükseltilecek projedir bildiren bir ileti görürsünüz. **Tamam** ' a tıklayın ve yükseltmenin tamamlanmasını bekleyin.

3. Başlangıç sayfası proje hem denetimi projesi için proje özelliklerinde, hedef Framework'ü en az olduğundan emin olun. .NET Framework 4.5.

4. Başlangıç sayfası proje için proje özellikleri hata ayıklama kategorisinde devenv.exe Visual Studio 2015 sürümüne yolunu ayarlayın.

5. Her iki proje için proje başvuruları, Microsoft.VisualStudio.Shell.11.0 yönelik başvuruları kaldırmanız ve Microsoft.VisualStudio.Shell.14.0 başvurular ekleyin.

6. StartPage.xaml ile XML Düzenleyicisi'ni açın ve aşağıdaki değişiklikleri yapın:

    1. Ad alanlarını güncelleştirin. Aşağıdaki satırları değiştirin:

        ```

        xmlns:vs="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.11.0"
         xmlns:vsfxim="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.Immutable.11.0"
        xmlns:vsfx="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.11.0"
        ```

         şu şekilde:

        ```

        xmlns:vs="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.142.0"
         xmlns:vsfxim="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.Immutable.14.0"
        xmlns:vsfx="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0"
        ```

7. MyControl. xaml ' yi açın ve ad alanı başvurusunu `xmlns:vs="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0"` `xmlns:vs="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.11.0"` değiştirin.