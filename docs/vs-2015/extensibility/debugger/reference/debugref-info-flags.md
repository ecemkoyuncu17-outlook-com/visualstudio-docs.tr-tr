---
title: DEBUGREF_INFO_FLAGS | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- DEBUGREF_INFO_FLAGS
helpviewer_keywords:
- DEBUGREF_INFO_FLAGS enumeration
ms.assetid: 1b043327-302a-4f6d-b51d-f94f9d7c7f9d
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 05a073b3663ff85fe3d68878999aaf1dfa9e0017
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68198853"
---
# <a name="debugrefinfoflags"></a>DEBUGREF_INFO_FLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Hangi bilgilerin hakkında bir hata ayıklama başvuru nesnesi alınacağını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
enum enum_DEBUGREF_INFO_FLAGS {   
   DEBUGREF_INFO_NAME             = 0x00000001,  
   DEBUGREF_INFO_TYPE             = 0x00000002,  
   DEBUGREF_INFO_VALUE            = 0x00000004,  
   DEBUGREF_INFO_ATTRIB           = 0x00000008,  
   DEBUGREF_INFO_REFTYPE          = 0x00000010,  
   DEBUGREF_INFO_REF              = 0x00000020,  
   DEBUGREF_INFO_VALUE_AUTOEXPAND = 0x00010000,  
   DEBUGREF_INFO_NONE             = 0x00000000,  
   DEBUGREF_INFO_ALL              = 0xffffffff  
};  
typedef DWORD DEBUGREF_INFO_FLAGS;  
```  
  
```csharp  
public enum enum_DEBUGREF_INFO_FLAGS {   
   DEBUGREF_INFO_NAME             = 0x00000001,  
   DEBUGREF_INFO_TYPE             = 0x00000002,  
   DEBUGREF_INFO_VALUE            = 0x00000004,  
   DEBUGREF_INFO_ATTRIB           = 0x00000008,  
   DEBUGREF_INFO_REFTYPE          = 0x00000010,  
   DEBUGREF_INFO_REF              = 0x00000020,  
   DEBUGREF_INFO_VALUE_AUTOEXPAND = 0x00010000,  
   DEBUGREF_INFO_NONE             = 0x00000000,  
   DEBUGREF_INFO_ALL              = 0xffffffff  
};  
```  
  
## <a name="members"></a>Üyeler  
 DEBUGREF_INFO_NAME  
 Başlat/kullanım `bstrName` yapısında alan.  
  
 DEBUGREF_INFO_TYPE  
 Başlat/kullanım `bstrType` yapısında alan.  
  
 DEBUGREF_INFO_VALUE  
 Başlat/kullanım `bstrValue` yapısında alan.  
  
 DEBUGREF_INFO_ATTRIB  
 Başlat/kullanım `dwAttrib` yapısında alan.  
  
 DEBUGREF_INFO_REFTYPE  
 Başlat/kullanım `dwRefType` yapısında alan.  
  
 DEBUGREF_INFO_REF  
 Başlat/kullanım `pReference` yapısında alan.  
  
 DEBUGREF_INFO_VALUE_AUTOEXPAND  
 Değer alanı otomatik olarak genişletilmiş değeri varsa, bu nesne türü içermelidir.  
  
 DEBUGREF_INFO_NONE  
 Bayrak belirlendiğini gösterir.  
  
 DEBUGREF_INFO_ALL  
 Maske bayrakları belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu bayraklar geçirilen [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md) ve [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md) hangi alanları göstermek için yöntemlerini [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) yapısı olan başlatılacak.  
  
 İçin kullanılan `dwFields` üyesi `DEBUG_REFERENCE_INFO` yapısı yapısı döndürüldüğünde hangi alanların kullanılan ve geçerli olduğunu belirtmek için.  
  
 Bu değerler, bit düzeyinde ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Ad alanı: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)   
 [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md)
