---
title: Idiasymbol::get_container | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_container method
ms.assetid: 24e832eb-80b3-484c-a41b-11477ec9de99
caps.latest.revision: 9
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b759c8fc65130c37f24e8ec03bbcebf3a52241d0
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2019
ms.locfileid: "64810675"
---
# <a name="idiasymbolgetcontainer"></a>IDiaSymbol::get_container
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu işlev, bu sembol üst/kapsayıcı temsil eden bir sembol için bir işaretçi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT get_container(  
   IDiaSymbol **pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRetVal`  
 [out] Bir işaretçi döndüren bir `IDiaSymbol` bu simgenin kapsayıcı hakkında bilgileri içeren.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür; Aksi takdirde S_FALSE veya bir hata kodu döndürür.  
  
> [!NOTE]
> S_FALSE dönüş değeri, özellik simge için kullanılabilir olmadığı anlamına gelir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Gereksinim|Açıklama|  
|-----------------|-----------------|  
|Üst bilgi:|dia2.h|  
|Sürüm:|DIA SDK v8.0|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
