---
title: Visual Studio 'da çözüm veya proje olmadan JavaScript kodu yazma
titleSuffix: ''
description: Visual Studio, bir proje dosyası veya çözüm dosyası üzerinde bağımlılığını olmadan kod oluşturma desteği sağlar
ms.custom: seodec18
ms.date: 09/24/2018
ms.topic: how-to
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: jillfra
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 187ca5ea0d0232e0ca8b99165e77ee265b81e801
ms.sourcegitcommit: 1d4f6cc80ea343a667d16beec03220cfe1f43b8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85285094"
---
# <a name="develop-javascript-and-typescript-code-in-visual-studio-without-solutions-or-projects"></a>Visual Studio 'da çözüm veya proje olmadan JavaScript ve TypeScript kodu geliştirme

Visual Studio 2017 ' den başlayarak, [Proje veya çözümler olmadan kod geliştirebilirsiniz](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md). Bu, kod klasörünü açmanıza ve IntelliSense, arama, yeniden düzenleme, hata ayıklama ve daha fazlası gibi zengin düzenleyici desteğiyle çalışmaya hemen başlayabilmenizi sağlar. Bu özelliklere ek olarak, Visual Studio için Node.js araçları, TypeScript dosyaları oluşturmaya, NPM paketlerini yönetmeye ve NPM betikleri çalıştırmaya yönelik destek ekler.

Başlamak için araç çubuğundan **Dosya**  >  **Aç**  >  **klasörünü** seçin. Çözüm Gezgini klasördeki tüm dosyaları görüntüler ve düzenlemeden başlamak için herhangi bir dosyayı açabilirsiniz. Arka planda, Visual Studio, NPM, derleme ve hata ayıklama özelliklerini etkinleştirmek için dosyaları dizinliyor.

> [!IMPORTANT]
> Bu makalede açıklanan, npm tümleştirmesi dahil özelliklerinin birçoğu, Visual Studio 2017 sürüm 15,8 veya sonraki sürümleri gerektirir. Visual Studio **Node.js geliştirme** iş yükünün yüklenmesi gerekir.

## <a name="npm-integration"></a>npm tümleştirmesi

Açtığınız klasör bir *package.js* dosyası içeriyorsa, NPM 'ye özgü bir bağlam menüsünü (kısayol menüsü) göstermek için *package.jsüzerinde* sağ tıklayabilirsiniz.

![Çözüm Gezgini NPM menüsü](../javascript/media/solution-explorer-npm-ctx.png)

Kısayol menüsünde, NPM tarafından yüklenen paketleri, [NPM paketlerini](npm-package-management.md) bir proje dosyası kullanırken yönettiğiniz şekilde yönetebilirsiniz.

Ayrıca, menü Ayrıca `scripts` *üzerindepackage.js*öğesinde tanımlanan betikleri çalıştırmanıza de olanak tanır. Bu betikler, ortam değişkeninde kullanılabilir Node.js sürümünü kullanacaktır `PATH` . Betikler yeni bir pencerede çalışır. Bu, derleme veya çalıştırma betikleri çalıştırmak için harika bir yoldur.

## <a name="build-and-debug"></a>Derleme ve hata ayıklama

### <a name="packagejson"></a>package.json
Klasördeki *package.js* bir `main` öğesi belirtiyorsa, **hata ayıklama** komutu, *package.js*için sağ tıklama kısayol menüsünde kullanılabilir olacaktır.
Bunu tıklatmak, belirtilen komut dosyası bağımsız değişkeni olarak *node.exe* başlayacaktır.

### <a name="javascript-files"></a>JavaScript dosyaları
JavaScript dosyalarında hata ayıklama yaparak bir dosyaya sağ tıklayıp kısayol menüsünden **Hata Ayıkla** ' yı seçebilirsiniz. Bu, bağımsız değişkeni olarak bu JavaScript dosyası ile *node.exe* başlar.

### <a name="typescript-files-and-tsconfigjson"></a>TypeScript dosyaları ve üzerinde tsconfig.js
Klasörde mevcut bir *tsconfig.js* yoksa, bu dosyayı derleyip hata ayıklamanın kısayol menü komutlarını görmek Için bir TypeScript dosyasına sağ tıklayabilirsiniz. Bu komutları kullandığınızda, varsayılan seçeneklerle *tsc.exe* kullanarak derleyin veya hata ayıklayın. (Hata ayıklayabilmeniz için önce dosyayı oluşturmanız gerekir.)

> [!NOTE]
> TypeScript kodu oluştururken ' de yüklü en yeni sürümü kullanıyoruz `C:\Program Files (x86)\Microsoft SDKs\TypeScript` .

Klasörde mevcut bir *tsconfig.js* varsa, bu TypeScript dosyasında hata ayıklamak üzere bir menü komutu görmek Için bir TypeScript dosyasına sağ tıklayabilirsiniz. Seçeneği yalnızca `outFile` *üzerindetsconfig.js*belirtilmemişse görüntülenir. Eğer `outFile` belirtilmişse, *üzerindetsconfig.js* sağ tıklayıp doğru seçeneği belirleyerek bu dosyada hata ayıklayabilirsiniz. Bu `tsconfig.json` Dosya Ayrıca, derleyici seçeneklerini belirtmenize izin veren bir yapı seçeneği sağlar.

> [!NOTE]
> *tsconfig.js* hakkında daha fazla bilgi Için [tsconfig.jsTypeScript el kitabı sayfasında](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html)hakkında daha fazla bilgi edinebilirsiniz.

## <a name="unit-tests"></a>Birim testleri
*Üzerindepackage.js*bir test kökü belirterek, Visual Studio 'da birim testi tümleştirmesini etkinleştirebilirsiniz:

```json
{
    // ...
    "vsTest":{
        "testRoot": "./tests"
    }
    // ...
}
```

Test Çalıştırıcısı, hangi test çerçevesinin kullanılacağını belirleyen yerel olarak yüklenen paketleri numaralandırır.
Desteklenen çerçevelerin hiçbiri tanınmazsa, Test Çalıştırıcısı varsayılan olarak *ExportRunner*olur. Desteklenen diğer çerçeveler şunlardır:
* Mocha ([mochajs.org](https://mochajs.org/))
* Jasmine ([Jasmine.GitHub.io](https://jasmine.github.io/))
* Bant ([GitHub.com/substack/Tape](https://github.com/substack/tape))
* Jest ([jestjs.io](https://jestjs.io/))

Test Gezgini 'ni açtıktan sonra ( **Test**  >  **Windows**  >  **Test Gezgini**'ni seçin), Visual Studio Testleri bulur ve görüntüler.

> [!NOTE]
> Test Çalıştırıcısı yalnızca test kökündeki JavaScript dosyalarını numaralandıracaktır, çünkü uygulamanız TypeScript 'te yazılmışsa, önce bunları derlemeniz gerekir.
