---
title: BP_PASSCOUNT_STYLE | Microsoft Dokümanlar
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_PASSCOUNT_STYLE
helpviewer_keywords:
- BP_PASSCOUNT_STYLE structure
ms.assetid: 0a647047-e2d5-4724-a0b8-68108425ecad
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1633c5e9aa6ff251fedce83a0243664cd9e0e0a7
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80737921"
---
# <a name="bp_passcount_style"></a>BP_PASSCOUNT_STYLE
Kesme noktasının yanmasını neden olan kesme noktası geçiş sayısıyla ilişkili durumu belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
enum enum_BP_PASSCOUNT_STYLE {
    BP_PASSCOUNT_NONE             = 0x0000,
    BP_PASSCOUNT_EQUAL            = 0x0001,
    BP_PASSCOUNT_EQUAL_OR_GREATER = 0x0002,
    BP_PASSCOUNT_MOD              = 0x0003
};
typedef DWORD BP_PASSCOUNT_STYLE;
```

```csharp
public enum enum_BP_PASSCOUNT_STYLE {
    BP_PASSCOUNT_NONE             = 0x0000,
    BP_PASSCOUNT_EQUAL            = 0x0001,
    BP_PASSCOUNT_EQUAL_OR_GREATER = 0x0002,
    BP_PASSCOUNT_MOD              = 0x0003
};
```

## <a name="fields"></a>Alanlar
`BP_PASSCOUNT_NONE`\
Kesme noktası geçiş sayısı stili ni belirtir.

`BP_PASSCOUNT_EQUAL`\
Kesme noktası geçiş sayısı stilini eşit olarak ayarlar. Kesme noktası, kesme noktasının isabet sayısı geçiş sayısına eşit olduğunda yangınlar.

`BP_PASSCOUNT_EQUAL_OR_GREATER`\
Kesme noktası geçiş sayısı stilini eşit veya daha büyük olarak ayarlar. Kesme noktası, kesme noktasının isabet etme sayısı geçiş sayısına eşit veya daha büyük olduğunda yangınlar.

`BP_PASSCOUNT_MOD`\
Modüler geçiş sayısını belirtir. Örneğin, geçiş sayısı türdeyse `BP_PASSCOUNT_MOD` ve geçiş sayısı 4 ise, isabet sayısı 4'ün bir katı olduğunda kesme noktası yangınları.

## <a name="remarks"></a>Açıklamalar
BP_REQUEST_INFO ve `stylePassCount` [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) yapıların bir üyesi olan [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md) [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) yapının üyesi için kullanılır.

## <a name="requirements"></a>Gereksinimler
Üstbilgi: msdbg.h

Ad alanı: Microsoft.VisualStudio.Debugger.Interop

Montaj: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Ayrıca bkz.
- [Numaralandırma](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)
- [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)
- [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)
