---
title: THUNK_ORDINAL | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Thunk_Ordinal enumeration
ms.assetid: 026f98a9-36b8-41ef-8a72-12d7cbc2d362
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b98098c0b6e1de9c3c2ceda5c644bc2957ab22bd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62576414"
---
# <a name="thunkordinal"></a>THUNK_ORDINAL
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Dönüştürücü türlerini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
typedef enum THUNK_ORDINAL {   
   THUNK_ORDINAL_NOTYPE,  
   THUNK_ORDINAL_ADJUSTOR,  
   THUNK_ORDINAL_VCALL,  
   THUNK_ORDINAL_PCODE,  
   THUNK_ORDINAL_LOAD   
  
   // trampoline thunk ordinals - only for use in Trampoline thunk symbols  
   THUNK_ORDINAL_TRAMP_INCREMENTAL,  
   THUNK_ORDINAL_TRAMP_BRANCHISLAND,  
} THUNK_ORDINAL;  
```  
  
## <a name="elements"></a>Öğeleri  
 THUNK_ORDINAL_NOTYPE  
 Standart dönüştürücü.  
  
 THUNK_ORDINAL_ADJUSTOR  
 A `this` adjustor dönüştürücü.  
  
 THUNK_ORDINAL_VCALL  
 Sanal çağrı dönüştürücü.  
  
 THUNK_ORDINAL_PCODE  
 P-code dönüştürücü.  
  
 THUNK_ORDINAL_LOAD  
 Gecikme yükü dönüştürücü.  
  
 THUNK_ORDINAL_TRAMP_INCREMENTAL  
 Artımlı trampoline dönüştürücü (trampoline dönüştürücü çağrıları bir bellek alanından Sıçrama için kullanılır).  
  
 THUNK_ORDINAL_TRAMP_BRANCHISLAND  
 Dal noktası trampoline dönüştürücü.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sabit listesi değerleri çağrısından döndürülen [Idiasymbol::get_thunkordinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: cvconst.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri ve yapıları](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_thunkOrdinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md)
