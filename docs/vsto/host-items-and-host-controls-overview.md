---
title: Konak öğeleri ve konak denetimlerine genel bakış
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- host controls [Office development in Visual Studio], adding
- Office documents [Office development in Visual Studio, host controls
- host items [Office development in Visual Studio]
- application development [Office development in Visual Studio], host items
- Office applications [Office development in Visual Studio], host items
- host controls [Office development in Visual Studio], listed
- Excel [Office development in Visual Studio], host items
- host controls [Office Development in Visual Stuio], naming
- host controls [Office development in Visual Studio]
- host controls [Office development in Visual Studio], about host controls
- document-level customizations [Office development in Visual Studio], host controls
- Office applications [Office development in Visual Studio], host controls
- documents [Office development in Visual Studio], host controls
- controls [Office development in Visual Studio], host controls
- application development [Office development in Visual Studio], host controls
- Excel [Office development in Visual Studio], host controls
- host items [Office development in Visual Studio], about host items
- host items [Office development in Visual Studio], listed
- documents [Office development in Visual Studio], host items
- data binding [Office development in Visual Studio], host controls
- Office documents [Office development in Visual Studio, host items
- Word [Office development in Visual Studio], host items
- document-level customizations [Office development in Visual Studio], host items
- Word [Office development in Visual Studio], host controls
- host controls [Office development in Visual Studio], deleting
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: c349756eb12fe66800e209bd6a1aad5b8d2337ab
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71255925"
---
# <a name="host-items-and-host-controls-overview"></a>Konak öğeleri ve konak denetimlerine genel bakış
  Konak öğeleri ve konak denetimleri, Visual Studio 'da Office geliştirme araçları kullanılarak oluşturulan Office çözümlerine yönelik programlama modelinin sağlanmasına yardımcı olan türlerdir. Konak öğeleri ve konak denetimleri, COM 'a dayalı Microsoft Office Word ve Microsoft Office Excel 'in nesne modelleriyle etkileşim kuran Windows Forms denetimleri gibi yönetilen nesnelerle etkileşim kurma gibi.

 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]

## <a name="host-items"></a>Konak öğeleri
 Konak öğeleri, Office projelerinde nesne modeli hiyerarşilerinin en üstünde yer alan türlerdir. Word ve Excel çözümleri için aşağıdaki konak öğelerini tanımlar:[!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]

- <xref:Microsoft.Office.Tools.Word.Document>

- <xref:Microsoft.Office.Tools.Excel.Workbook>

- <xref:Microsoft.Office.Tools.Excel.Worksheet>

- <xref:Microsoft.Office.Tools.Excel.ChartSheet>

  Bu türlerin her biri, *yerel bir Office nesnesi*olarak adlandırılan Word veya Excel nesne modelinde yerel olarak var olan bir nesneyi genişletir. Örneğin, <xref:Microsoft.Office.Tools.Word.Document> konak öğesi, Word için birincil <xref:Microsoft.Office.Interop.Word.Document> birlikte çalışma derlemesinde tanımlanan nesneyi genişletir.

  Ana bilgisayar öğeleri genellikle karşılık gelen Office nesneleriyle aynı temel işlevlere sahiptir, ancak aşağıdaki özelliklerle geliştirilmiştir:

- Konak denetimleri ve Windows Forms denetimleri dahil olmak üzere yönetilen denetimleri barındırma özelliği.

- Daha zengin olay modelleri. Yerel Word ve Excel nesne modelleriyle bazı belge, çalışma kitabı ve çalışma sayfası olayları yalnızca uygulama düzeyinde oluşturulur. Konak öğeleri, bu olayları belge düzeyinde sağlar, böylece belirli bir belge için olayları işlemek daha kolay olur.

### <a name="understand-host-items-in-document-level-projects"></a>Belge düzeyi projelerdeki konak öğelerini anlama
 Belge düzeyi projelerinde, konak öğeleri kodunuz için bir giriş noktası sağlar ve çözümünüzü geliştirmenize yardımcı olan tasarımcılara sahiptir.

 <xref:Microsoft.Office.Tools.Word.Document> Ve<xref:Microsoft.Office.Tools.Excel.Worksheet> ana bilgisayar öğelerinde, Windows Forms Tasarımcısı gibi belge veya çalışma sayfasının görsel temsili olan ilişkili tasarımcılar vardır. Bu Tasarımcıyı kullanarak belge veya çalışma sayfasının içeriğini doğrudan Word veya Excel 'de değiştirebilir ve denetimleri tasarım yüzeyine sürükleyebilirsiniz. Daha fazla bilgi için bkz. [belge konak öğesi](../vsto/document-host-item.md) ve [çalışma sayfası konak öğesi](../vsto/worksheet-host-item.md).

 Konak <xref:Microsoft.Office.Tools.Excel.Workbook> öğesi, Kullanıcı arabirimine sahip denetimler için kapsayıcı görevi yapmaz. Bunun yerine, bu konak öğesi için tasarımcı, bir <xref:System.Data.DataSet>bileşeni gibi bir bileşeni tasarım yüzeyine sürüklemenize olanak tanıyan bir bileşen tepsisi işlevi görür. Daha fazla bilgi için bkz. [çalışma kitabı konak öğesi](../vsto/workbook-host-item.md).

 Konak öğeleri belge düzeyi projelerde program aracılığıyla oluşturulamaz. Bunun yerine, Visual `ThisDocument`Studio 'nun projenizde `Sheet`tasarım zamanında otomatik olarak oluşturduğu, `ThisWorkbook`veya *n* sınıflarını kullanın. Oluşturulan bu sınıflar konak öğelerinden türetilir ve kodunuz için bir giriş noktası sağlar. Daha fazla bilgi için bkz. [konak öğelerinin ve konak denetimlerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).

### <a name="understand-host-items-in-vsto-add-in-projects"></a>VSTO eklentisi projelerinde konak öğelerini anlama
 Bir VSTO eklentisi oluşturduğunuzda, varsayılan olarak herhangi bir konak öğesine erişiminiz olmaz. Ancak, çalışma zamanında Word <xref:Microsoft.Office.Tools.Word.Document>ve <xref:Microsoft.Office.Tools.Excel.Workbook>Excel VSTO <xref:Microsoft.Office.Tools.Excel.Worksheet> Eklentilerindeki öğeleri oluşturabilir, ve barındırabilirsiniz.

 Bir konak öğesi oluşturduktan sonra belgelere denetim ekleme gibi görevleri gerçekleştirebilirsiniz. Daha fazla bilgi için bkz. [çalışma ZAMANıNDA VSTO Eklentilerindeki Word belgelerini ve Excel çalışma kitaplarını genişletme](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).

## <a name="host-controls"></a>Konak denetimleri
 Konak denetimleri Word ve Excel nesne modellerindeki `Microsoft.Office.Interop.Word.ContentControl` ve <xref:Microsoft.Office.Interop.Excel.Range> nesneler gibi çeşitli kullanıcı arabirimi (UI) nesnelerini genişletir.

 Aşağıdaki konak denetimleri Excel projeleri için kullanılabilir:

- [Grafik denetimi](../vsto/chart-control.md)

- [ListObject denetimi](../vsto/listobject-control.md)

- [NamedRange denetimi](../vsto/namedrange-control.md)

- [XmlMappedRange denetimi](../vsto/xmlmappedrange-control.md)

  Aşağıdaki konak denetimleri Word projeleri için kullanılabilir:

- [Yer işareti denetimi](../vsto/bookmark-control.md)

- [İçerik denetimleri](../vsto/content-controls.md)

- [XMLNode denetimi](../vsto/xmlnode-control.md)

- [XMLNodes denetimi](../vsto/xmlnodes-control.md)

  Office belgelerine eklenen ana bilgisayar denetimleri, yerel Office nesneleri gibi davranır; Ancak, ana bilgisayar denetimleri, olaylar ve veri bağlama özellikleri dahil olmak üzere ek işlevlere sahiptir. Örneğin, Excel 'deki bir yerel <xref:Microsoft.Office.Interop.Excel.Range> nesnenin olaylarını yakalamak istediğinizde, önce çalışma sayfasının değişiklik olayını işlemeniz gerekir. Ardından, <xref:Microsoft.Office.Interop.Excel.Range>değişikliğin içinde oluşup oluşmadığını belirlemelisiniz. Buna karşılık, <xref:Microsoft.Office.Tools.Excel.NamedRange> konak denetiminin doğrudan işleyebilmeniz <xref:Microsoft.Office.Tools.Excel.NamedRange.Change> için bir olayı vardır.

  Bir konak öğesi ve konak denetimleri arasındaki ilişki, bir Windows form ve Windows Forms denetimleri arasındaki ilişkiye benzerdir. Bir Windows formuna metin kutusu denetimi yerleştirdiğiniz gibi, bir <xref:Microsoft.Office.Tools.Excel.NamedRange> <xref:Microsoft.Office.Tools.Excel.Worksheet> konak öğesine bir denetim yerleştirebilirsiniz. Aşağıdaki çizimde konak öğeleri ve konak denetimleri arasındaki ilişki gösterilmektedir.

  ![Konak öğeleri ve konak denetimleri arasındaki ilişki](../vsto/media/hostitemscontrols.png "Konak öğeleri ve konak denetimleri arasındaki ilişki")

  Office çözümlerinizde Windows Forms denetimlerini doğrudan Word ve Excel belge yüzeyine ekleyerek de kullanabilirsiniz. Daha fazla bilgi için bkz. [Office belgelerindeki Windows Forms denetimleri genel bakış](../vsto/windows-forms-controls-on-office-documents-overview.md).

> [!NOTE]
> Bir Word alt belgesinde konak denetimleri veya Windows Forms denetimleri ekleme desteklenmez.

### <a name="add-host-controls-to-your-documents"></a>Belgelerinize konak denetimleri ekleyin
 Belge düzeyi projelerinde, tasarım zamanında Word belgelerinize veya Excel çalışma sayfalarına aşağıdaki yollarla konak denetimleri ekleyebilirsiniz:

- Belgenize, bir yerel nesne ekleyeceğiniz şekilde tasarım zamanında konak denetimleri ekleyin.

- **Araç kutusundan** , ana bilgisayar denetimlerini belgelerinize ve çalışma sayfalarına sürükleyin. Excel konak denetimleri Excel projelerinde Excel **denetimleri** sekmesinde bulunur ve Word konak denetimleri Word projeleri ' nde Word **denetimleri** sekmesinde bulunur.

- Konak denetimlerini, **veri kaynakları** penceresinden belge ve çalışma sayfalarına sürükleyin. Bu, verilere zaten bağlanan denetimler eklemenize olanak sağlar. Daha fazla bilgi için bkz. [Office çözümlerinde verileri denetimlere bağlama](../vsto/binding-data-to-controls-in-office-solutions.md).

  Belge düzeyi ve VSTO eklenti projelerinde, çalışma zamanında belgelere bazı konak denetimleri de ekleyebilirsiniz. Daha fazla bilgi için bkz. [çalışma zamanında Office belgelerine denetim ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).

  Belgelere konak denetimleri ekleme hakkında daha fazla bilgi için aşağıdaki konulara bakın:

- [Nasıl yapılır: Çalışma sayfalarına Grafik denetimleri ekleme](../vsto/how-to-add-chart-controls-to-worksheets.md)

- [Nasıl yapılır: Çalışma sayfalarına ListObject denetimleri ekleme](../vsto/how-to-add-listobject-controls-to-worksheets.md)

- [Nasıl yapılır: Çalışma sayfalarına NamedRange denetimleri ekleme](../vsto/how-to-add-namedrange-controls-to-worksheets.md)

- [Nasıl yapılır: Çalışma sayfalarına XMLMappedRange denetimleri ekleme](../vsto/how-to-add-xmlmappedrange-controls-to-worksheets.md)

- [Nasıl yapılır: Word belgelerine yer Işareti denetimleri ekleme](../vsto/how-to-add-bookmark-controls-to-word-documents.md)

- [Nasıl yapılır: Word belgelerine Içerik denetimleri ekleme](../vsto/how-to-add-content-controls-to-word-documents.md)

- [Nasıl yapılır: Word belgelerine XMLNode denetimleri ekleme](../vsto/how-to-add-xmlnode-controls-to-word-documents.md)

- [Nasıl yapılır: Word belgelerine XMLNodes denetimleri ekleme](../vsto/how-to-add-xmlnodes-controls-to-word-documents.md)

### <a name="name-host-controls"></a>Konak denetimlerini Adlandır
 **Araç kutusundan** bir konak denetimini belgenize sürüklediğinizde Denetim, sonunda artımlı bir sayı ile denetim türü kullanılarak otomatik olarak adlandırılır. Örneğin, yer işaretleri **Bookmark1**, **bookmark2**vb. olarak adlandırılır. Denetimi eklemek için Word veya Excel 'in yerel işlevlerini kullanırsanız, oluşturduğunuz zamanda buna özel bir ad verebilirsiniz. Ayrıca, **Özellikler** penceresinde **ad** özelliğinin değerini değiştirerek denetimlerinizi yeniden adlandırabilirsiniz.

> [!NOTE]
> Konak denetimlerini adlandırmak için ayrılmış sözcükler kullanamazsınız. Örneğin, bir çalışma sayfasına bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetim ekler ve adı **sistem**olarak değiştirirseniz, projeyi oluşturduğunuzda hatalar oluşur.

### <a name="delete-host-controls"></a>Konak denetimlerini Sil
 Belge düzeyi projelerinde, Excel çalışma sayfasındaki veya Word belgesindeki denetimi seçerek ve **Delete** tuşuna basarak, tasarım zamanında konak denetimlerini silebilirsiniz. Ancak, denetimleri silmek <xref:Microsoft.Office.Tools.Excel.NamedRange> için Excel 'de **adı tanımla** iletişim kutusunu kullanmanız gerekir.

 Tasarım zamanında bir belgeye bir ana bilgisayar denetimi eklerseniz, bu denetimi kodda bir sonraki kez kullanmaya çalıştığınızda bir özel durum oluşturulur. Bir konak denetiminin yöntemi yalnızca çalışma zamanında belgeye eklenen konak denetimlerini kaldırır. `Delete` Tasarım zamanında oluşturulan bir `Delete` konak denetiminin yöntemini çağırırsanız, bir özel durum oluşturulur.

 Örneğin, bir <xref:Microsoft.Office.Tools.Excel.NamedRange> ' <xref:Microsoft.Office.Tools.Excel.NamedRange.Delete%2A> ın yöntemi, programlı olarak çalışma sayfasına <xref:Microsoft.Office.Tools.Excel.NamedRange> eklendiyse, bu, dinamik olarak konak denetimleri oluşturma olarak bilinen öğesini siler. Dinamik olarak oluşturulan konak denetimleri, `Remove` <xref:Microsoft.Office.Tools.Excel.Worksheet.Controls%2A> veya <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> özelliğinin yöntemine denetim adı geçirerek de kaldırılabilir. Daha fazla bilgi için bkz. [çalışma zamanında Office belgelerine denetim ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).

 Son kullanıcılar, çalışma zamanında belgeden bir konak denetimini siler, çözüm beklenmedik yollarla başarısız olabilir. Konak denetimlerinin silinmesini korumak için Word ve Excel 'deki belge koruma özelliklerini kullanabilirsiniz. Daha fazla bilgi için bkz. [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md).

> [!NOTE]
> Belge veya çalışma sayfasının `Shutdown` olay işleyicisi sırasında denetimleri program aracılığıyla kaldırmayın. `Shutdown` Olay gerçekleştiğinde UI öğeleri artık kullanılamaz. Uygulama kapanmadan önce denetimleri kaldırmak istiyorsanız, kodunuzu `BeforeClose` veya `BeforeSave`gibi başka bir olay işleyicisine ekleyin.

### <a name="program-against-host-control-events"></a>Konak denetim olaylarına karşı program
 Konak denetimlerinin Office nesnelerini genişletmesinin bir yolu, olaylar eklemektir. Örneğin, <xref:Microsoft.Office.Interop.Excel.Range> Excel 'deki nesne ve <xref:Microsoft.Office.Interop.Word.Bookmark> Word içindeki nesne, olayları içermez, ancak [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] programlanabilir olaylar ekleyerek bu nesneleri genişletir. Bu olaylara karşı, Visual Basic ve içindeki C#olay özelliği sayfasındaki olay açılan listesi aracılığıyla Windows Forms: denetim olaylarına aynı şekilde erişim sağlayabilirsiniz. Daha fazla bilgi için bkz [. İzlenecek yol: NamedRange denetimindeki](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)olaylara karşı program.

> [!NOTE]
> Excel 'deki <xref:Microsoft.Office.Interop.Excel._Application.EnableEvents%2A> <xref:Microsoft.Office.Interop.Excel.Application> nesnesinin özelliğini **false**olarak ayarlamanız gerekir. Bu özelliğin **false** olarak ayarlanması, Excel 'in konak denetimlerinin olayları da dahil olmak üzere tüm olayları oluşturmasını engeller.

## <a name="see-also"></a>Ayrıca bkz.
- [Konak öğelerinin ve konak denetimlerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
- [Program VSTO eklentileri](../vsto/programming-vsto-add-ins.md)
- [Program belge düzeyi özelleştirmeleri](../vsto/programming-document-level-customizations.md)
- [Genişletilmiş nesneleri kullanarak Word 'Ü otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md)
- [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirmek](../vsto/automating-excel-by-using-extended-objects.md)
- [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)
- [Office çözümlerinde verileri denetimlere bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)
