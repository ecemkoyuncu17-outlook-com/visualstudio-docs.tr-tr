---
title: IEnumDebugPortSuppliers2::Next | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IEnumDebugPortSuppliers2::Next
helpviewer_keywords:
- IEnumDebugPortSuppliers2::Next
ms.assetid: e2a2d226-e70b-42c2-bf00-a936517940c8
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0a2e887c6e00587c4101c73c9cc6b5bdd0a47789
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68164717"
---
# <a name="ienumdebugportsuppliers2next"></a>IEnumDebugPortSuppliers2::Next
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Sabit listesinden alınmış sonraki öğe kümesini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT Next(  
   ULONG                 celt,  
   IDebugPortSupplier2** rgelt,  
   ULONG*                pceltFetched  
);  
```  
  
```csharp  
int Next(  
   uint                  celt,  
   IDebugPortSupplier2[] rgelt,  
   ref uint              pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `celt`  
 [in] Alınacak öğelerin sayısı. Ayrıca en büyük boyutunu belirtir `rgelt` dizisi.  
  
 `rgelt`  
 [out içinde] Dizi [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md) doldurulacak öğeleri.  
  
 `pceltFetched`  
 [out] Gerçekte döndürülen öğe sayısını döndürür `rgelt`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`. Döndürür `S_FALSE` istenen öğelerin sayısından daha az döndürülebilen; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)
