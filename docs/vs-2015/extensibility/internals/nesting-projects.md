---
title: Projeleri iç içe geçirme | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project nesting
- nested projects
- projects [Visual Studio SDK], child projects
- projects [Visual Studio SDK], nesting
ms.assetid: 12cce037-9840-4761-845e-5abd5fb317b0
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0e3a0fae42dc7bf1497e3d0d4a9d23f9cab50675
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2019
ms.locfileid: "68180428"
---
# <a name="nesting-projects"></a>Projeleri İç İçe Geçirme
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

VS paketinizi kullanan kurumsal uygulama geliştiricileri, *proje iç içe geçme*kullanarak [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] benzer proje türlerini kolayca gruplandırabilirsiniz. Örneğin, kurumsal şablon proje, projeleri kategoriler halinde gruplamak için iç içe geçmiş projeleri kullanır. İş façlade projeleri, Web UI projeleri vb. bir kategoride birlikte gruplandırılır.  
  
 Bu senaryoda, geliştirici program aracılığıyla sınırları sağlayabilse de, geliştiricinin her bir üst projenin altına iç içe geçirebilmesine rağmen proje sayısı için bir sınır yoktur. Bu gruplandırma türü de özyinelemeli hale getirilebilir. Bu durumda, bir alt proje ile aynı türdeki projelerin alt öğesi olmak üzere alt öğesi olmak üzere alt öğe altında iç içe yerleştirilenebilir.  
  
 Proje iç içe geçme [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]iç parçası değil. İç içe geçme ve alt proje iç içe geçme özelliğini etkinleştirmek için kodu yazmanız gerekir. Üst proje, özel bir VSPackage veya proje türü oluşturup, proje iç içe geçirilmesi için gerekli kodu içeren kendi GUID 'sine sahip oluşturulup kaydedilir.  
  
 Yuvalanmış projelerin bir örneğini C# örnek. Iç içe proje örneğinde bulabilirsiniz.  
  
## <a name="nested-projects-example"></a>İç içe projeler örneği  
 ![Iç Içe projeler çözümü](../../extensibility/internals/media/vsnestedprojects.gif "vsnestedprojects")  
İç içe projeler örneği  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Iç Içe Projeler uygulama](../../extensibility/internals/how-to-implement-nested-projects.md)   
 [Iç Içe projeleri kaldırma ve yeniden yükleme](../../extensibility/internals/considerations-for-unloading-and-reloading-nested-projects.md) Ile ilgili hususlar   
 [Iç Içe projeler Için sihirbaz desteği](../../extensibility/internals/wizard-support-for-nested-projects.md)   
 [Proje ve öğe şablonlarını kaydetme](../../extensibility/internals/registering-project-and-item-templates.md)   
 [Iç Içe projeler Için komut Işlemeyi uygulama](../../extensibility/internals/implementing-command-handling-for-nested-projects.md)   
 [Iç Içe projeler Için AddItem Iletişim kutusunu filtreleme](../../extensibility/internals/filtering-the-additem-dialog-box-for-nested-projects.md)   
 [Denetim listesi: yeni proje türleri oluşturma](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [Bağlam parametreleri](../../extensibility/internals/context-parameters.md)   
 [Sihirbaz (.Vsz) Dosyası](../../extensibility/internals/wizard-dot-vsz-file.md)
