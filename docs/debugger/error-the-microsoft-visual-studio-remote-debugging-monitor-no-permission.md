---
title: Hata-uzak bilgisayardaki Microsoft Visual Studio Uzaktan Hata Ayıklama İzleyicisi bu bilgisayara bağlanma izni yok
titleSuffix: ''
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: error-reference
f1_keywords:
- vs.debug.error.access_denied_oncallback
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, Windows version error
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: aa9304c999abb1401af8e524551a999556826062
ms.sourcegitcommit: 66f31cc4ce1236e638ab58d2f70d3646206386fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2020
ms.locfileid: "85460462"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-does-not-have-permission-to-connect-to-this-computer"></a>Hata: Uzak bilgisayardaki Microsoft Visual Studio Uzaktan Hata Ayıklama İzleyicisinin bu bilgisayara bağlanma izni yok.

Bu hata, Visual Studio Uzaktan Hata Ayıklama İzleyicisi (msvsmon) çalıştırmayı deneyen kullanıcının yerel bilgisayarda bir hesabı olmadığında oluşur. Bu hata, eski hata ayıklama altyapısı kullanılarak uzaktan hata ayıklanırken oluşabilir.

## <a name="to-fix-this-problem"></a>Bu sorunu gidermek için

- Uzak bilgisayarda msvsmon çalıştıran kullanıcı hesabıyla aynı adı ve parolayı kullanarak, Visual Studio hata ayıklayıcısı ana bilgisayarına bir kullanıcı hesabı ekleyin.

   \-veya

- Msvsmon 'i yerel bilgisayara çağırma izni olan bir kullanıcı olarak çalıştırın. Bu, kullanıcının msvsmon bilgisayarında bir etki alanı kullanıcısı ve yönetici olması gerektiği anlamına gelir. Msvsmon çalıştırmak için Kullanıcı hesabını iki şekilde belirtebilirsiniz:

  - Msvsmon simgesine sağ tıklayın ve kısayol menüsünde **Farklı Çalıştır** ' ı seçin.

    \-veya

  - Komut Isteminde komutunu çalıştırın `runas.exe` .

## <a name="see-also"></a>Ayrıca bkz.

- [Uzaktan Hata Ayıklama Hataları ve Sorun Giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)
- [Uzaktan hata ayıklama](../debugger/remote-debugging.md)