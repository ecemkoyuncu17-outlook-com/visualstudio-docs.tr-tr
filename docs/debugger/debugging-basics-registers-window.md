---
title: Yazmaçları penceresi hakkında | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Registers window, about Registers window
- debugging [Visual Studio], Registers window
ms.assetid: ab354047-053e-4f94-8ac1-26e761442b6f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4deaf03013b6e28ea02e6ec7412bd23a05f1b87e
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72738258"
---
# <a name="about-the-registers-window-in-visual-studio-c-c-visual-basic-f"></a>Visual Studio 'daki Yazmaçları penceresi hakkında (C#, C++, Visual Basic,) F#

**Yazmaçları** penceresi yalnızca, **Seçenekler** Iletişim kutusunda, **hata ayıklama** düğümünde adres düzeyi hata ayıklama etkinse kullanılabilir.

 Yazmaçları, işlemcinin etkin bir şekilde çalıştığı küçük veri parçalarını depolamak için kullanılan bir işlemci (CPU) içindeki özel konumlardır. Kaynak kodu derlemek veya yorumlamak, verileri bellekten kayıtlara taşıdığınızda ve gerektiğinde yeniden geri alan yönergeler oluşturur. Kayıt içindeki verilere erişmek, bellekteki verilere erişirken çok hızlıdır. bu nedenle, işlemcinin verileri bir kasada bulundurmasına ve bu işlem, işlemcinin kayıtları sürekli olarak yüklemesini ve kaldırmayı gerektiren koddan daha hızlı bir şekilde çalışmasına olanak tanır. Derleyicinin verileri Yazmaçlarda tutmasını ve diğer iyileştirmeler gerçekleştirmesini kolaylaştırmak için, genel değişkenleri kullanmaktan kaçının ve yerel değişkenlere mümkün olduğunca güvenmelisiniz. Bu şekilde yazılan kod, başvurunun doğru yere sahip olduğu söylenir. C/C++gibi bazı dillerde, programcılar bir yazmaç değişkeni bildirebilir, bu da derleyiciye değişkeni her zaman bir kasada tutmaya en iyi şekilde denemesini söyler. Daha fazla bilgi için bkz. [register anahtar sözcüğü](https://msdn.microsoft.com/library/5b66905a-2f7f-4918-bb55-5e66d4bc50f9).

 Yazmaçları iki türe ayrılabilir: genel amaçlı ve özel amaç. Genel amaçlı kayıt kayıtları, iki sayı ekleme veya bir dizideki bir öğeye başvurma gibi genel işlemlere yönelik verileri tutar. Özel amaçlı kayıtların belirli amaçları ve özelleştirilmiş anlamları vardır. İyi bir örnek, işlemcinin programın çağrı yığınını izlemek için kullandığı yığın işaretçisi kayıt örneğidir. Bir programcı olarak, büyük olasılıkla yığın işaretçisini doğrudan işlemeyecektir. Ancak, yığın işaretçisi olmadığında, işlemcinin bir işlev çağrısının sonunda nereye dönebileceklerini bilmez hale getirmediği için, programınızın düzgün çalışması önemlidir.

 Çoğu genel amaçlı kayıt yalnızca tek bir veri öğesini tutar. Örneğin, tek bir tamsayı, kayan noktalı sayı veya bir dizinin öğesi. Daha yeni işlemcilerin, küçük bir veri dizisini tutabilecek vektör kayıtları olarak adlandırılan daha büyük Yazmaçları vardır. Çok fazla veri tutulduğundan, vektör kayıtları dizileri içeren işlemlere çok hızlı bir şekilde gerçekleştirilmesini sağlar. Vektör kayıtları öncelikle pahalı ve yüksek performanslı süper bilgisayarlarda kullanılmıştır, ancak artık yoğun grafik işlemlerinde çok daha fazla avantaj sağlamak için kullanıldıkları mikro işlemcilerde kullanılabilir hale geliyor.

 İşlemcinin genellikle, kayan nokta işlemleri için en iyi duruma getirilmiş ve tamsayı işlemleri için bir tane olmak üzere iki genel amaçlı kayıt kümesi vardır. Bunlara göre değil, bunlar kayan nokta ve tamsayı Yazmaçları olarak adlandırılır.

 Yönetilen kod, çalışma zamanında mikro işlemcinin fiziksel kayıtlarına erişen yerel koda derlenir. **Kayıt** penceresi, ortak dil çalışma zamanı veya yerel kod için bu fiziksel kayıtları görüntüler. Betik ve SQL, kayıt kavramını desteklemeyen diller olduğundan, **Yazmaçları** penceresi BETIK veya SQL uygulaması için kayıt bilgilerini görüntülemez.

 **Yazmaçları** penceresini görüntüleme hakkında daha fazla bilgi için, bkz. [Yazmaçları penceresini kullanma](../debugger/how-to-use-the-registers-window.md).

 **Kayıt** penceresine baktığınızda, `EAX = 003110D8` gibi girdileri görürsünüz.

 @No__t_0 işaretinin solundaki simge, kayıt adı, `EAX`, bu durumda. @No__t_0 işaretinin sağındaki sayı, kayıt içeriğini temsil eder.

 **Yazmaçları** penceresi yalnızca bir kaydın içeriğini görüntülemenizi sağlar. Yerel kodda kesme modundayken, bir kaydın içeriğine tıklayıp değeri düzenleyebilirsiniz. Bu, rastgele yapmanız gereken bir şey değildir. Düzenlemekte olduğunuz kaydı ve içerdiği verileri anlamadığınız takdirde, daha az düzenlemenin sonucu, bir program kilitlenmesi veya başka bir istenmeyen sonuç olabilir. Ne yazık ki, çeşitli Intel ve Intel uyumlu işlemcilerin kayıt kümelerinin ayrıntılı bir açıklaması, bu kısa giriş kapsamına çok daha fazla gidiyor.

## <a name="register-groups"></a>Grupları Kaydet

Dağınıklığı azaltmak için, **Yazmaçları** penceresi kayıtları gruplar halinde düzenler. **Yazmaçları** penceresine sağ tıkladığınızda, uygun gördüğünüz şekilde görüntüleyebilen veya gizleyebileceğiniz bir Grup listesi içeren bir kısayol menüsü görürsünüz.

## <a name="register-flags"></a>Kayıt bayrakları

Intel x86 işlemciler için, **Yazmaçları** penceresinde aşağıdaki bayrakları görebilirsiniz. Bir hata ayıklama oturumu sırasında bu bayrakları da düzenleyebilirsiniz.

|bayrağıyla|Değer ayarla|
|-|-|
|Taşma|OV = 1|
|Yön|YUKARı = 1|
|İsteği|EI = 1|
|İmzalayabilirsiniz|PL = 1|
|Sıfırlama|ZR = 1|
|Yardımcı taşıma|AC = 1|
|Eşlik|PE = 1|
|Sürdür|CY = 1|

## <a name="see-also"></a>Ayrıca bkz.
- [Nasıl Yapılır: Yazmaçlar Penceresini Kullanma](../debugger/how-to-use-the-registers-window.md)
- [Hata ayıklayıcıya ilk bakış](../debugger/debugger-feature-tour.md)