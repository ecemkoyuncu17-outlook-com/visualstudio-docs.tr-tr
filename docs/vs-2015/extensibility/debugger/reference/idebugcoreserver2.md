---
title: IDebugCoreServer2 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugCoreServer2
helpviewer_keywords:
- IDebugCoreServer2 interface
ms.assetid: 9c47d0a6-9eb1-464e-bd44-fa2b552d4d36
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c0bca6ccd3738518df339084b0f6463be181e52d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68192910"
---
# <a name="idebugcoreserver2"></a>IDebugCoreServer2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu arabirim, temsil ve ağ üzerindeki bir makinede bir sunucudan bilgi almak için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugCoreServer2 : IUknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Visual Studio, bir sunucu temsil etmek için bu arabirimi uygular. Visual Studio'nun her örneği, bu arabirim bir örneğini oluşturur.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Özel bağlantı noktası sağlayıcısı bir çağrıda bu arabirimin aldığı [olay](../../../extensibility/debugger/reference/idebugportevents2-event.md).  
  
 Bu arabirim için bir çağrı aracılığıyla dolaylı olarak bir hata ayıklama altyapısı elde edebilirsiniz [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md) (döndüren [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md), türetilmiş bir arabirim `IDebugCoreServer2`).  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugCoreServer2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetMachineInfo](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineinfo.md)|Bir makine özniteliklerini ve adını alır.|  
|[GetMachineName](../../../extensibility/debugger/reference/idebugcoreserver2-getmachinename.md)|Bir makine adını alır.|  
|[GetPortSupplier](../../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)|Bir makinede var olan bağlantı noktası sağlayıcısı alır.|  
|[GetPort](../../../extensibility/debugger/reference/idebugcoreserver2-getport.md)|Bir makinede zaten bir bağlantı noktasını alır.|  
|[EnumPorts](../../../extensibility/debugger/reference/idebugcoreserver2-enumports.md)|Tüm bağlantı noktaları için bir numaralandırıcı bir makinede oluşturur.|  
|[EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md)|Tüm bağlantı noktası sağlayıcıları için bir numaralandırıcı bir makinede oluşturur.|  
|[GetMachineUtilities_V7](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineutilities-v7.md)|Makine yardımcı programlar bir makine için alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim, ağdaki makineler üzerinde çalışan işlemler göz atmak için Visual Studio tarafından da kullanılır.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Ad alanı: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [Olay](../../../extensibility/debugger/reference/idebugportevents2-event.md)   
 [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md)   
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)
