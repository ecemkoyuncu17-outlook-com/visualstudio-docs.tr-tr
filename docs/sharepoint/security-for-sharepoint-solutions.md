---
title: SharePoint çözümleri için güvenlik | Microsoft Docs
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- security [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, security
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 6dc1449a40528670274ea5b275cca3f0a8d2f277
ms.sourcegitcommit: 3a19319e2599bd193fb2ca32020ca53942974bfd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "73983784"
---
# <a name="security-for-sharepoint-solutions"></a>SharePoint çözümleri için güvenlik
  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], SharePoint uygulamalarının güvenliğinin artırılmasına yardımcı olmak için aşağıdaki özellikleri içerir.

## <a name="safe-control-entries"></a>Güvenli denetim girdileri
 [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] ' de oluşturulan her SharePoint proje öğesinde, güvenli bir denetim koleksiyonu temsil eden **güvenli bir denetim girişleri** özelliği bulunur. **Güvenli** alt özelliği, güvenli hale getirmek istediğiniz denetimleri belirtmenize olanak sağlar. Daha fazla bilgi için bkz. [Proje öğelerinde paket ve dağıtım bilgilerini sağlama](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md) ve [Güvenli Web bölümleri belirtme](/previous-versions/office/developer/sharepoint2003/dd583154(v=office.11)#specifying-safe-web-parts).

## <a name="allowpartiallytrustedcallers-attribute"></a>Allowpartiallytrustedçağıranlar özniteliği
 Varsayılan olarak, yalnızca çalışma zamanı kodu erişim güvenliği (CAS) sistemi tarafından tam olarak güvenilen uygulamalar paylaşılan bir yönetilen kod derlemesine erişebilir. Tam güvenilir bir derlemeyi Allowpartiallytrustedçağıranlar özniteliğiyle işaretlemek, kısmen güvenilen derlemelerin buna erişmesini sağlar.

 Allowpartiallytrustedçağıranlar özniteliği, sistem genel derleme önbelleğine ([!INCLUDE[TLA2#tla_gac](../sharepoint/includes/tla2sharptla-gac-md.md)]) dağıtılmamış herhangi bir SharePoint çözümüne eklenir. Bu, korumalı çözümleri veya SharePoint uygulama sepeti dizinine dağıtılan çözümleri içerir. Daha fazla bilgi için bkz. [Microsoft .NET Framework Için sürüm 1 güvenlik değişiklikleri](/previous-versions/msp-n-p/ff921345(v=pandp.10)) ve [SharePoint Foundation 'da Web bölümleri dağıtma](/previous-versions/office/developer/sharepoint-2010/cc768621(v=office.14)).

## <a name="safe-against-script-property"></a>Betik özelliğine karşı güvenli
 *Betiği ekleme* , olası kötü amaçlı kodun denetimlere veya Web sayfalarına eklenmesidir. SharePoint 2010 sitelerini betik eklenmesine karşı korumaya yardımcı olmak için, katkıda bulunanlar, varsayılan olarak Web bölümlerini veya özelliklerini görüntüleyemez veya düzenleyemez. Bu davranış, SafeAgainstScript adlı bir SafeControl özniteliğiyle denetlenir. [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)]içinde, bu özniteliği bir proje öğesinin **Güvenli denetim girdileri** alt özelliğine **karşı güvenli**olarak ayarlayın. Daha fazla bilgi için bkz. [Proje öğelerinde paket ve dağıtım bilgilerini sağlama](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md) ve [nasıl yapılır: denetimleri güvenli denetim olarak işaretleme](../sharepoint/how-to-mark-controls-as-safe-controls.md).

## <a name="vista-and-windows-7-user-account-control"></a>Vista ve Windows 7 Kullanıcı hesabı denetimi
 [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] ve [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] Kullanıcı hesabı denetimi (UAC) olarak bilinen bir güvenlik özelliği ekleyin. [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] ve [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] sistemlerinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint çözümleri geliştirmek için UAC, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] bir sistem yöneticisi olarak çalıştırmanızı gerektirir. **Başlat** menüsünden, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]için kısayol menüsünü açın ve ardından **yönetici olarak çalıştır**' ı seçin.

 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] kısayolunu her zaman yönetici olarak çalışacak şekilde yapılandırmak için, kısayol menüsünü açın, **Özellikler**' i seçin, **Özellikler** iletişim kutusunda **Gelişmiş** düğmesini seçin ve ardından **yönetici olarak çalıştır** onay kutusunu seçin.

 Daha fazla bilgi için bkz. [Windows Vista 'Da Kullanıcı hesabı denetimini anlama ve yapılandırma](/previous-versions/windows/it-pro/windows-vista/cc709628(v=ws.10)). ve [Windows 7 Kullanıcı hesabı denetimi](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731416(v=ws.10)).

## <a name="sharepoint-permissions-considerations"></a>SharePoint izinleri konuları
 SharePoint çözümleri geliştirmek için, SharePoint çözümlerini çalıştırmak ve hatalarını ayıklamak için yeterli izinlere sahip olmanız gerekir. Bir SharePoint çözümünü test etmeden önce, gerekli izinlere sahip olduğunuzdan emin olmak için aşağıdaki adımları uygulayın:

1. Kullanıcı hesabınızı sisteme yönetici olarak ekleyin.

2. Kullanıcı hesabınızı SharePoint sunucusu için bir grup yöneticisi olarak ekleyin.

    1. SharePoint 2010 Merkezi Yönetimi 'nde **Grup yöneticileri grubunu yönet** bağlantısını seçin.

    2. **Grup yöneticileri** sayfasında, **Yeni** menü seçeneğini belirleyin.

3. Kullanıcı hesabınızı WSS_ADMIN_WPG grubuna ekleyin.

## <a name="additional-security-resources"></a>Ek güvenlik kaynakları
 Güvenlik sorunları hakkında daha fazla bilgi için aşağıdaki konulara bakın.

### <a name="visual-studio-security"></a>Visual Studio güvenliği

- [Güvenlik ve Kullanıcı Izinleri](/previous-versions/visualstudio/visual-studio-2010/ms165099(v=vs.100))

- [Yerel ve .NET Framework kodundaki güvenlik](/previous-versions/visualstudio/visual-studio-2010/1787tk12(v=vs.100))

- [.NET Framework güvenliği](/previous-versions/dotnet/netframework-4.0/fkytk30f(v=vs.100))

### <a name="sharepoint-security"></a>SharePoint güvenliği

- [SharePoint Foundation yönetimi ve güvenliği](/previous-versions/office/developer/sharepoint-2010/ee537811(v=office.14))

- [SharePoint güvenliği Kaynak Merkezi](/sharepoint/dev/)

- [SharePoint Foundation 'da Web Bölümleri güvenliğini sağlama](/previous-versions/office/developer/sharepoint-2010/cc768613(v=office.14))

- [Web uygulaması güvenliğini artırma: tehditler ve onay ölçüleri](/previous-versions/msp-n-p/ff649874(v=pandp.10))

### <a name="general-security"></a>Genel güvenlik

- [MSDN güvenlik geliştirme yaşam döngüsü](https://www.microsoft.com/msrc?rtc=1)

- [Güvenli ASP.NET uygulamaları oluşturma: kimlik doğrulama, yetkilendirme ve güvenli Iletişim](/previous-versions/msp-n-p/ff649100(v=pandp.10))

## <a name="see-also"></a>Ayrıca bkz.

- [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md)