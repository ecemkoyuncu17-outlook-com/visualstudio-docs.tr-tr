---
title: T4 derleme yönergesi | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: 44949749-ce3c-4fb5-8690-a17f1564ac2f
caps.latest.revision: 6
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: bc0e6e7e1530abb63beabc6fa4aedd4a0fa985af
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72672333"
---
# <a name="t4-assembly-directive"></a>T4 Derleme Yönergesi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

@No__t_0 tasarım zamanı metin şablonunda, `assembly` yönergesi şablon kodunuzun türlerini kullanabilmesi için bir derlemeyi yükler. Efekt, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] projesine derleme başvurusu eklemeye benzer.

 Metin şablonları yazma hakkında genel bir bakış için bkz. [T4 metin şablonu yazma](../modeling/writing-a-t4-text-template.md).

> [!NOTE]
> Çalışma zamanı (önceden işlenmiş) metin şablonunda `assembly` yönergesine ihtiyacınız yoktur. Bunun yerine, gerekli derlemeleri [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] projenizin **başvurularına** ekleyin.

## <a name="using-the-assembly-directive"></a>Derleme Yönergesini Kullanma
 Yönergenin sözdizimi aşağıdaki gibidir:

```
<#@ assembly name="[assembly strong name|assembly file name]" #>
```

 Derleme adı aşağıdakilerden biri olmalıdır:

- GAC 'deki bir derlemenin tanımlayıcı adı, örneğin `System.Xml.dll`. Ayrıca, `name="System.Xml, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"` gibi uzun biçimi de kullanabilirsiniz. Daha fazla bilgi için bkz. <xref:System.Reflection.AssemblyName>.

- Derlemenin mutlak yolu

  @No__t_2 gibi [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] değişkenlerine başvurmak için `$(variableName)` sözdizimini ve ortam değişkenlerine başvurmak için `%VariableName%` kullanabilirsiniz. Örneğin:

```
<#@ assembly name="$(SolutionDir)\MyProject\bin\Debug\SomeLibrary.Dll" #>
```

 Derleme yönergesinin önceden işlenmiş metin şablonu üzerinde etkisi yoktur. Bunun yerine, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] projenizin **Başvurular** bölümüne gerekli başvuruları ekleyin. Daha fazla bilgi için bkz. [T4 metin şablonlarıyla çalışma zamanı metin üretimi](../modeling/run-time-text-generation-with-t4-text-templates.md).

## <a name="standard-assemblies"></a>Standart Derlemeler
 Aşağıdaki derlemeler otomatik olarak yüklenir, böylece onlar için derleme yönergelerini yazmanıza gerek yoktur:

- `Microsoft.VisualStudio.TextTemplating.1*.dll`

- `System.dll`

- `WindowsBase.dll`

  Özel bir yönerge kullanırsanız, yönerge işlemcisi ek derlemeler yükleyebilir. Örneğin, etki alanına özgü dil (DSL) için şablonlar yazarsanız, aşağıdaki derlemeler için derleme yönergeleri yazmak gerekmez:

- `Microsoft.VisualStudio.Modeling.Sdk.1*.dll`

- `Microsoft.VisualStudio.Modeling.Sdk.Diagrams.1*.dsl`

- `Microsoft.VisualStudio.TextTemplating.Modeling.1*.dll`

- DSL'nizi içeren derleme.

## <a name="msbuild"></a>MSBuild ve Visual Studio 'da proje özelliklerini kullanma
 $(SolutionDir) gibi Visual Studio makroları MSBuild içinde çalışmaz. Şablonları yapı makinenizde dönüştürmek isterseniz, bunun yerine proje özelliklerini kullanmanız gerekir.

 Proje özelliği tanımlamak için .csproj veya .vbproj dosyanızı düzenleyin. Bu örnek, `myLibFolder` adlı bir özelliği tanımlar:

```xml
<!-- Define a project property, myLibFolder: -->
<PropertyGroup>
    <myLibFolder>$(MSBuildProjectDirectory)\..\libs</myLibFolder>
</PropertyGroup>

<!-- Tell the MSBuild T4 task to make the property available: -->
<ItemGroup>
    <T4ParameterValues Include="myLibFolder">
      <Value>$(myLibFolder)</Value>
    </T4ParameterValues>
  </ItemGroup>

```

 Artık proje özelliğinizi metin şablonlarında kullanabilirsiniz, böylece hem Visual Studio hem de MSBuild içinde doğru dönüştürme yapılır:

```
<#@ assembly name="$(myLibFolder)\MyLib.dll" #>
```

## <a name="see-also"></a>Ayrıca Bkz.
 [T4 Include Yönergesi](../modeling/t4-include-directive.md)
