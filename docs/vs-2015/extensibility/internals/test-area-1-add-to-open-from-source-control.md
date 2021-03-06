---
title: 'Test Alanı 1: İçin açık kaynak denetiminden Ekle | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], adding and opening solutions
- source control plug-ins, adding and opening solutions
ms.assetid: 5b3b5b08-5e9b-41be-ac72-c63957faed22
caps.latest.revision: 21
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e7b65eae0dcd71c2ad1bb3d72bf08ea90e69036a
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63441254"
---
# <a name="test-area-1-add-toopen-from-source-control"></a>Test Alanı 1: / Açık kaynak denetiminden Ekle
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu kaynak denetimi eklentisi test çözümlerin veya projelerin kaynak denetimi altındaki yerleştirmek ve onları kaynak denetiminden alma alan kapsar.  
  
## <a name="command-menu-access"></a>Komut menü erişimi  
 Aşağıdaki [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] tümleşik geliştirme ortamı menüsü yolları test durumlarında kullanılır:  
  
- İçin [!INCLUDE[vsvss](../../includes/vsvss-md.md)], kaynak denetiminden Aç: **Dosya**, **açık**, **proje**/**çözüm**; arama içinde [!INCLUDE[vsvss](../../includes/vsvss-md.md)] konumu.  
  
- Diğer kaynak denetimi eklentileri için kaynak denetiminden Aç: **Dosya**, **kaynak denetimi**, **kaynak denetiminden Aç**.  
  
- Kaynak denetimine ekleyin: **Dosya**, **kaynak denetimi**, **çözüm kaynak denetimi dosyasına ekleme**, **kaynak denetimi**, **Seçilen projeler kaynak denetimineEkle**.  
  
- Kısayol menüsünü (Proje/çözüm) **kaynak denetimine Çözüm Ekle**.  
  
- Kaynak denetiminden ekleyin: **Dosya**, **kaynak denetimi**, **kaynak denetiminden Proje Ekle**.  
  
- İçin [!INCLUDE[vsvss](../../includes/vsvss-md.md)], ekleme kaynak denetimi ayrıca kullanılabilir **dosya**, **Ekle**, **mevcut proje**; arama içinde [!INCLUDE[vsvss](../../includes/vsvss-md.md)] konumu.  
  
    > [!NOTE]
    > Bu sınamada bir yolunu yerel bir dosyaya veya bir yerel IIS (web sunucusu) kullanılabilir.  
  
## <a name="expected-behavior"></a>Beklenen davranış  
  
- Her desteklenen proje türü için bir kullanıcı, "Ekle" ve "kaynak denetimi açık" olmalıdır.  
  
- Karşılık gelen kaynak denetimi için bir proje eklendiğinde \< *ProjectName*> .vspscc dosyalarını _ıgnorablefilesınprojectfolder (Proje ipucu dosyası) oluşturulur. Bu dışlama dosya listesi ve bağlantı bilgilerini içerir. Projeye özel bilgiler içerdiği için bu dosyayı silmeyin.  
  
- Kaynak denetimi için karşılık gelen bir çözüm eklendiğinde \< *SolutionName*> .vssscc (üçlü S) dosyası oluşturulur. Metin dosyası bir proje ipucu dosyasına benzer dışlama dosya listesi ve bağlantı bilgilerini içerir. Bu dosya geçicidir ve yalnızca kaynak denetim veritabanında bulunmuyor.  
  
- Kaynak denetiminden bir çözüm açıldığında bir \< *SolutionName*> yalnızca kaynak denetim veritabanında var olan .vsscc (çift S) dosyası yerel olarak geçici bir dosya olarak oluşturulur. Bu dosya çözüm bağlantı klasörden çözüm dosyasının yolunu içerir. Bu dosya geçicidir ve "Açık kaynak denetimi" işlemi tamamlandığında yerel kopya silinir.  
  
- Kaynak denetimi için bir proje eklendikten sonra (kullanıma, alma vb.) üzerindeki herhangi bir kaynak denetimi eylemlerini gerçekleştirebilirsiniz.  
  
## <a name="test-cases"></a>Test çalışmaları  
 Belirli test çalışmaları Ekle şunlardır / açık kaynak denetimine test alanından.  
  
### <a name="case-1a-add-solution-to-source-control"></a>Büyük/küçük harf 1a: Kaynak Denetimine Çözüm Ekle  
 Bu test çalışması, çözümleri kaynak denetimine eklemeye ilişkin odaklanır.  
  
|Eylem|Test adımları|Beklenen sonuçları doğrulamak için|  
|------------|----------------|--------------------------------|  
|İçeren bir istemci projesi kaynak denetimine Çözüm Ekle|1.  Bir istemci projesi oluşturun.<br />2.  Kaynak Denetimine Çözüm Ekle (**dosya**, **kaynak denetimi**, **kaynak denetimine Çözüm Ekle**).|Çözüm/proje kaynak denetimi eklendi.|  
|Bir dosya sisteminde veya kaynak denetimine yerel IIS Web projesini içeren çözüm ekleyin|1.  Bir dosya sistemi veya yerel IIS Web projesi oluşturun (projenin konumu; göstermek için Gözat düğmesini kullanın. ne tür bir Web projesi oluşturulması yolu belirler).<br />2.  Kaynak Denetimine Çözüm Ekle (**dosya**, **kaynak denetimi**, **kaynak denetimine Çözüm Ekle**).|Çözüm/proje kaynak denetimi eklendi.|  
|İçeren bir uzak Site Web projesi kaynak denetimine Çözüm Ekle|1.  Uzak Site Web projesi oluşturun.<br />2.  Kaynak Denetimine Çözüm Ekle (**dosya**, **kaynak denetimi**, **kaynak denetimine Çözüm Ekle**).<br />3.  Tıklayın **Tamam** FrontPage erişim uyarı iletişim kutusunda.|Çözüm kaynak denetimi eklendi.<br /><br /> Uzak Site proje kaynak denetimi altında değil. (Uzak Site projeleri kendi IIS sunucudan denetlenmesi gerekir.)|  
|Bir çoklu proje çözümü kullanarak kaynak denetimine Ekle **seçili projeleri kaynak denetimine Ekle**.|1.  Bir çoklu proje çözümü oluşturun.<br />2.  Yalnızca çözüm kaynak denetimine seçim olarak ekleyin (**dosya**, **kaynak denetimi**, **seçili projeleri kaynak denetimine Ekle**). Bu adım başarılı olursa, sonraki adıma geçin.<br />3.  Projeyi kaynak denetimine seçim olarak Ekle (**dosya**, **kaynak denetimi**, **seçili projeleri kaynak denetimine Ekle**).<br />4.  Tıklayın **Evet** aynı konuma projeye eklenecek.<br />5.  Tıklayın **kullanıma** içinde **Check Out For Edit** iletişim kutusu.|`Result from Step 2:`<br /><br /> İşaretli bir proje ve proje içindeki tüm dosyalar kaynak denetimi göstergesi sahip ve bir araç ipucu "Değil. kaynak denetimi altında" görüntüler.<br /><br /> `Result from Step 5:`<br /><br /> Proje ve çözüm dosyası kaynak denetiminde aynı klasörde olan.|  
|Bir çözüm kaynak denetimine eklemeyi iptal et|1.  Bir çoklu proje çözümü oluşturun.<br />2.  Proje ve çözüm kaynak denetimine ekleme denemesi. Bu adım başarılı olursa, sonraki adıma geçin.<br />3.  Kaynak denetim sistemi olduktan sonra iptal edin.|`Result from Step 2:`<br /><br /> Yalnızca bir kez Ayarla proje konumu kaynak denetim iletişim kutusu görünür.<br /><br /> `Result from Step 3:`<br /><br /> Proje iptal edilmiş eklemek, proje/çözüm kaynak denetimi altında değil ve tüm kaynak denetim menülerine hala kullanılabilir ekleme.|  
  
### <a name="case-1b-open-solution-from-source-control"></a>Büyük/küçük harf 1b. Açık çözüm kaynak denetimi  
 Bu test çalışması, çözümleri kaynak denetiminden açma üzerinde odaklanır.  
  
|Eylem|Test adımları|Beklenen sonuçları doğrulamak için|  
|------------|----------------|--------------------------------|  
|Kaynak denetiminden bir istemci projesi içeren bir çözüm açın|1.  Bir istemci projesi oluşturun.<br />2.  Çözüm kaynak denetimine ekleyin.<br />3.  Çözümü kapatın.<br />4.  Çözümü kaynak denetiminden yeni bir konuma açın.|Kaynak denetiminden açtığınız çözüm/proje.|  
|Bir yerel veya kaynak denetiminden IIS Web projesi içeren bir çözüm açın|1.  Yerel veya IIS Web projesi oluşturun.<br />2.  Çözüm kaynak denetimine ekleyin.<br />3.  Çözümü kapatın.<br />4.  Çözümü kaynak denetiminden yeni bir konuma açın.|Kaynak denetiminden açtığınız çözüm/proje.|  
|Kaynak denetiminden bir uzak Site Web projesi içeren bir çözüm açın|1.  Uzak Site Web projesi oluşturun.<br />2.  Çözüm kaynak denetimine ekleyin. Bu adım başarılı olursa, sonraki adıma geçin.<br />3.  Çözümü kapatın.<br />4.  Çözümü kaynak denetiminden yeni bir konuma açın.|`Result from Step 2:`<br /><br /> Uzak Site Web kaynak denetimi altında değil.<br /><br /> `Result from Step 4:`<br /><br /> Kaynak denetiminden açtığınız çözüm.<br /><br /> Uzak Site proje yüklendi, ancak kaynak denetimi altında değil.|  
  
### <a name="case-1c-add-solution-from-source-control"></a>Durum 1c: Kaynak denetiminden çözüm ekleyin  
 Bu test çalışması, çözümleri kaynak denetiminden ekleme üzerinde odaklanır.  
  
|Eylem|Test adımları|Beklenen sonuçları doğrulamak için|  
|------------|----------------|--------------------------------|  
|Boş bir çözüme ekleyin; bir çoklu proje çözümü|1.  Bir çoklu proje çözümü oluşturun.<br />2.  Çözüm kaynak denetimine ekleyin.<br />3.  Çözümü kapatın.<br />4.  İkinci bir boş çözüm oluşturun.<br />5.  Daha önce denetimli çözümü kaynak denetiminden Ekle (**dosya**, **kaynak denetimi**, **kaynak denetiminden Proje Ekle**).|Eklenen proje görünür **Çözüm Gezgini** ve iade edildi.|  
|Çözüme tek proje ile ekleme — tek bir proje|1.  Bir çözümü ile tek bir proje oluşturun.<br />2.  Çözüm kaynak denetimine ekleyin.<br />3.  Çözümü kapatın.<br />4.  İkinci bir boş çözüm oluşturun.<br />5.  Daha önce denetimli çözümü kaynak denetiminden Ekle (**dosya**, **kaynak denetimi**, **kaynak denetiminden Proje Ekle**).|Eklenen proje görünür **Çözüm Gezgini** ve iade edildi.|  
|Çözüme eklemek — çözüm kaynak denetimi seçerek eklendi|1.  Bir çözüm kullanarak bir proje oluşturun.<br />2.  Yalnızca çözüm kaynak denetimi için seçim olarak ekleyin. Bu adım başarılı olursa, sonraki adıma geçin.<br />3.  Çözümü kapatın.<br />4.  Yeni bir çözüm oluşturun.<br />5.  Daha önce denetimli çözümü kaynak denetiminden Ekle (**dosya**, **kaynak denetimi**, **kaynak denetiminden Proje Ekle**).|`Result from Step 2:`<br /><br /> Proje kaynak denetimi altında değil.<br /><br /> `Result from Step 5:`<br /><br /> İlk çözümü, çözüm öğeleri olsaydı değil görünmesi için kaynak denetiminden eklenemez.<br /><br /> İlk çözümden proje kullanılamaz olarak görünür.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentileri için Test Kılavuzu](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)
