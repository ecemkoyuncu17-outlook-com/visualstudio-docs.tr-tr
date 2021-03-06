---
title: Eşzamanlılık özel durumunu işleme | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- concurrency control, exceptions
- datasets [Visual Basic], errors
- exception handling, concurrency issues
- data concurrency, walkthroughs
- updating datasets, errors
- concurrency control, walkthroughs
ms.assetid: 73ee9759-0a90-48a9-bf7b-9d6fc17bff93
caps.latest.revision: 27
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 1b3f9bdaf5107f805100b938212128d42c0263dd
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72670034"
---
# <a name="handle-a-concurrency-exception"></a>Bir eşzamanlılık özel durumunu işleme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Eşzamanlılık özel durumları (<xref:System.Data.DBConcurrencyException>) iki kullanıcı aynı anda bir veritabanında aynı verileri değiştirmeye çalıştıklarında tetiklenir. Bu kılavuzda, bir <xref:System.Data.DBConcurrencyException> nasıl yakalayacağınızı gösteren bir Windows uygulaması oluşturacaksınız, hataya neden olan satırı nasıl bulabileceğinizi ve nasıl işleyeceğinizi gösteren bir strateji öğreneceksiniz.

 Bu izlenecek yol, aşağıdaki işlem boyunca size kılavuzluk eden bir işlemdir:

1. Yeni bir **Windows uygulaması** projesi oluşturun.

2. Northwind `Customers` tablosunu temel alan yeni bir veri kümesi oluşturun.

3. Verileri göstermek için <xref:System.Windows.Forms.DataGridView> bir form oluşturun.

4. Northwind veritabanındaki `Customers` tablodaki verileri içeren bir veri kümesini doldur.

5. @No__t_1 veri tablosuna doğrudan erişmek ve bir kaydı değiştirmek için Visual Studio 'daki [Visual veritabanı araçları](https://msdn.microsoft.com/6b145922-2f00-47db-befc-bf351b4809a1) 'nı kullanın.

6. Aynı kaydı farklı bir değerle değiştirin, veri kümesini güncelleştirin ve değişiklikleri veritabanına yazmayı deneyin, bu da bir eşzamanlılık hatası oluşur.

7. Hatayı Yakalayın, ardından kaydın farklı sürümlerini görüntüleyin, böylece kullanıcının devam edip etmeyeceğini veya güncelleştirmeyi iptal edip etmediğini belirlemesine izin verir.

## <a name="prerequisites"></a>Prerequisites
 Bu izlenecek yolu tamamlamak için şunlar gerekir:

- Güncelleştirme gerçekleştirme izniyle Northwind örnek veritabanına erişim.

> [!NOTE]
> Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza veya kullandığınız sürüme bağlı olarak yardım bölümünde açıklananlardan farklı bir durum içerebilir. Ayarlarınızı değiştirmek için **Araçlar** menüsünden **Içeri ve dışarı aktarma ayarları** ' nı seçin. Daha fazla bilgi için bkz. [Visual Studio 'Da geliştirme ayarlarını özelleştirme](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).

## <a name="create-a-new-project"></a>Yeni bir proje oluşturma
 Yeni bir Windows uygulaması oluşturarak adım adım kullanmaya başlayabilirsiniz.

#### <a name="to-create-a-new-windows-application-project"></a>Yeni bir Windows uygulaması projesi oluşturmak için

1. **Dosya** menüsünde Yeni bir proje oluşturun.

2. **Proje türleri** bölmesinde bir programlama dili seçin.

3. **Şablonlar** bölmesinde **Windows uygulaması**' nı seçin.

4. Projeyi `ConcurrencyWalkthrough` olarak adlandırın ve ardından **Tamam**' ı seçin.

     Visual Studio, projeyi **Çözüm Gezgini** ekler ve tasarımcıda yeni bir form görüntüler.

## <a name="create-the-northwind-dataset"></a>Northwind veri kümesini oluşturma
 Bu bölümde, `NorthwindDataSet` adlı bir veri kümesi oluşturursunuz.

#### <a name="to-create-the-northwinddataset"></a>NorthwindDataSet 'i oluşturmak için

1. **Veri** menüsünde **Yeni veri kaynağı Ekle**' yi seçin.

     [Veri kaynağı Yapılandırma Sihirbazı](https://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f) açılır.

2. **Veri kaynağı türü seçin**ekranında **veritabanı**' nı seçin.

3. Kullanılabilir bağlantılar listesinden Northwind örnek veritabanına bir bağlantı seçin. Bağlantı listesinde bağlantı yoksa,**Yeni bağlantı** ' yı seçin.

    > [!NOTE]
    > Bir yerel veritabanı dosyasına bağlanıyorsanız, dosyayı projenize eklemek isteyip istemediğiniz sorulduğunda **Hayır** ' ı seçin.

4. **Bağlantı dizesini uygulama yapılandırma dosyasına kaydet**ekranında, **İleri**' yi seçin.

5. **Tablolar** düğümünü genişletin ve `Customers` tablosunu seçin. Veri kümesi için varsayılan ad `NorthwindDataSet` olmalıdır.

6. Veri kümesini projeye eklemek için **son** ' u seçin.

## <a name="create-a-data-bound-datagridview-control"></a>Veri bağlantılı DataGridView denetimi oluşturma
 Bu bölümde, **müşteriler** öğesini **veri kaynakları** penceresinden Windows formunuzun üzerine sürükleyerek bir <xref:System.Windows.Forms.DataGridView> oluşturursunuz.

#### <a name="to-create-a-datagridview-control-that-is-bound-to-the-customers-table"></a>Müşteriler tablosuna bağlanan bir DataGridView denetimi oluşturmak için

1. Veri **Kaynakları penceresini**açmak için **veri** menüsünde **veri kaynaklarını göster** ' i seçin.

2. **Veri kaynakları** penceresinde **NorthwindDataSet** düğümünü genişletin ve ardından **Customers** tablosunu seçin.

3. Tablo düğümünde aşağı oku seçin ve ardından açılır listeden **DataGridView** ' i seçin.

4. Tabloyu formunuzun boş bir alanının üzerine sürükleyin.

     @No__t_1 adlı ve `CustomersBindingNavigator` adlı bir <xref:System.Windows.Forms.BindingNavigator> <xref:System.Windows.Forms.DataGridView> denetim, <xref:System.Windows.Forms.BindingSource> bağlantılı forma eklenir. Bu, içinde olduğu için `Customers` `NorthwindDataSet` tablosuna bağımlıdır.

## <a name="test-the-form"></a>Formu test etme
 Artık formu, bu noktaya kadar beklenildiği şekilde davrandığından emin olmak için test edebilirsiniz.

#### <a name="to-test-the-form"></a>Formu test etmek için

1. Uygulamayı çalıştırmak için **F5** ' i seçin

     Form, `Customers` tablosundan alınan verilerle doldurulan <xref:System.Windows.Forms.DataGridView> bir denetim ile görüntülenir.

2. **Hata Ayıkla** menüsünde,**hata ayıklamayı Durdur**' u seçin.

## <a name="handleconcurrency-errors"></a>Handleconcurrency hataları
 Hataları nasıl işleyeceğinizi, uygulamanızı yöneten belirli iş kurallarına bağlıdır. Bu kılavuzda, eşzamanlılık hatasını nasıl işleyeceğinizi gösteren bir örnek olarak aşağıdaki stratejiyi kullanırız.

 ApplicationA, kullanıcıya kaydın üç sürümünü sunar:

- Veritabanındaki geçerli kayıt

- Veri kümesine yüklenen özgün kayıt

- Veri kümesindeki önerilen değişiklikler

  Böylece Kullanıcı önerilen sürümle birlikte veritabanının üzerine yazabilir veya güncelleştirmeyi iptal edebilir ve veri kümesini veritabanından yeni değerlerle yenileyebilir.

#### <a name="to-enable-the-handling-of-concurrency-errors"></a>Eşzamanlılık hatalarının işlenmesini etkinleştirmek için

1. Özel bir hata işleyicisi oluşturun.

2. Kullanıcılara seçenekleri görüntüleyin.

3. Kullanıcının yanıtını işleyin.

4. Güncelleştirmeyi yeniden gönderin veya veri kümesindeki verileri sıfırlayın.

### <a name="addcode-to-handle-the-concurrency-exception"></a>Eşzamanlılık özel durumunu işlemek için AddCode
 Bir güncelleştirme gerçekleştirmeye çalıştığınızda ve bir özel durum ortaya çıktığında, genellikle oluşturulan özel durum tarafından verilen bilgilerle ilgili bir şey yapmak istersiniz.

 Bu bölümde, veritabanını güncelleştirmeyi deneyen kodu eklersiniz. Ayrıca, başka özel durumlar da ortaya çıkan <xref:System.Data.DBConcurrencyException> de işleyebilirsiniz.

> [!NOTE]
> @No__t_0 ve `ProcessDialogResults` yöntemleri Bu izlenecek yolda daha sonra eklenecektir.

##### <a name="to-add-error-handling-for-the-concurrency-error"></a>Eşzamanlılık hatası için hata işleme eklemek için

1. @No__t_0 yönteminin altına aşağıdaki kodu ekleyin:

     [!code-csharp[VbRaddataConcurrency#1](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataConcurrency/CS/Form1.cs#1)]
     [!code-vb[VbRaddataConcurrency#1](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataConcurrency/VB/Form1.vb#1)]

2. @No__t_0 yöntemini, aşağıdaki gibi görünmesi için `UpdateDatabase` yöntemini çağırmak üzere değiştirin:

     [!code-csharp[VbRaddataConcurrency#2](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataConcurrency/CS/Form1.cs#2)]
     [!code-vb[VbRaddataConcurrency#2](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataConcurrency/VB/Form1.vb#2)]

### <a name="displaychoices-to-the-user"></a>Kullanıcıya displayseçimlerinizi
 Yeni yazdığınız kod, kullanıcıya hata bilgilerini göstermek için `CreateMessage` yordamını çağırır. Bu izlenecek yol için, kaydın farklı sürümlerini kullanıcıya göstermek üzere bir ileti kutusu kullanın. Bu, kullanıcının değişikliklerle ilgili kaydın üzerine yazılıp yazılmayacağını veya düzenlemeyi iptal edip etmediğini seçmesini sağlar. Kullanıcı, ileti kutusunda bir seçenek seçtiğinde (bir düğmeye tıkladığında), yanıt `ProcessDialogResult` yöntemine geçirilir.

##### <a name="to-create-the-message-to-display-to-the-user"></a>Kullanıcıya görüntülenecek iletiyi oluşturmak için

- **Kod düzenleyicisine**aşağıdaki kodu ekleyerek iletiyi oluşturun. @No__t_0 yönteminin altına bu kodu girin.

     [!code-csharp[VbRaddataConcurrency#4](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataConcurrency/CS/Form1.cs#4)]
     [!code-vb[VbRaddataConcurrency#4](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataConcurrency/VB/Form1.vb#4)]

### <a name="process-the-users-response"></a>Kullanıcının yanıtını işle
 Kullanıcının ileti kutusuna yanıtını işlemek için de kod gerekir. Seçenekler, önerilen değişiklikle veritabanındaki geçerli kaydın üzerine yazar veya yerel değişiklikleri iptal edebilir ve veri tablosunu veritabanında Şu anda olan kayıtla yeniler. Kullanıcı Evet ' i seçerse <xref:System.Data.DataTable.Merge%2A> yöntemi *PreserveChanges* bağımsız değişkeni `true` olarak ayarlanır. Bu, kaydın orijinal sürümü artık veritabanındaki kayıtla eşleştiğinden güncelleştirme denemesinin başarılı olmasına neden olur.

##### <a name="to-process-the-user-input-from-the-message-box"></a>İleti kutusundan Kullanıcı girişini işlemek için

- Önceki bölümde eklenmiş olan kodun altına aşağıdaki kodu ekleyin.

     [!code-csharp[VbRaddataConcurrency#3](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataConcurrency/CS/Form1.cs#3)]
     [!code-vb[VbRaddataConcurrency#3](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataConcurrency/VB/Form1.vb#3)]

## <a name="test-the-form"></a>Formu test etme
 Artık, beklenen şekilde davrandığından emin olmak için formu test edebilirsiniz. Bir eşzamanlılık ihlalinin benzetimini yapmak için, NorthwindDataSet 'i doldurduktan sonra veritabanındaki verileri değiştirmeniz gerekir.

#### <a name="to-test-the-form"></a>Formu test etmek için

1. Uygulamayı çalıştırmak için **F5** ' i seçin.

2. Form görüntülendikten sonra çalışır durumda bırakın ve Visual Studio IDE 'ye geçin.

3. **Görünüm** menüsünde **Sunucu Gezgini**' yi seçin.

4. **Sunucu Gezgini**, uygulamanızın kullandığı bağlantıyı genişletin ve **Tablolar** düğümünü genişletin.

5. **Müşteriler** tablosuna sağ tıklayın ve ardından **tablo verilerini göster**' i seçin.

6. İlk kayıtta (`ALFKI`) `ContactName` `Maria Anders2` olarak değiştirin.

    > [!NOTE]
    > Değişikliği uygulamak için farklı bir satıra gidin.

7. @No__t_0 çalışan biçimine geçiş yapın.

8. Formdaki ilk kayıtta (`ALFKI`) `ContactName` `Maria Anders1` olarak değiştirin.

9. **Kaydet** düğmesini seçin.

     Eşzamanlılık hatası oluşur ve ileti kutusu görüntülenir.

10. **Hayır** seçilirse güncelleştirme iptal edilir ve veri kümesini veritabanında Şu anda olan değerlerle günceller. **Evet** seçildiğinde önerilen değer veritabanına yazılır.

## <a name="see-also"></a>Ayrıca Bkz.

- [Verileri yeniden veritabanına kaydetme](../data-tools/save-data-back-to-the-database.md)