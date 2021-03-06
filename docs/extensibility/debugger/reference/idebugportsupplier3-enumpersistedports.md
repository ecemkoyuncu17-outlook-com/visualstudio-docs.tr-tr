---
title: IDebugPortSupplier3::EnumPersistedPorts | Microsoft Dokümanlar
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortSupplier3::EnumPersistedPorts
helpviewer_keywords:
- IDebugPortSupplier3::EnumPersistedPorts
ms.assetid: 1c3dead3-5d6c-4067-8418-4015f0b0dd07
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 92b31a6b6898b0031e4a01d5a6433d0ce77e64f4
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80724445"
---
# <a name="idebugportsupplier3enumpersistedports"></a>IDebugPortSupplier3::EnumPersistedPorts
Bu yöntem, kalıcı bağlantı noktaları listesinin numaralandırmasına izin veren bir nesne alır.

## <a name="syntax"></a>Sözdizimi

```cpp
HRESULT EnumPersistedPorts(
   BSTR_ARRAY         PortNames,
   IEnumDebugPorts2** ppEnum
);
```

```csharp
int EnumPersistedPorts(
   BSTR_ARRAY           PortNames,
   out IEnumDebugPorts2 ppEnum
);
```

## <a name="parameters"></a>Parametreler
`PortNames`\
[içinde] Kalıcı bağlantı noktaları arasında bulabileceğiniz ve döndürülecek bağlantı noktası adlarının listesini içeren [BSTR_ARRAY](../../../extensibility/debugger/reference/bstr-array.md) bir yapı. Yalnızca bu adlara sahip kalıcı bağlantı noktaları döndürülür.

`ppEnum`\
[çıkış] [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md) arabirimini uygulayan bir nesne.

## <a name="return-value"></a>Dönüş Değeri
 Başarılı olursa, `S_OK`döner; aksi takdirde, bir hata kodu döndürür.

## <a name="remarks"></a>Açıklamalar
 Kalıcı bağlantı noktaları, bir bağlantı noktası tedarikçisi anında yüklendiğinde ve bağlantı noktası tedarikçisi yok edildiğinde kaydedilir.

## <a name="see-also"></a>Ayrıca bkz.
- [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)
- [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)
- [BSTR_ARRAY](../../../extensibility/debugger/reference/bstr-array.md)
