---
title: N katmanlı uygulamalarda TableAdapter’lara kod ekleme
ms.date: 11/04/2016
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- TableAdapters, n-tier applications
- n-tier applications, extending TableAdapters
ms.assetid: dafac00e-df9d-4d4a-95a6-e34b4d099425
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 3ea451ac60de971677ee2f7910b28b334c67dff3
ms.sourcegitcommit: 1d4f6cc80ea343a667d16beec03220cfe1f43b8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85283105"
---
# <a name="add-code-to-tableadapters-in-n-tier-applications"></a>N katmanlı uygulamalarda TableAdapter’lara kod ekleme
TableAdapter için kısmi bir sınıf dosyası oluşturarak ve buna kod ekleyerek bir TableAdapter 'ın işlevselliğini genişletebilirsiniz ( *DataSetName. DataSet. Designer* dosyasına kod eklemek yerine). Kısmi sınıflar, belirli bir sınıfın kodunu birden çok fiziksel dosyaya bölünecek şekilde etkinleştirir. Daha fazla bilgi için bkz. [kısmi](/dotnet/visual-basic/language-reference/modifiers/partial) veya [kısmi (tür)](/dotnet/csharp/language-reference/keywords/partial-type).

Bir TableAdapter tanımlayan kod, veri kümesindeki TableAdapter 'ta her değişiklik yapıldığında oluşturulur. Bu kod ayrıca, TableAdapter yapılandırmasını değiştiren herhangi bir sihirbazın çalıştırılması sırasında değişiklik yapıldığında da oluşturulur. Bir TableAdapter 'ın yeniden oluşturulması sırasında kodunuzun silinmesini engellemek için TableAdapter 'ın parçalı sınıf dosyasına kod ekleyin.

Varsayılan olarak, veri kümesini ve TableAdapter kodunu ayırdıktan sonra sonuç, her projedeki ayrı bir sınıf dosyasıdır. Özgün projenin, TableAdapter kodunu içeren *DataSetName. Designer. vb* (veya *DataSetName.Designer.cs*) adlı bir dosyası vardır. **DataSet projesi** özelliğinde belirtilen proje, dataset kodunu Içeren *DataSetName. DataSet. Designer. vb* (veya *DataSetName.DataSet.Designer.cs*) adlı bir dosyaya sahiptir.

> [!NOTE]
> Veri kümelerini ve TableAdapters ayırabilirsiniz ( **veri kümesi proje** özelliğini ayarlayarak), projedeki mevcut kısmi veri kümesi sınıfları otomatik olarak taşınmaz. Mevcut kısmi veri kümesi sınıflarının veri kümesi projesine el ile taşınması gerekir.

> [!NOTE]
> Veri kümesi, <xref:System.Data.DataTable.ColumnChanging> doğrulama gerektiğinde oluşturma ve <xref:System.Data.DataTable.RowChanging> olay işleyicileri için işlevsellik sağlar. Daha fazla bilgi için bkz. [n katmanlı bir veri kümesine doğrulama ekleme](../data-tools/add-validation-to-an-n-tier-dataset.md).

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="to-add-user-code-to-a-tableadapter-in-an-n-tier-application"></a>N katmanlı bir uygulamadaki bir TableAdapter 'a Kullanıcı kodu eklemek için

1. *. Xsd* dosyasını içeren projeyi bulun.

2. **Veri kümesi Tasarımcısı**açmak için *. xsd* dosyasına çift tıklayın.

3. Kod eklemek istediğiniz TableAdapter öğesine sağ tıklayın ve ardından **kodu görüntüle**' yi seçin.

     Kod düzenleyicisinde kısmi bir sınıf oluşturulur ve açılır.

4. Kısmi sınıf bildiriminin içine kod ekleyin.

5. Aşağıdaki örnek, içindeki içine kodunun nereye ekleneceğini göstermektedir `CustomersTableAdapter` `NorthwindDataSet` :

    ```vb
    Partial Public Class CustomersTableAdapter
        ' Add code here to add functionality
        ' to the CustomersTableAdapter.
    End Class
    ```

    ```csharp
    public partial class CustomersTableAdapter
    {
        // Add code here to add functionality
        // to the CustomersTableAdapter.
    }
    ```

## <a name="see-also"></a>Ayrıca bkz.

- [N katmanlı veri uygulamalarına genel bakış](../data-tools/n-tier-data-applications-overview.md)
- [N katmanlı uygulamalardaki veri kümelerine kod ekleme](../data-tools/add-code-to-datasets-in-n-tier-applications.md)
- [TableAdapter’lar oluşturma ve yapılandırma](create-and-configure-tableadapters.md)
- [Hiyerarşik Güncelleştirmeye Genel Bakış](hierarchical-update.md)
