---
title: Metin Şablonlarında Çıkış Sıraları Kullanma
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, escape sequences
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 83e6e5cf163037077d0517e5f7ea460f9124f27c
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/01/2020
ms.locfileid: "75594051"
---
# <a name="use-escape-sequences-in-text-templates"></a>Metin şablonlarında kaçış dizilerini kullanma

Metin şablonu etiketleri ve (yalnızca C# kodda) denetim karakterlerini ve tırnak işaretlerini atlamak için metin şablonlarındaki kaçış dizilerini kullanabilirsiniz.

Çıkış dosyasına standart bir kod bloğunun açık ve kapalı etiketlerini yazdırmak için etiketleri aşağıdaki gibi kaçış:

```
\<# ... \#>
```

Diğer metin şablonu yönergesi ve kod bloğu etiketleriyle aynı şekilde yapabilirsiniz.

Metin bloğu metin şablonu etiketlerini kaçış için kullanılan dizeleri içeriyorsa, aşağıdaki kaçış dizilerini kullanabilirsiniz:

- Bir metin şablonu etiketinin öncesinde çift sayıda kaçış (\\) karakteri varsa, şablon ayrıştırıcısı kaçış karakterlerinin yarısını içerir ve sırası metin şablonu etiketi olarak ekler. Örneğin, metin şablonunda dört kaçış karakteri varsa oluşturulan dosyada iki "\\" karakteri olacaktır.

- Metin şablonu etiketinin öncesinde tek sayıda kaçış (\\) karakteri varsa, şablon ayrıştırıcısı "\\" karakterlerinin yarısını ve etiketinin kendisini (\<# veya # >) içerecektir. Etiket, bir metin şablonu etiketi olarak kabul edilmez.

- Bir kaçış (\\) karakteri, bir denetim karakteri veya tırnak işareti (yalnızca içinde C# ) dışında herhangi bir sırada başka bir yerde görünürse, karakter doğrudan çıktı olur.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: Çıkış Sıraları Kullanarak Şablonlardan Şablon Oluşturma](../modeling/how-to-generate-templates-from-templates-by-using-escape-sequences.md)
