---
title: Ekleme ve programdan ayırma | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, attaching to programs
- debug engines, detaching from programs
ms.assetid: 79dcbb9b-c7f8-40fc-8a00-f37fe1934f51
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6e232a6f7fcb8813670ca6d949fdb6b3287bb79c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68146454"
---
# <a name="attaching-and-detaching-to-a-program"></a>Programa Ekleme ve Programdan Ayırma
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Hata ayıklayıcısı ekleniyor, yöntemlerini ve olaylarını uygun özniteliklerle doğru sırasını gönderilmesi gerekir.  
  
## <a name="sequence-of-methods-and-events"></a>Dizi yöntemler ve olaylar  
  
1. Oturum hata ayıklama Yöneticisi (SDM) çağıran [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) yöntemi.  
  
    Hata ayıklama altyapısı (DE) işlem modelini temel alan `IDebugProgramNodeAttach2::OnAttach` yöntemi ne olacağını belirler aşağıdaki yöntemlerden birini döndürür.  
  
    Varsa `S_FALSE` döndürülür, hata ayıklama altyapısı başarıyla bağlı program. Aksi takdirde, [iliştirme](../../extensibility/debugger/reference/idebugengine2-attach.md) yöntemi ekleme işlemi tamamlamak için çağrılır.  
  
    Varsa `S_OK` döndürülür, DE aynı işlemde SDM olarak yüklenecek. SDM aşağıdaki görevleri gerçekleştirir:  
  
   1. Çağrıları [GetEngineInfo](../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md) altyapısı DE almak için.  
  
   2. Birlikte DE oluşturur.  
  
   3. Çağrıları [ekleme](../../extensibility/debugger/reference/idebugengine2-attach.md).  
  
2. DE gönderen bir [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) ile SDM için bir `EVENT_SYNC` özniteliği.  
  
3. DE gönderen bir [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) ile SDM için bir `EVENT_SYNC` özniteliği.  
  
4. DE gönderen bir [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) ile SDM için bir `EVENT_SYNC_STOP` özniteliği.  
  
   Bir programdan ayırma basit, iki adımlı işlem aşağıdaki gibidir:  
  
5. SDM çağrıları [ayırma](../../extensibility/debugger/reference/idebugprogram2-detach.md).  
  
6. DE gönderen bir [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklayıcısı Olaylarını Çağırma](../../extensibility/debugger/calling-debugger-events.md)
