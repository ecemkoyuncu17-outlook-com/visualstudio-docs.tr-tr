---
title: İletileri çıkış penceresine gönder | Microsoft Docs
ms.date: 11/08/2018
ms.topic: how-to
helpviewer_keywords:
- diagnostic messages [C#]
- System.Diagnostics.Debug class, Output window
- messages, diagnostic
- Debug.Print replacements
- diagnosis
- Output window, diagnostic messages
- System.Diagnostics.Trace class, Output window
- Trace class, diagnostic messages
- diagnostics
- debugger, Output window
- debugging [Visual Studio], diagnostic messages in Output window
- Debug class
ms.assetid: 386e9524-be17-4573-83fb-4f7c5cae0be0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 85d3c146775ac06b3118186738ee74932a4c452a
ms.sourcegitcommit: c076fe12e459f0dbe2cd508e1294af14cb53119f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2020
ms.locfileid: "85350478"
---
# <a name="send-messages-to-the-output-window"></a>Çıkış penceresine ileti gönderme

Çalışma zamanı iletilerini **Çıkış** penceresine, sınıf <xref:System.Diagnostics.Debug> kitaplığının parçası olan sınıfını veya sınıfını kullanarak yazabilirsiniz <xref:System.Diagnostics.Trace> <xref:System.Diagnostics> . <xref:System.Diagnostics.Debug>Yalnızca programınızın *hata ayıklama* sürümünde çıkış istiyorsanız sınıfını kullanın. <xref:System.Diagnostics.Trace>Hem *hata ayıklama* hem de *Sürüm* sürümlerinde çıkış istiyorsanız sınıfını kullanın.

## <a name="output-methods"></a>Çıkış yöntemleri
 <xref:System.Diagnostics.Trace>Ve <xref:System.Diagnostics.Debug> sınıfları aşağıdaki çıkış yöntemlerini sağlar:

- Farklı `Write` Yöntemler, önemli bir yürütme olmadan bilgi çıktı. Bu yöntemler `Debug.Print` Visual Basic önceki sürümlerinde kullanılan yöntemi değiştirir.

- <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>ve <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> belirli bir koşul başarısız olursa yürütme ve çıkış bilgilerini kesen Yöntemler. Varsayılan olarak, `Assert` yöntemi bilgileri bir iletişim kutusunda görüntüler. Daha fazla bilgi için bkz. [Yönetilen koddaki Onaylamalar](../debugger/assertions-in-managed-code.md).

- <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=fullName> <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=fullName> Yürütme ve çıkış bilgilerini her zaman kesen ve yöntemleri. Varsayılan olarak, `Fail` Yöntemler bilgileri bir iletişim kutusunda görüntüler.

**Çıkış** penceresinde hakkında bilgi de görüntülenebilir:

- Hata ayıklayıcı tarafından yüklenen veya yüklenmeyen modüller.

- Oluşturulan özel durumlar.

- Çıkış işlemi.

- Çıkış yapan iş parçacıkları.

## <a name="see-also"></a>Ayrıca bkz.
- [Hata ayıklayıcı güvenliği](../debugger/debugger-security.md)
- [Çıktı penceresi](../ide/reference/output-window.md)
- [İzleme ve araç uygulamaları](/dotnet/framework/debug-trace-profile/tracing-and-instrumenting-applications)
- [C#, F # ve Visual Basic proje türleri](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)
- [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)
