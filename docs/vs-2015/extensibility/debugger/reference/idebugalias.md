---
title: IDebugAlias | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugAlias
helpviewer_keywords:
- IDebugAlias interface
ms.assetid: 3cc4c9a4-7805-4239-b00e-eb4a024f3c55
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6c05b6987804681176abdde0e8c94a7463a9163c
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63442314"
---
# <a name="idebugalias"></a>IDebugAlias
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

> [!IMPORTANT]
> Visual Studio 2015'te, bu şekilde ifade değerlendiricisi uygulama kullanım dışı bırakılmıştır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricilerini](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Bir değişken için sayısal bir diğer adı temsil eder. Bir diğer ad yalnızca bir değişken için farklı bir ad olduğu.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugAlias : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 İfade değerlendirici (EE) sayısal diğer adları için değişkenleri desteklemek için bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 [CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md) belirli bir nesnesi için bir diğer ad oluşturur. Diğer adlar için aranacak kullanın [FindAlias](../../../extensibility/debugger/reference/idebugbinder3-findalias.md) veya [GetAllAliases](../../../extensibility/debugger/reference/idebugbinder3-getallaliases.md).  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki yöntemlerden tanımlanan `IDebugAlias` arabirimi.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetObject](../../../extensibility/debugger/reference/idebugalias-getobject.md)|Bu diğer adı başvurduğu nesneyi alır.|  
|[GetName](../../../extensibility/debugger/reference/idebugalias-getname.md)|Diğer ad alır.|  
|[GetICorDebugValue](../../../extensibility/debugger/reference/idebugalias-geticordebugvalue.md)|Alır bir `ICorDebugValue` erişim sağlayan bir arabirimi yönetilen kod bilgilerini bu nesne (yalnızca yönetilen kod).|  
|[Dispose](../../../extensibility/debugger/reference/idebugalias-dispose.md)|Bu, diğer ad olarak artık kullanılmayan işaretler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir diğer ad, sonrasında # karakteri, örneğin, 1001 # dize biçiminde bir ondalık sayıdır.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: ee.h  
  
 Ad alanı: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfade değerlendirme arabirimleri](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md)   
 [FindAlias](../../../extensibility/debugger/reference/idebugbinder3-findalias.md)   
 [GetAllAliases](../../../extensibility/debugger/reference/idebugbinder3-getallaliases.md)
