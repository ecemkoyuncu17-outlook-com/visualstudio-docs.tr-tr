---
title: IDebugAddress2::GetProcessID | Microsoft Dokümanlar
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAddress2::GetProcessID
helpviewer_keywords:
- IDebugAddress2::GetProcessID method
ms.assetid: 2c18889d-074a-4b95-87b4-bf1a067f44ed
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 94873e9a9c05a0c5e9253ce53240ab6b4ca39064
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80736581"
---
# <a name="idebugaddress2getprocessid"></a>IDebugAddress2::GetProcessID
Bu [IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md) arabirimi tarafından temsil edilen nesnenin sahibi olan işlemin kimliğini alır.

## <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetProcessID (
   DWORD* pProcID
);
```

```csharp
int GetProcessID (
   out uint pProcID
);
```

## <a name="parameters"></a>Parametreler
`pProcID`\
[çıkış] İşlem kimliği.

## <a name="return-value"></a>Dönüş Değeri
 Başarılı olursa, S_OK döndürür; aksi takdirde, bir hata kodu döndürür.

## <a name="see-also"></a>Ayrıca bkz.
- [IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md)
