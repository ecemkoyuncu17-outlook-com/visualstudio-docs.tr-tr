---
title: ButtonText öğesi | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- ButtonText element (VSCT XML schema)
- VSCT XML schema elements, ButtonText
ms.assetid: 56aba884-0356-4894-ae4e-32d3938f6865
caps.latest.revision: 7
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: ef22471d20df5582fec96c8a685029a1d475a4a4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68184575"
---
# <a name="buttontext-element"></a>ButtonText Öğesi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu alan çeşitli menülerde görüntülenen metin belirtmenize olanak sağlar. Varsayılan olarak, `ButtonText` öğesi menüsü denetleyicileri görünür. `ButtonText` Öğesi diğer metin alanları boş ise varsayılan ayrıca olur. `ButtonText` Bile diğer metin alanları öğesi boş olamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<ButtonText>My Command</ButtonText>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Strings Öğesi](../extensibility/strings-element.md)|Metin öğeleri gibi gruplar `ButtonText` ve `CommandName`.|  
  
## <a name="text-value"></a>Metin Değeri  
 Metin değeri `ButtonText` öğesi menü öğeleri, combos ve görünen metin sahip diğer kullanıcı arabirimi (UI) öğeleri için görüntülenen metni sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
