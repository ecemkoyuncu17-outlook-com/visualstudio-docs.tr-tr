---
title: ZipDirectory görevi | Microsoft Docs
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ZipDirectory
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ZipDirectory task [MSBuild]
- MSBuild, ZipDirectory task
ms.assetid: 916bb2e3-3017-4828-ae27-c0b5c99bbb48
caps.latest.revision: 16
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1092add6386ccc5bc1de78efcf7b623a617d920b
ms.sourcegitcommit: d20ce855461c240ac5eee0fcfe373f166b4a04a9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2020
ms.locfileid: "84183073"
---
# <a name="zipdirectory-task"></a>ZipDirectory görevi

Bir dizinin içeriğinden bir *. zip* arşivi oluşturur.

>[!NOTE]
>`ZipDirectory`Görev yalnızca MSBuild 15,8 ve üzeri sürümlerde kullanılabilir.

## <a name="parameters"></a>Parametreler

 Aşağıdaki tablo, görevin parametrelerini açıklar `ZipDirectory` .

|Parametre|Açıklama|
|---------------|-----------------|
|`DestinationFile`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem> parametre<br /><br /> Oluşturulacak *. zip* dosyasının tam yolu.|
|`Overwrite`|İsteğe bağlı `Boolean` parametre.<br /><br /> İse `true` , varsa hedef dosyanın üzerine yazılır. Varsayılan olarak olur `false` .|
|`SourceDirectory`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem> parametre.<br /><br /> İçinden bir *. zip* Arşivi oluşturulacak dizini belirtir.|

## <a name="remarks"></a>Açıklamalar

 Yukarıda listelenen parametrelere ek olarak, bu görev sınıfından devralınan parametreleri devralır <xref:Microsoft.Build.Tasks.TaskExtension> <xref:Microsoft.Build.Utilities.Task> . Bu ek parametrelerin ve açıklamalarının listesi için bkz. [TaskExtension temel sınıfı](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Örnek

 Aşağıdaki örnek (içeri aktarılmış bir *. targets* dosyası olarak kullanılırsa), bir proje oluşturulduktan sonra çıkış dizininden bir *. zip* arşivi oluşturur. `$(OutputPath)`Özelliği normalde bir MSBuild proje dosyasında tanımlanır, bu nedenle aşağıdaki dosyayı içeri aktaran bir proje dosyası bir ZIP arşivi üretir `output.zip` :

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <Target Name="ZipOutputPath" AfterTargets="Build">
        <ZipDirectory
            SourceDirectory="$(OutputPath)"
            DestinationFile="$(MSBuildProjectDirectory)\output.zip" />
    </Target>

</Project>
```

## <a name="see-also"></a>Ayrıca bkz.

- [Görevler](../msbuild/msbuild-tasks.md)
- [Görev başvurusu](../msbuild/msbuild-task-reference.md)
