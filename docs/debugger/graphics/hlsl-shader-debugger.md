---
title: HLSL gölgelendirici hata ayıklayıcısı | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.graphics.shaderviewer
ms.assetid: 4ccec541-3c49-42bd-972a-686eb3a88fbc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 164c404f3bce6b8216092635e3489843039fb1eb
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72735296"
---
# <a name="hlsl-shader-debugger"></a>HLSL Gölgelendirici Hata Ayıklayıcısı
Visual Studio Grafik Çözümleyicisi içindeki HLSL hata ayıklayıcı, HLSL gölgelendirici kodunuzun uygulamanızın gerçek koşullarında nasıl çalıştığını anlamanıza yardımcı olur.

 HLSL hata ayıklayıcısı şudur:

 ![İzleme ve çağrı yığını pencerelerini kullanarak HLSL hatalarını ayıklama.](media/gfx_diag_demo_hlsl_debugger_orientation.png "gfx_diag_demo_hlsl_debugger_orientation")

## <a name="understanding-the-hlsl-debugger"></a>HLSL hata ayıklayıcısını anlama
 HLSL hata ayıklayıcısı, gölgelendirici kodunuzda ortaya çıkan sorunları anlamanıza yardımcı olur. @No__t_0 'de HLSL kodu hata ayıklaması diğer dillerde yazılmış hata ayıklama koduna benzer — örneğin C++ C#,, veya Visual Basic. Aynı diğer dillere hata ayıklaması yaparken olduğu gibi, değişkenlerin içeriğini inceleyebilir, kesim noktaları ayarlayabilir, kodda adım adım ilerleyebilir ve çağrı yığınına yaklaşabilirsiniz.

 Ancak, GPU 'Lar yüzlerce iş parçacığı üzerinde aynı anda gölgelendirici kodu çalıştırarak yüksek performans elde ettiğinden, HLSL hata ayıklayıcısı diğer grafik Çözümleyicisi araçlarıyla birlikte çalışarak bu bilgilerin tümünü anlamlı hale getirmenize yardımcı olacak şekilde sunar. içerdiği. Grafik Çözümleyicisi, yakalanan kareleri bir grafik günlüğüne kaydedilmiş bilgileri kullanarak yeniden oluşturur; HLSL hata ayıklayıcı, gölgelendirici kodu çalıştırdığı için GPU yürütmesini gerçek zamanlı olarak izlemez. Bir grafik günlüğü çıktının herhangi bir bölümünü yeniden oluşturmak için yeterli bilgi içerdiğinden ve grafik analizi bir hatanın gerçekleştiği tam pikseli ve olayı belirlemenize yardımcı olabilecek araçlar sağladığından, HLSL hata ayıklayıcısında yalnızca tam gölgelendiriciye benzeme yapmak gerekir İlgilendiğiniz iş parçacığı. Başka bir deyişle, gölgelendiricinin çalışması, iç çalışmalarının tam görünümde olduğu CPU üzerinde benzetilebilir. Bu da, HLSL hata ayıklayıcısına CPU benzeri bir hata ayıklama deneyimi kazandırır.

 Ancak, HLSL hata ayıklayıcısı şu an için aşağıdaki bakımlardan sınırlıdır:

- HLSL hata ayıklayıcısı düzenleme ve devam etmeyi desteklemez, ancak gölgelendiricilerde değişiklik yapıp sonuçları görmek için çerçeveyi yeniden oluşturabilirsiniz.

- Bir uygulamanın ve gölgelendirici kodunun hatalarını aynı anda ayıklamak mümkün değildir. Ancak, bunlar arasında geçiş yapabilirsiniz.

- İzle penceresine değişkenler ve kayıtlar ekleyebilirsiniz, ancak ifadeler desteklenmez.

  Yine de, HLSL hata ayıklayıcısı başka bir yöntemle sağlanabilecek olandan daha iyi ve daha CPU benzeri bir hata ayıklama deneyimi sağlar.

## <a name="hlsl-shader-edit--apply"></a>HLSL gölgelendirici düzenleme & Uygula
 HLSL gölgelendirici hata ayıklayıcısı, GPU yürütme modeli gölgelendirici durumunun geri alınamadığı için, CPU hata ayıklayıcısı tarafından aynı şekilde devam et & ' u desteklemiyor. Bunun yerine, HLSL hata & ayıklayıcısı, HLSL kaynak dosyalarını düzenlemenizi ve ardından **Uygula** ' yı seçerek değişikliklerinizin etkisini görmenizi sağlar. Değiştirdiğiniz Gölgelendirici kodunuz, projenizin orijinal HLSL kaynak dosyasının bütünlüğünü korumak için ayrı bir dosyada depolanır, ancak yaptığınız değişikliklerden memnun kaldığınızda, değişiklikleri projenize kopyalamak için **Kopyala..** . seçeneğini belirleyebilirsiniz. Bu özelliği kullanarak, hata içeren gölgelendirici kodunu hızla yineleyebilir ve HLSL hata ayıklama iş akışınızın maliyetli yeniden oluşturma ve yakalama adımlarını ortadan kaldırabilirsiniz.

## <a name="hlsl-disassembly"></a>HLSL ayrıştırılmış derleme
 HLSL gölgelendirici hata ayıklayıcısı, HLSL kaynak kodu listesinin sağında HLSL gölgelendirici derlemesinin bir listesini sağlar.

## <a name="debugging-hlsl-code"></a>HLSL kodunda hata ayıklama
 HLSL hata ayıklayıcısına işlem hattı aşamaları veya piksel geçmişi pencerelerini kullanabilirsiniz.

#### <a name="to-start-the-hlsl-debugger-from-the-graphics-pipeline-stages-window"></a>HLSL hata ayıklayıcısını Grafik Ardışık Düzen Aşamaları penceresinden başlatmak için

1. **Grafik ardışık düzen aşamaları** penceresinde, hata ayıklamak istediğiniz gölgelendirici ile ilişkili ardışık düzen aşamasını bulun.

2. Ardışık düzen aşamasının başlığının altında, küçük yeşil ok olarak görünen **hata ayıklamayı Başlat**' ı seçin.

    > [!NOTE]
    > HLSL hata ayıklayıcısına bu giriş noktası, karşılık gelen aşamanın yalnızca ilk gölgelendirici iş parçacığında (yani işlenen ilk köşe veya piksel) hata ayıklar. Bu gölgelendirici aşamalarının diğer iş parçacıklarına erişmek için piksel geçmişi kullanabilirsiniz.

#### <a name="to-start-the-hlsl-debugger-from-the-graphics-pixel-history"></a>HLSL hata ayıklayıcısını Grafik Piksel Geçmişi'nden başlatmak için

1. **Grafik piksel geçmişi** penceresinde, hata ayıklamak istediğiniz gölgelendirici ile ilişkili çizim çağrısını genişletin. Her bir çizim çağrısı birden fazla temel öğeye karşılık gelebilir.

2. Çizim çağrısı ayrıntılarında, elde edilen renk katkısı gölgelendirici kodunda bir hata olduğunu gösteren bir temel öğeyi genişletin. Hata olduğunu ortaya koyan birden fazla temel öğe varsa, soruna tanı koymayı zorlaştırabilecek hata birikiminden kaçınmak için bu duruma işaret eden ilk temel öğeyi seçin.

3. İlkel ayrıntılarda, **köşe gölgelendiricide** mi yoksa **piksel gölgelendiricide**mi hata ayıklama yapılıp yapılmayacağını seçin. Piksel gölgelendiricisinin doğru olduğu, ancak köşe gölgelendiricisinin kendisine yanlış sabitler aktarması nedeniyle yanlış renk katkısı ürettiğinden şüphelendiğiniz durumlarda, köşe gölgelendiricisi için hata ayıklama uygulayın. Aksi durumlarda piksel gölgelendiricisi için hata ayıklama uygulayın.

    Seçilen gölgelendiricinin sağında, küçük yeşil ok olarak görünen **hata ayıklamayı Başlat**' ı seçin.

   > [!NOTE]
   > HLSL hata ayıklayıcısına bu giriş noktası, ya seçilen çizim çağrısına, temel öğeye ve seçtiğiniz piksele karşılık gelen piksel gölgelendiricisi iş parçacığına ya da sonuçları çizim çağrısı, temel öğe ve seçmiş olduğunuz piksel tarafından ilişkilendirilen köşe gölgelendiricisi iş parçacıklarına hata ayıklama uygular. Köşe gölgelendiricileri durumunda, köşe gölgelendiricisi ayrıntılarını genişleterek giriş noktasını belirli bir köşeye kadar iyice daraltabilirsiniz.

   HLSL hata ayıklayıcının gölgelendirici hatalarını ayıklamak için nasıl kullanılacağına ilişkin örnekler için [, bkz.](graphics-diagnostics-examples.md) Ayrıca bkz. bölümünde bağlantılı izlenecek yollar

## <a name="see-also"></a>Ayrıca bkz.
- [İzlenecek Yol: Köşe Gölgeleme Nedeniyle Nesnelerin Eksikliği](walkthrough-missing-objects-due-to-vertex-shading.md)
- [İzlenecek Yol: Gölgeleme Nedeniyle Çıkan Oluşturma Hatalarını Ayıklama](walkthrough-debugging-rendering-errors-due-to-shading.md)
- [İzlenecek Yol: Hesaplayıcı Gölgelendiricisinde Hata Ayıklamak İçin Grafik Tanılamayı Kullanma](walkthrough-using-graphics-diagnostics-to-debug-a-compute-shader.md)