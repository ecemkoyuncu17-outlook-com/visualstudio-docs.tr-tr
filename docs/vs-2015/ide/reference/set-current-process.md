---
title: Geçerli Işlemi ayarla | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Debug.SetCurrentProcess command
- Set Current Process command
ms.assetid: 1e016ebd-aadd-411f-a606-03bf69d3f8aa
caps.latest.revision: 13
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: c362d3f5dda5015e91ac88dd8f0abd60a185ba72
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72665475"
---
# <a name="set-current-process"></a>Geçerli Süreci Ayarla
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Belirtilen işlemi hata ayıklayıcıda etkin işlem olarak ayarlar.

## <a name="syntax"></a>Sözdizimi

```
Debug.SetCurrentProcess index
```

## <a name="arguments"></a>Arguments
 `index` gerekiyor. İşlemin dizini.

## <a name="remarks"></a>Açıklamalar
 Hata ayıklarken birden çok işleme iliştirebilirsiniz, ancak belirli bir zamanda Dubber içinde yalnızca bir işlem etkin olur. Etkin işlemi ayarlamak için `SetCurrentProcess` komutunu kullanabilirsiniz.

## <a name="example"></a>Örnek

```
>Debug.SetCurrentProcess 1
```

## <a name="see-also"></a>Ayrıca Bkz.
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md) [komut penceresi](../../ide/reference/command-window.md) [Visual Studio komut diğer adları](../../ide/reference/visual-studio-command-aliases.md)
