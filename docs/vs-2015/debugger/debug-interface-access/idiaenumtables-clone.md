---
title: Idiaenumtables::Clone | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumTables::Clone method
ms.assetid: beb21109-b12c-44d8-8c1f-a332216b3713
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: feb4fdbdfe734263fee97fd0e71dfe0c132f26d6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68194832"
---
# <a name="idiaenumtablesclone"></a>IDiaEnumTables::Clone
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Geçerli Numaralandırıcı aynı numaralandırma duruma içeren bir numaralandırıcı oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT Clone (   
   IDiaEnumTables** ppenum  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppenum`  
 [out] Döndürür bir [Idiaenumtables](../../debugger/debug-interface-access/idiaenumtables.md) Numaralandırıcı bir kopyasını içeren nesne. Tabloları çoğaltılmadığından, numaralandırıcı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)
