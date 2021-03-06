---
title: 'Öğretici: Hata Ayıklama Visual Basic kodu'
description: Visual Studio hata ayıklayıcısını nasıl başlatacaknızı, koda nasıl basıp verileri inceleyiniz öğrenin.
ms.custom: debug-experiment, seodec18, get-started
ms.date: 02/03/2020
ms.technology: vs-ide-debug
ms.topic: tutorial
dev_langs:
- VB
helpviewer_keywords:
- debugger
ms.assetid: 62734c0d-a75a-4576-8f73-0e97c19280e1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 84ed0de3542822597c64e0866c04f719ed6c2ab7
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/20/2020
ms.locfileid: "77027244"
---
# <a name="tutorial-learn-to-debug-visual-basic-code-using-visual-studio"></a>Öğretici: Visual Studio kullanarak Visual Basic kodunu hata ayıklamayı öğrenin

Bu makalede, Visual Studio hata ayıklama nın özellikleri adım adım gözden geçirilerek tanıtılır. Hata ayıklama özelliklerinin daha üst düzey bir görünümünü istiyorsanız, [hata ayıklama özelliğine ilk bakışta](../../debugger/debugger-feature-tour.md)bakın. *Uygulamanızı hata ayıklama*yaptığınızda, bu genellikle uygulamanızı bağlı hata ayıklama yla çalıştırdığınız anlamına gelir. Bunu yaptığınızda, hata ayıklayıcı, kodunuzu çalışırken ne yaptığını görmek için birçok yol sağlar. Kodunuzu gözden geçirebilir ve değişkenlerde depolanan değerlere bakabilirsiniz, değerler ne zaman değiştiğini görmek için değişkenler üzerinde saatler ayarlayabilir, kodunuzun yürütme yolunu inceleyebilir, kod dalının çalışıp çalışmadığını görebilirsiniz, vesaire. Bu kod hata ayıklama denedim ilk kez ise, bu makalede geçmeden önce [mutlak yeni başlayanlar için Hata Ayıklama](../../debugger/debugging-absolute-beginners.md) okumak isteyebilirsiniz.

Demo uygulaması Visual Basic olmasına rağmen, özelliklerin çoğu C#, C++, F#, Python, JavaScript ve Visual Studio tarafından desteklenen diğer diller için geçerlidir (F# Düzenleme ve devam ı desteklemez. F# ve JavaScript **Autos** penceresini desteklemez). Ekran görüntüleri Visual Basic'te.

Bu öğreticide şunları yapacaksınız:

> [!div class="checklist"]
> * Hata ayıklama başlatın ve kesme noktalarına çarptı.
> * Hata ayıklayıcıda koda basmak için komutları öğrenin
> * Veri ipuçlarındaki ve hata ayıklama pencerelerinde değişkenleri inceleyin
> * Arama yığınını inceleme

## <a name="prerequisites"></a>Önkoşullar

::: moniker range=">=vs-2019"

Visual Studio 2019 yüklü ve **.NET Core çapraz platform geliştirme** iş yükünü yüklemeniz gerekir.

::: moniker-end
::: moniker range="vs-2017"

Visual Studio 2017 yüklü ve **.NET Core çapraz platform geliştirme** iş yükünü yüklemeniz gerekir.

::: moniker-end

::: moniker range="vs-2017"

Visual Studio'yu henüz yüklemediyseniz, visual [studio indirme sayfasına](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) gidin ve ücretsiz olarak yükleyin.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio'yu henüz yüklemediyseniz, visual [studio indirme sayfasına](https://visualstudio.microsoft.com/downloads) gidin ve ücretsiz olarak yükleyin.

::: moniker-end

İş yükünü yüklemeniz gerekiyorsa ancak visual studio'ya zaten sahipseniz, **Visual** > Studio Installer'ı açan**Araçlar Ve Özellikler...'** a gidin. Visual Studio Installer başlattı. **.NET Core çapraz platform geliştirme** iş yükünü seçin ve ardından **Değiştir'i**seçin.

## <a name="create-a-project"></a>Proje oluşturma

İlk olarak, bir .NET Core konsol uygulama projesi oluşturursunuz. Proje türü, daha bir şey eklemeden önce ihtiyacınız olan tüm şablon dosyalarıyla birlikte gelir!

::: moniker range="vs-2017"

1. Visual Studio 2017'yi açın.

2. Üst menü çubuğundan **Yeni** > **New** > **Dosya Yı**seçin.

3. Sol bölmedeki **Yeni Proje** iletişim kutusunda **Visual Basic'i**genişletin ve **ardından .NET Core'u**seçin. Orta bölmede Konsol **Uygulaması'nı (.NET Core)** seçin. Sonra proje *get-started-hata ayıklama*adını.

     **Konsol Uygulaması (.NET Core)** proje şablonunu görmüyorsanız, **Yeni Proje** iletişim kutusunun sol bölmesinde Bulunan Görsel **Stüdyo Yükleyicisi** Açık bağlantısını seçin.

     Visual Studio Installer başlattı. **.NET Core çapraz platform geliştirme** iş yükünü seçin ve sonra **Değiştir'i**seçin.

::: moniker-end

::: moniker range="vs-2019"

1. Görsel Stüdyo 2019'u açın.

   Başlangıç penceresi açık değilse, **Dosya** > **Başlangıç Penceresi'ni**seçin.

1. Başlangıç penceresinde yeni **bir proje oluştur'u**seçin.

1. Yeni **proje oluştur** penceresinde, arama kutusuna *konsol* girin veya yazın. Ardından, Dil listesinden **Visual Basic'i** seçin ve ardından Platform listesinden **Windows'u** seçin. 

   Dil ve platform filtrelerini uyguladıktan sonra **Konsol Uygulaması (.NET Core)** şablonunu seçin ve **sonra İleri'yi**seçin.

   ![Konsol Uygulaması (.NET Core) için Visual Basic şablonunu seçin](../visual-basic/media/vs-2019/get-started-create-console-project.png)

   > [!NOTE]
   > **Konsol Uygulaması (.NET Core)** şablonunu görmüyorsanız, yeni **bir proje oluştur** penceresinden yükleyebilirsiniz. **Aradığınızı bulamıyor musunuz?** iletisinde, daha **fazla araç ve özellik yükle** bağlantısını seçin. Ardından, Visual Studio Installer'da **.NET Core çapraz platform geliştirme** iş yükünü seçin.

1. Yeni **proje pencerenizi Yapılandır'da** **Proje adı** kutusuna başlangıç *hata ayıklama* yazın veya girin. Ardından **Oluştur'u**seçin.

   Visual Studio yeni projenizi açıyor.
   
::: moniker-end

## <a name="create-the-application"></a>Uygulama oluşturma

1. *Program.vb'de,* varsayılan kodun tümünün yerine aşağıdaki kodu değiştirin:

    ```vb
    Imports System

    Class ArrayExample
        Public Shared Sub Main()
            Dim letters As Char() = {"f"c, "r"c, "e"c, "d"c, " "c, "s"c, "m"c, "i"c, "t"c, "h"c}
            Dim name As String = ""
            Dim a As Integer() = New Integer(9) {}

            For i As Integer = 0 To letters.Length - 1
                name += letters(i)
                a(i) = i + 1
                SendMessage(name, a(i))
            Next

            Console.ReadKey()
        End Sub

        Private Shared Sub SendMessage(ByVal name As String, ByVal msg As Integer)
            Console.WriteLine("Hello, " & name & "! Count to " & msg)
        End Sub
    End Class
    ```

## <a name="start-the-debugger"></a>Hata ayıklamayı başlatın!

1. **Hata** Ayıklama > Hata**Ayıklama'ya**veya Hata **Ayıklama** Başlatma düğmesine basın Hata Ayıklama Araç Çubuğu'nda Hata ![Ayıklama](../../debugger/media/dbg-tour-start-debugging.png "Hata Ayıklama'yı Başlatma") başlat.

     **F5,** uygulamayı uygulama sürecine bağlı hata ayıklayıcıyla başlatır, ancak şu anda kodu incelemek için özel bir şey yapmadık. Yani uygulama sadece yükler ve konsol çıkışı bakın.

    ```cmd
    Hello, f! Count to 1
    Hello, fr! Count to 2
    Hello, fre! Count to 3
    Hello, fred! Count to 4
    Hello, fred ! Count to 5
    Hello, fred s! Count to 6
    Hello, fred sm! Count to 7
    Hello, fred smi! Count to 8
    Hello, fred smit! Count to 9
    Hello, fred smith! Count to 10
    ```

     Bu öğreticide, hata ayıklama yı kullanarak bu uygulamaya daha yakından bakacağız ve hata ayıklama özelliklerine bir göz atacağız.

2. Kırmızı stop Hata Ayıklama yı durdur düğmesine **(Shift** + **F5)** basarak hata ![ayıklamayı](../../debugger/media/dbg-tour-stop-debugging.png "Hata Ayıklamayı Durdur") durdurun.

3. Konsol penceresinde, konsol penceresini kapatmak için bir tuşa basın.

## <a name="set-a-breakpoint-and-start-the-debugger"></a>Bir kesme noktası ayarlayın ve hata ayıklamayı başlatın

1. `Main` İşlevin `For` döngüsünde, aşağıdaki kod satırının sol kenar boşluğuna tıklayarak bir kesme noktası ayarlayın:

    `name += letters(i)`

    Kesme noktasını ayarladığın yerde kırmızı bir daire ![Breakpoint](../../debugger/media/dbg-breakpoint.png "Kesme noktası") görünür.

    Kesme noktaları, güvenilir hata ayıklamanın en temel ve temel özelliklerinden biridir. Kesme noktası, Visual Studio'nun çalışan kodunuzu nerede askıya alması gerektiğini gösterir, böylece değişkenlerin değerlerine veya belleğin davranışına veya bir kod dalının çalıştırılıp çalıştırılmayacağına göz atabilirsiniz.

2. **F5** veya **Başlangıç Hata Ayıklama** düğmesine basın Hata ![Ayıklama başlat,](../../debugger/media/dbg-tour-start-debugging.png "Hata Ayıklama'yı Başlatma")uygulama başlar ve hata ayıklayıcı kesme noktasını ayarladığınız kod satırına çalışır.

    ![Bir kesme noktası ayarlayın ve çarptı](../visual-basic/media/get-started-hit-breakpoint-vb.png)

    Sarı ok, hata ayıklamanın duraklatılmış olduğu ve aynı noktada uygulama yürütmesini de askıya alan deyimi temsil eder (bu bildirim henüz yürütülmedi).

     Uygulama henüz çalışmıyorsa, **F5** hata ayıklamayı başlatır ve ilk kesme noktasında durur. Aksi takdirde, **F5** uygulamayı bir sonraki kesme noktasına çalıştırmaya devam edin.

    Kesme noktaları, kod satırını veya ayrıntılı olarak incelemek istediğiniz kod bölümünü bildiğinizde yararlı bir özelliktir. Koşullu kesme noktaları gibi ayarlayabildiğiniz farklı kesme noktaları türleri hakkında bilgi [için](../../debugger/using-breakpoints.md)bkz.

## <a name="navigate-code-in-the-debugger-using-step-commands"></a>Adım komutlarını kullanarak hata ayıklayıcıda kodda gezinme

Çoğunlukla, hata ayıklamada uygulamanızı yürütmede hızlı olmak için iyi bir yol olduğundan burada klavye kısayollarını kullanırız (menü komutları gibi eşdeğer komutlar parantez içinde gösterilir).

1. `Main` Yöntemde `For` döngü içinde duraklatılmış iken, `SendMessage` yöntem çağrısına ilerlemek için **F11** 'e (veya Hata **Ayıklama > Adım Adım)** iki kez seçin.

     **F11 tuşuna** iki kez bastıktan sonra, bu kod satırında olmalısınız:

     `SendMessage(name, a(i))`

1. `SendMessage` Yönteme adım atmak için **F11** tuşuna bir kez daha basın.

     Sarı işaretçi `SendMessage` yönteme ilerler.

     ![Koda Adım Atmak için F11'i kullanma](../visual-basic/media/get-started-f11-vb.png "F10 Adım Adım")

     F11, **Step Into** komutudur ve uygulama yürütmeyi bir er seferde bir ekibe iletir. F11, yürütme akışını en ayrıntılı olarak incelemek için iyi bir yoldur. (Kod üzerinden daha hızlı hareket etmek için, size diğer bazı seçenekleri de gösteririz.) Varsayılan olarak, hata ayıklayıcı kullanıcı olmayan kodu atlar (daha fazla ayrıntı istiyorsanız, [Bkz. Just My Code).](../../debugger/just-my-code.md)

     Yöntemi incelemeyi `SendMessage` bitirdiğinizi ve yöntemden çıkmak ama hata ayıklamada kalmak istediğinizi varsayalım. Bunu **Step Out** komutunu kullanarak yapabilirsiniz.

1. **Shift** + **F11** tuşuna basın (veya **Hata Ayıklama > Adım Dışarı**).

     Bu komut, geçerli yöntem veya işlev dönene kadar uygulama yürütmeyi devam ettirer (ve hata ayıklayıcıyı ilerler).

     Yöntemde `For` döngüye geri dönmelisiniz, `SendMessage` yöntem çağrısında duraklatılmalısınız. `Main`

1. Yöntem çağrısına `SendMessage` geri dönene kadar **F11** tuşuna birkaç kez basın.

1. Yöntem çağrısında duraklatırken, **F10'a** (veya **Hata Ayıklama > Adımı)** bir kez seçin.

     ![Kodu Aşmak için F10'u kullanma](../visual-basic/media/get-started-step-over-vb.png "F10 Adım Üstü")

     Hata ayıklamanın yönteme adım atmadığını `SendMessage` bu kez fark edin. **F10,** hata ayıklayıcıyı uygulama kodunuzdaki işlevlere veya yöntemlere adım atmadan ilerler (kod hala yürütülür). Yöntem aramasında **F10** tuşuna `SendMessage` basarak **(F11**yerine), uygulama `SendMessage` kodunu atladık (belki de şu anda ilgilenmiyoruz). Kodunuzda gezinmenin farklı yolları hakkında daha fazla bilgi için [hata ayıklayıcıda kodu gezin'](../../debugger/navigating-through-code-with-the-debugger.md)e bakın.

## <a name="navigate-code-using-run-to-click"></a>Tıklatmak Için Çalıştır'ı kullanarak kodda gezinme

1. Kırılma noktasına tekrar ilerlemek için **F5** tuşuna basın.

1. Kod düzenleyicisinde, soltarafta yeşil **Tıklat'a** `SendMessage` Çalıştır düğmesi ![belirene](../../debugger/media/dbg-tour-run-to-click.png "RunToClick") kadar `Console.WriteLine` yöntemdeki yöntemin üzerine gidin ve gidin. Düğmenin araç ucu "Yürütmeyi buraya çalıştır" düğmesini gösterir.

     ![Tıklatma özelliğini kullan](../visual-basic/media/get-started-run-to-click-vb.png "Tıklanan Satıra Kadar Çalıştır")

   > [!NOTE]
   > **Tıklatmak için Çalıştır** düğmesi [!include[vs_dev15](../../misc/includes/vs_dev15_md.md)]' nde yeni (Yeşil ok düğmesini görmüyorsanız, hata ayıklamayı doğru yere ilerlemek için bu örnekte **F11'i** kullanın.)

2. **Tıklatma düğmesine** tıklayın ![Tıkla ' yı tıklatın.](../../debugger/media/dbg-tour-run-to-click.png "RunToClick")

    Hata ayıklama `Console.WriteLine` yöntemine ilerler.

    Bu düğmeyi kullanmak geçici bir kesme noktası ayarlamaya benzer. **Run to Click,** uygulama kodunun görünür bir bölgesinde hızlı bir şekilde gezinmek için kullanışlıdır (herhangi bir açık dosyayı tıklayabilirsiniz).

## <a name="restart-your-app-quickly"></a>Uygulamanızı hızla yeniden başlatın

Hata Ayıklama Araç Çubuğu'ndaki **(Ctrl** + **Shift** + **F5)** Uygulamayı Yeniden **Başlat** ![Restart App](../../debugger/media/dbg-tour-restart.png "Yeniden BaşlatApp") düğmesini tıklatın.

**Yeniden Başlat**tuşuna bastığınızda, uygulamayı durdurmak ve hata ayıklamayı yeniden başlatmak karşı zaman kazandırır. Hata ayıklayıcı, yürütme kodu tarafından vurulan ilk kesme noktasında duraklar.

Hata ayıklama, daha önce `For` döngü içinde ayarladığınız kesme noktasında yeniden durur.

## <a name="inspect-variables-with-data-tips"></a>Değişkenleri veri ipuçlarıyla inceleyin

Değişkenleri incelemenize olanak tanıyan özellikler hata ayıklamanın en yararlı özelliklerinden biridir ve bunu yapmanın farklı yolları vardır. Genellikle, bir sorunu hata ayıklamaya çalıştığınızda, değişkenlerin belirli bir anda sahip olmasını beklediğiniz değerleri depolayıp depolamadığını bulmaya çalışırsınız.

1. İfadeüzerinde duraklatılsa `name += letters[i]` da, değişkenin `letters` üzerine gezinirve bunun varsayılan değerini, dizideki `"f"c`ilk öğenin değerini görürsünüz.

1. Sonra, değişkenin `name` üzerine basın ve şimdiki değerini, boş bir dizeyi görürsünüz.

1. `For` **F5** (veya **Hata Ayıklama** > **Devam)** tuşuna birkaç kez basarak döngü boyunca birkaç kez yineleyin, `name` kesme noktasında yeniden duraklayın ve değerini kontrol etmek için her seferinde değişkenin üzerinde gezinin.

     ![Veri ipucunu görüntüleme](../visual-basic/media/get-started-data-tip-vb.png "Veri İpucunu Görüntüleme")

     Değişkenin `For` değeri, döngünün her yinelemesi ile değişir `f`ve `fr`değerlerini `fre`, sonra , sonra , ve benzeri değerleri gösterir.

     Genellikle, hata ayıklama yaparken, değişkenler üzerindeki özellik değerlerini denetlemek için hızlı bir yol istersiniz, bunların depolamasını beklediğiniz değerleri depolayıp depolamadıklarını görmek için ve veri ipuçları bunu yapmak için iyi bir yoldur.

## <a name="inspect-variables-with-the-autos-and-locals-windows"></a>Otomatik ve Yerel pencerelerle değişkenleri inceleyin

1. Kod düzenleyicisinin altındaki **Otomatik ler** penceresine bak.

    Kapalıysa, hata ayıklamada hata ayıklama sırasında hata ayıklama sırasında hata **ayıklama** > **Windows** > **Autos**seçerek açın.

    Otomatik **Ler** penceresinde değişkenleri ve bunların geçerli değerini görürsünüz. **Otomatik Ler** penceresi geçerli satırda veya önceki satırda kullanılan tüm değişkenleri gösterir (dile özgü davranış için belgeleri denetleyin).

1. Ardından, **Otomatik** **Ler** penceresinin yanındaki sekmede Yerel ler penceresine bakın.

1. İçerdiği öğeleri göstermek için değişkeni `letters` genişletin.

     ![Yerel Ler Penceresindeki değişkenleri inceleyin](../visual-basic/media/get-started-locals-window-vb.png "Yerel Pencere")

    **Locals** penceresi, geçerli [kapsamdaki](https://www.wikipedia.org/wiki/Scope_(computer_science))değişkenleri , yani geçerli yürütme bağlamını gösterir.

## <a name="set-a-watch"></a>Bir saat ayarlama

1. Ana kod düzenleyicisi penceresinde, `name` değişkene sağ tıklayın ve **İzle Ekle'yi**seçin.

    Kod düzenleyicisinin alt kısmında **Saat** penceresi açılır. İzlemek istediğiniz bir değişkeni (veya ifadeyi) belirtmek için **İzleme** penceresini kullanabilirsiniz.

    Şimdi, `name` değişkenüzerinde bir saat setiniz var ve hata ayıklamada hareket ettikçe değerinin değiştiğini görebilirsiniz. Diğer değişken pencerelerin aksine, **İzleme** penceresi her zaman izlediğiniz değişkenleri gösterir (kapsam dışında olduklarında gri renktedirler).

## <a name="examine-the-call-stack"></a>Arama yığınını inceleme

1. Döngüde duraklatılırken, sağ alt bölmede varsayılan olarak açık olan Yığın Çağır penceresini tıklatın. **Call Stack** `For`

    Kapalıysa, hata ayıklama da hata**ayıklama**sırasında **hata ayıklama** > **Windows** > Çağrı Yığını seçerek duraklatılmış iken açın.

2. `SendMessage` Yöntemde hata ayıklama duraklamasını görene kadar **F11'i** birkaç kez tıklatın. **Çağrı Yığını** penceresine bak.

    ![Arama yığınını inceleme](../visual-basic/media/get-started-call-stack-vb.png "CallStack'i İncele")

    **Çağrı Yığını** penceresi, yöntemlerin ve işlevlerin çağrılma sırasını gösterir. Üst satır geçerli işlevi (bu uygulamadaki `SendMessage` yöntem) gösterir. İkinci satır, `SendMessage` yöntemden çağrıldıve `Main` benzeri gösterir.

   > [!NOTE]
   > **Arama Yığını** penceresi Eclipse gibi bazı IDA'larda Hata Ayıklama perspektifine benzer.

    Arama yığını, bir uygulamanın yürütme akışını incelemek ve anlamak için iyi bir yoldur.

    Kaynak kodu na bakmak için bir kod satırına çift tıklayabilirsiniz ve bu da hata ayıklayıcı tarafından denetlenen geçerli kapsamı değiştirir. Bu eylem hata ayıklama ilerlemez.

    Başka şeyler yapmak için **Yığın Çağır** penceresinden sağ tıklatma menülerini de kullanabilirsiniz. Örneğin, kesme noktalarını belirtilen işlevlere ekleyebilir, Hata ayıklayıcıyı **Çalıştır'ı kullanarak Imleç'e**ilerleyebilir ve kaynak kodunu incelemeye gidebilirsiniz. Daha fazla bilgi için [bkz: Arama Yığınını Inceleyin.](../../debugger/how-to-use-the-call-stack-window.md)

## <a name="change-the-execution-flow"></a>Yürütme akışını değiştirme

1. Yöntemi çalıştırmak için iki `Console.WriteLine` kez **F11** tuşuna basın.

1. `SendMessage` Hata ayıklama yöntemi çağrısında duraklatılmışken, soldaki sarı oku (yürütme işaretçisi) kapmak için fareyi `Console.WriteLine`kullanın ve sarı oku bir satıryukarı doğru hareket ettirin.

1. **F11 tuşuna**basın.

    Hata ayıklama yöntemini `Console.WriteLine` yeniden çalıştırAr (bunu konsol penceresi çıkışında görürsünüz).

    Yürütme akışını değiştirerek, hata ayıklayıcıyı yeniden başlatmadan farklı kod yürütme yollarını sınamak veya kodu yeniden çalıştırmak gibi şeyler yapabilirsiniz.

    > [!WARNING]
    > Genellikle bu özellik ile dikkatli olmak gerekir ve araç ucunda bir uyarı bakın. Başka uyarılar da görebilirsiniz. İşaretçiyi taşımak, uygulamanızı önceki bir uygulama durumuna geri çeviremez.

1. Uygulamayı çalıştırmaya devam etmek için **F5** tuşuna basın.

    Bu öğretici tamamladıktan sonra tebrikler!

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, hata ayıklayıcıyı başlatmayı, koda nasıl basabileceğinizi ve değişkenleri nasıl inceleyincenizi öğrendiniz. Hata ayıklama özelliklerine daha fazla bilgi bağlantılarıyla birlikte üst düzey bir görünüm elde etmek isteyebilirsiniz.

> [!div class="nextstepaction"]
> [Hata ayıklayıcıya ilk bakış](../../debugger/debugger-feature-tour.md)
