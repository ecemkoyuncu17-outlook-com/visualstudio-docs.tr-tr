---
title: "İzlenecek yol: bir VSTO eklentisinde VBA 'dan kod çağırma"
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- VBA [Office development in Visual Studio], calling code in application-level add-ins
- application-level add-ins [Office development in Visual Studio], calling code from other solutions
- Video How tos, Office development in Visual Studio
- calling add-in code
- add-ins [Office development in Visual Studio], calling code from other solutions
- interoperability [Office development in Visual Studio]
- calling code from VBA
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 6fdbd2cf85086bac0aa7bb56c128a7ad6fe36f94
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650781"
---
# <a name="walkthrough-call-code-in-a-vsto-add-in-from-vba"></a>İzlenecek yol: bir VSTO eklentisinde VBA 'dan kod çağırma
  Bu izlenecek yol, VSTO Eklentilerindeki bir nesneyi Visual Basic for Applications (VBA) ve COM VSTO eklentileri dahil diğer Microsoft Office çözümlerine nasıl kullanıma sunılacağını gösterir.

 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]

 Bu izlenecek yol Excel 'i özel olarak kullanıyor olsa da, izlenecek yol tarafından gösterilen kavramlar, Visual Studio tarafından sunulan tüm VSTO eklentisi proje şablonları için geçerlidir.

 Bu izlenecek yol aşağıdaki görevleri gösterir:

- Diğer Office çözümlerine maruz olabilecek bir sınıf tanımlama.

- Sınıfı diğer Office çözümlerine sunma.

- VBA kodundan sınıfın bir yöntemini çağırma.

  [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

## <a name="prerequisites"></a>Prerequisites
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:

- [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]

- Microsoft Excel

## <a name="create-the-vsto-add-in-project"></a>VSTO eklentisi projesini oluşturma
 İlk adım Excel için bir VSTO eklentisi projesi oluşturmaktır.

### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için

1. Excel VSTO eklentisi proje şablonunu kullanarak **Excelimportdata**adlı BIR Excel VSTO eklentisi projesi oluşturun. Daha fazla bilgi için bkz. [nasıl yapılır: Visual Studio 'Da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).

     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] **ThisAddIn.cs** veya **ThisAddIn. vb** kod dosyasını açar ve **ExcelImportData** projesini **Çözüm Gezgini**ekler.

## <a name="define-a-class-that-you-can-expose-to-other-office-solutions"></a>Diğer Office çözümlerine sergilemek için kullanabileceğiniz bir sınıf tanımlayın
 Bu izlenecek yolun amacı, VBA kodundaki VSTO eklentiinizdeki `AddInUtilities` adlı bir sınıfın `ImportData` yöntemine çağrı sağlamaktır. Bu yöntem, etkin çalışma sayfasının A1 hücresine bir dize yazar.

 @No__t_0 sınıfını diğer Office çözümlerine göstermek için, sınıfı ortak ve COM 'a görünür hale getirmelisiniz. Ayrıca, sınıfında [IDispatch](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) arabirimini kullanıma sunmalısınız. Aşağıdaki yordamdaki kod, bu gereksinimleri karşılamak için bir yol gösterir. Daha fazla bilgi için bkz. [diğer Office ÇÖZÜMLERINDEKI VSTO eklentilerindeki kodu çağırma](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md).

### <a name="to-define-a-class-that-you-can-expose-to-other-office-solutions"></a>Diğer Office çözümlerine açığa çıkarmak için kullanabileceğiniz bir sınıf tanımlamak için

1. **Proje** menüsünde **Sınıf Ekle**' ye tıklayın.

2. **Yeni öğe Ekle** iletişim kutusunda, yeni sınıfın adını **AddInUtilities**olarak değiştirin ve **Ekle**' ye tıklayın.

     **AddInUtilities.cs** veya **AddInUtilities. vb** dosyası kod düzenleyicisinde açılır.

3. Aşağıdaki yönergeleri dosyanın en üstüne ekleyin.

     [!code-csharp[Trin_AddInInteropWalkthrough#2](../vsto/codesnippet/CSharp/Trin_AddInInteropWalkthrough/AddInUtilities.cs#2)]
     [!code-vb[Trin_AddInInteropWalkthrough#2](../vsto/codesnippet/VisualBasic/Trin_AddInInteropWalkthrough/AddInUtilities.vb#2)]

4. @No__t_0 sınıfını aşağıdaki kodla değiştirin.

     [!code-csharp[Trin_AddInInteropWalkthrough#3](../vsto/codesnippet/CSharp/Trin_AddInInteropWalkthrough/AddInUtilities.cs#3)]
     [!code-vb[Trin_AddInInteropWalkthrough#3](../vsto/codesnippet/VisualBasic/Trin_AddInInteropWalkthrough/AddInUtilities.vb#3)]

     Bu kod, `AddInUtilities` sınıfını COM 'a görünür hale getirir ve `ImportData` yöntemini sınıfa ekler. [IDispatch](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) arabirimini kullanıma sunmak için `AddInUtilities` sınıfı <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> özniteliğe de sahıptır ve com tarafından görülebilen bir arabirim uygular.

## <a name="expose-the-class-to-other-office-solutions"></a>Sınıfı diğer Office çözümlerine kullanıma sunma
 @No__t_0 sınıfını diğer Office çözümlerine göstermek için `ThisAddIn` sınıfındaki <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A> yöntemini geçersiz kılın. Geçersiz kılmada `AddInUtilities` sınıfının bir örneğini döndürün.

### <a name="to-expose-the-addinutilities-class-to-other-office-solutions"></a>AddInUtilities sınıfını diğer Office çözümlerine göstermek için

1. **Çözüm Gezgini**, **Excel**' i genişletin.

2. **ThisAddIn.cs** veya **ThisAddIn. vb**öğesine sağ tıklayın ve ardından **kodu görüntüle**' ye tıklayın.

3. Aşağıdaki kodu `ThisAddIn` sınıfına ekleyin.

     [!code-csharp[Trin_AddInInteropWalkthrough#1](../vsto/codesnippet/CSharp/Trin_AddInInteropWalkthrough/ThisAddIn.cs#1)]
     [!code-vb[Trin_AddInInteropWalkthrough#1](../vsto/codesnippet/VisualBasic/Trin_AddInInteropWalkthrough/ThisAddIn.vb#1)]

4. **Yapı** menüsünde **çözüm oluştur**' a tıklayın.

     Çözümün hata olmadan yapılandırıldığını doğrulayın.

## <a name="test-the-vsto-add-in"></a>VSTO eklentisini test etme
 Birçok farklı Office çözüm türünden `AddInUtilities` sınıfına çağırabilirsiniz. Bu kılavuzda, VBA kodunu bir Excel çalışma kitabında kullanacaksınız. Ayrıca kullanabileceğiniz diğer Office çözümleri türleri hakkında daha fazla bilgi için bkz. [VSTO eklentilerindeki kodu diğer Office Çözümlerinden çağırma](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md).

### <a name="to-test-your-vsto-add-in"></a>VSTO eklentisini test etmek için

1. Projenizi çalıştırmak için **F5** tuşuna basın.

2. Excel 'de, etkin çalışma kitabını Excel makro içerebilen bir çalışma kitabı (*. xlsm) olarak kaydedin. Masaüstü gibi uygun bir konuma kaydedin.

3. Şeritte **Geliştirici** sekmesine tıklayın.

    > [!NOTE]
    > **Geliştirici** sekmesi görünür değilse, önce onu göstermelisiniz. Daha fazla bilgi için bkz. [nasıl yapılır: Şeritte Geliştirici sekmesini gösterme](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).

4. **Kod** grubunda **Visual Basic**' a tıklayın.

     Visual Basic Düzenleyicisi açılır.

5. **Proje** penceresinde, **ThisWorkbook**' a çift tıklayın.

     @No__t_0 nesne için kod dosyası açılır.

6. Aşağıdaki VBA kodunu kod dosyasına ekleyin. Bu kod, önce **Excelimportdata** VSTO eklentisini temsil eden bir COMAddIn nesnesi alır. Daha sonra kod, `ImportData` yöntemini çağırmak için COMAddIn nesnesinin Object özelliğini kullanır.

    ```vb
    Sub CallVSTOMethod()
        Dim addIn As COMAddIn
        Dim automationObject As Object
        Set addIn = Application.COMAddIns("ExcelImportData")
        Set automationObject = addIn.Object
        automationObject.ImportData
    End Sub
    ```

7. **F5**tuşuna basın.

8. Çalışma kitabına yeni bir **Içeri aktarılan veri** sayfası eklendiğini doğrulayın. Ayrıca, A1 hücresindeki dizenin **Bu**dize olduğunu doğrulayın.

9. Excel 'den çıkın.

## <a name="next-steps"></a>Sonraki adımlar
 Aşağıdaki konulardan VSTO eklentileri programlama hakkında daha fazla bilgi edinebilirsiniz:

- Konak uygulamasını otomatikleştirmek ve VSTO eklenti projelerinde diğer görevleri gerçekleştirmek için `ThisAddIn` sınıfını kullanın. Daha fazla bilgi için bkz. [Program VSTO eklentileri](../vsto/programming-vsto-add-ins.md).

- VSTO eklentisi içinde özel bir görev bölmesi oluşturun. Daha fazla bilgi için bkz. [özel görev bölmeleri](../vsto/custom-task-panes.md) ve [nasıl yapılır: uygulamaya özel görev bölmesi ekleme](../vsto/how-to-add-a-custom-task-pane-to-an-application.md).

- Bir VSTO eklentisinin içindeki şeridi özelleştirin. Daha fazla bilgi için bkz. [Şerit 'e genel bakış](../vsto/ribbon-overview.md) ve [nasıl yapılır: Şeriti özelleştirmeye başlama](../vsto/how-to-get-started-customizing-the-ribbon.md).

## <a name="see-also"></a>Ayrıca bkz.
- [Program VSTO eklentileri](../vsto/programming-vsto-add-ins.md)
- [Diğer Office çözümlerindeki VSTO eklentilerindeki kodu çağırma](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md)
- [Office çözümleri geliştirme](../vsto/developing-office-solutions.md)
- [Nasıl yapılır: Visual Studio 'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)
- [VSTO Eklentileri Mimarisi](../vsto/architecture-of-vsto-add-ins.md)
- [Genişletilebilirlik arabirimlerini kullanarak Kullanıcı arabirimi özelliklerini özelleştirme](../vsto/customizing-ui-features-by-using-extensibility-interfaces.md)
