---
title: İç içe projeler için addItem iletişim kutusunu filtreleme | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- filtering, nested projects
- nested projects, AddItem dialog box filtering
ms.assetid: 5b3e352e-7f18-4f66-be16-b0ad55637ce5
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7bb98eac2bc481aa5e3652144dfbcadf70430d04
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62538102"
---
# <a name="filtering-the-additem-dialog-box-for-nested-projects"></a>İç içe Projeler için AddItem İletişim Kutusunu Filtreleme
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Görüntülerken bir **addItem** ana proje iç içe geçmiş proje için iletişim kutusu, hangi öğeleri iletişim kutusunda görüntülenen denetleyebilirsiniz.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2> Arabirimi sayesinde filtre olacak düğümleri bir **addItem** iletişim kutusu. Alt projenin görüntülendiğinde **addItem** iletişim kutusu, üst uygulayabilirsiniz `IVsFilterAddProjectItemDlg` çocuğun projesinde gösterilecek arabirimi ve filtre öğeleri.  
  
 Projeleri, belirli bir üst projeleri altında işlevi tarafından gruplandırıldığında, uygulayabileceğiniz `IVsFilterAddProjectItemDlg` kullanıcı seçtiğinde **proje Öğe Ekle** iç içe geçmiş bir projedeki kısayol menüsünde. Uygulama `IvsFilterAddProjectItemDlg displays` yalnızca proje öğelerini ya da bu gruba belirli dosyaları. Aynı dizinde depolanan bile diğer gruplar için proje öğeleri iletişim kutusu dışı filtrelenir.  
  
 Kullanıcı açtığında **addItem** alt, üst projenin uygulaması için iletişim kutusu `IVsFilterAddProjectItemDlg` arabirimi çağrılır.  
  
 `IVsFilterAddProjectItemDlg` Arabirimi, kategoriye göre filtreleme de uygulayabilirsiniz. Daha fazla bilgi için [ekleme yeni öğe iletişim kutularına öğe eklemeyi](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md) ve [kaydetme proje ve öğe şablonları](../../extensibility/internals/registering-project-and-item-templates.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>   
 [Öğeler ekleme yeni öğe Ekle iletişim kutuları](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [Proje ve öğe şablonlarını kaydetme](../../extensibility/internals/registering-project-and-item-templates.md)   
 [Projeleri İç İçe Geçirme](../../extensibility/internals/nesting-projects.md)
