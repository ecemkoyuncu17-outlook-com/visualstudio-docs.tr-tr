---
title: Entity Framework Araçları
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 1b06b573-84aa-4458-b3f5-e238df47bf45
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 250f1ad55f8d60396b8423098e58801d0ed81e77
ms.sourcegitcommit: 939407118f978162a590379997cb33076c57a707
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2020
ms.locfileid: "75916732"
---
# <a name="entity-framework-tools-in-visual-studio"></a>Visual Studio'da Entity Framework Araçları

Entity Framework, .NET geliştiricilerinin etki alanına özel nesneler kullanarak ilişkisel verilerle çalışmak bir nesne ilişkisel eşleme teknolojisidir. Genellikle geliştiricilerin yazmak zorunda olduğu çoğu veri erişim koduna yönelik gereksinimi ortadan kaldırır. Varlık, yeni .NET uygulamaları için teknoloji modelleme önerilen nesne ilişkisel eşleme (ORM) çerçevedir.

Entity Framework Araçları, Entity Framework (EF) uygulamaları oluşturmanıza yardımcı olacak şekilde tasarlanmıştır. Entity Framework için tam belgeler şunlardır: [genel bakış-EF 6](/ef/ef6/).

  > [!NOTE]
  > Bu sayfada açıklanan Entity Framework Tools, EF Core desteklenmeyen *. edmx* dosyalarını oluşturmak için kullanılır. Varolan bir veritabanından bir EF Core modeli oluşturmak için bkz. [ters mühendislik-EF Core](/ef/core/managing-schemas/scaffolding). EF 6 ve EF Core arasındaki farklar hakkında daha fazla bilgi için bkz. [EF 6 ve EF Core karşılaştırma](/ef/efcore-and-ef6/).

Entity Framework Araçları ile oluşturduğunuz bir *kavramsal model* mevcut bir veritabanı ve grafik görselleştirin ve kavramsal model düzenleyin. Veya bir kavramsal model ilk grafik oluşturun ve ardından modelinizin destekleyen bir veritabanı oluşturun. Her iki durumda da temel alınan veritabanı değişiklikleri ve otomatik olarak uygulamanız için nesne katmanı kodu oluşturma modeliniz otomatik olarak güncelleştirebilirsiniz. Veritabanı oluşturma ve nesne katmanı kodu oluşturma özelleştirilebilir.

Entity Framework Araçları bir parçası olarak yüklenen **veri depolama ve işleme** Visual Studio Yükleyicisi'nde iş yükü. Altında tek tek bir bileşen olarak da yükleyebilirsiniz **SDK'lar, kitaplıklar ve çerçeveler** kategorisi.

Entity Framework Araçları Visual Studio'da oluşturan özel araçlar şunlardır:

- Kullanabileceğiniz [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)]  **[!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] Tasarımcısı** (**varlık Tasarımcısı**) görsel olarak oluşturma ve varlıklar, ilişkilendirmeleri, eşlemeler ve devralma ilişkilerinin değiştirin. **Varlık Tasarımcısı** ayrıca oluşturur [!INCLUDE[TLA#tla_cshrp](../data-tools/includes/tlasharptla_cshrp_md.md)] veya [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] nesne katmanı kodu.

- Kullanabileceğiniz  **[!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] Sihirbazı** varolan bir veritabanından kavramsal model oluşturmak ve veritabanı bağlantı bilgilerini uygulamanıza ekleyin.

- Kullanabileceğiniz **Veritabanı Oluşturma Sihirbazı'nı** ilk kavramsal model oluşturun ve ardından modelini destekleyen bir veritabanı oluşturun.

- Kullanabileceğiniz **güncelleştirme modeli Sihirbazı** temel alınan veritabanına değişiklikler yapıldığında, kavramsal model, depolama model ve eşleme güncelleştirilecek.

  > [!NOTE]
  > Visual Studio 2010 ile başlayarak, Entity Framework Araçları desteği [!INCLUDE[ss2k](../data-tools/includes/ss2k_md.md)].

Araçlar oluşturma veya değiştirme bir *.edmx* dosya. Bu *.edmx* dosyası bunları arasındaki eşlemeleri kavramsal model ve depolama modeli açıklayan bilgileri içerir. Daha fazla bilgi için [EDMX](/ef/ef6/).

[Entity Framework güç araçları](https://marketplace.visualstudio.com/items?itemName=EntityFrameworkTeam.EntityFrameworkPowerToolsBeta4) varlık veri modeli kullanan uygulamalar oluşturmanıza yardımcı olur. Güç araçları bir kavramsal model oluşturmak, mevcut bir model doğrulama, kavramsal model temelinde nesne sınıfları içeren kaynak kodu dosyaları üretmek ve modeli oluşturur görünümleri içeren kaynak kodu dosyaları üretir. Ayrıntılı bilgi için bkz. [Pre-Generated eşleme görünümleri](/ef/ef6/fundamentals/performance/pre-generated-views).

## <a name="related-topics"></a>İlgili konular

| Başlık | Açıklama |
| - | - |
| [ADO.NET Entity Framework](/dotnet/framework/data/adonet/ef/index) | Nasıl kullanılacağını açıklar [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] araçları, hangi [!INCLUDE[adonet_ef](../data-tools/includes/adonet_ef_md.md)] uygulamalar oluşturmasını sağlar. |
| [Varlık Veri Modeli](/dotnet/framework/data/adonet/entity-data-model) | Üzerinde oluşturulan uygulamaları tarafından kullanılan verilerle çalışmaya yönelik bilgi ve bağlantılar sağlanmıştır [!INCLUDE[adonet_ef](../data-tools/includes/adonet_ef_md.md)]. |
| [Entity Framework (EF) belgeleri)](/ef/ef6/get-started) | Bir dizin videolar, öğreticiler ve en verimli şekilde Entity Framework yardımcı olan gelişmiş belgeler sağlar. |
| [ASP.NET 5 uygulaması için yeni veritabanı](https://docs.efproject.net/en/latest/platforms/aspnetcore/new-db.html) | Entity Framework 7 kullanarak yeni bir ASP.NET 5 uygulaması oluşturmayı açıklar. |

## <a name="see-also"></a>Ayrıca bkz.

- [.NET için Visual Studio veri araçları](../data-tools/visual-studio-data-tools-for-dotnet.md)
