---
title: Karışık modda hata ayıklama yalnızca Microsoft .NET Framework 2,0 veya 3,0 ' i kullanırken desteklenir | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.error.interop_unsupported_to_old
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: f607af6f-57fe-472a-a32e-b6202067aa96
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: b20ef6b81e4d7162fd230d9d0c3437fe1b5232c1
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72730925"
---
# <a name="mixed-mode-debugging-is-only-supported-when-using-microsoft-net-framework-20-or-30"></a>Karışık Modda Hata Ayıklama Yalnızca Microsoft .NET Framework 2.0 veya 3.0 Sürümü Kullanılırken Desteklenir
2,0 ' den önceki Microsoft .NET Framework sürümleri, 64 bit işlemlerde karışık modda hata ayıklama desteği sağlamaz. Bu, hata ayıklarken yönetilen koddan yerel koda veya yerel koddan yönetilen koda ilerlenemez.

 Bu sorunu geçici olarak çözmek için şunları yapabilirsiniz:

- Projenizi Microsoft .NET Framework 2,0 veya 3,0 ' ü kullanacak şekilde güncelleştirin.

- Yönetilen ve yerel kodunuzda ayrı hata ayıklama oturumlarında hata ayıklayın.

- Aşağıdaki yordamlarda açıklandığı gibi, karma kodunuzda 32 bitlik bir işlem olarak hata ayıklayın.

### <a name="to-change-the-operating-system-to-32-bit-visual-basic-or-c"></a>İşletim sistemini 32-bit (Visual Basic veya C#) olarak değiştirmek için

1. **Çözüm Gezgini**, projenize sağ tıklayın ve ardından kısayol menüsünde **Özellikler** ' e tıklayın.

2. Özellik sayfalarında, **Derle** veya **Hata Ayıkla** sekmesine tıklayın.

3. **Platform**' ı tıklatın ve ardından platformlar listesinden **x86** ' yı seçin.

     Visual Basic ve C# derleyiciler, varsayılan olarak HERHANGI bir CPU üzerinde çalışacak kodu üretir. 64 bitlik bir bilgisayarda bu ikili dosyalar 64 bit işlem olarak çalışır. 32 bitlik bir işlemde çalıştırmak için, **anycpu**değil, **Win32**öğesini seçmeniz gerekir.

### <a name="to-change-the-operating-system-to-32-bit-cc"></a>İşletim sistemini 32-bit (C/C++) olarak değiştirmek için

1. **Çözüm Gezgini**, projenize sağ tıklayın ve ardından kısayol menüsünde **Özellikler** ' e tıklayın.

     Özellik sayfalarında **Platform**' a tıklayın ve ardından platformlar listesinden **Win32** öğesini seçin.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Bkz. [SQL hata ayıklamayı ayarlama](/previous-versions/visualstudio/visual-studio-2010/s4sszxst(v=vs.100)).

## <a name="see-also"></a>Ayrıca bkz.
- [64 Bit Uygulamalarda Hata Ayıklama](../debugger/debug-64-bit-applications.md)