---
title: ClickOnce yönetilmeyen API Başvurusu | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- LaunchApplication [ClickOnce unmanaged]
- ClickOnce, unmanaged APIs
- CleanOnlineAppCache [ClickOnce unmanaged]
- CleanOnlineAppCacheW interface [ClickOnce unmanaged]
- GetDeploymentDataFromManifest [ClickOnce unmanaged]
ms.assetid: ec002138-4054-456d-bcc1-79ac2f4a4fd7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 714d7b18995bf1ad51b07e02227e440879f73c9e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68192313"
---
# <a name="clickonce-unmanaged-api-reference"></a>ClickOnce Yönetilmeyen API Başvurusu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] Yönetilmeyen genel API'ler dfshim.DLL'den.  
  
## <a name="cleanonlineappcache"></a>CleanOnlineAppCache  
 Temizler ve çevrimiçi tüm uygulamaları kaldırır [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] uygulama önbelleği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür; Aksi takdirde hata temsil eden HRESULT döndürür. Yönetilen bir özel durum oluşursa 0x80020009 (DISP_E_EXCEPTION) döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 CleanOnlineAppCache çağırma başlayacak [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] zaten çalışmıyorsa hizmet.  
  
## <a name="getdeploymentdatafrommanifest"></a>GetDeploymentDataFromManifest  
 Dağıtım bilgileri, bildirim ve etkinleştirme URL'den alır.  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|Tür|  
|---------------|-----------------|----------|  
|`pcwzActivationUrl`|Bir işaretçi `ActivationURL`.|LPCWSTR|  
|`pcwzPathToDeploymentManifest`|Bir işaretçi `PathToDeploymentManifest`.|LPCWSTR|  
|`pwzApplicationIdentity`|Tam uygulama kimliğini belirten bir NULL ile sonlandırılmış dize almak için arabellek için işaretçi.|LPWSTR|  
|`pdwIdentityBufferLength`|Bir işaretçi uzunluğu bir DWORD `pwzApplicationIdentity` arabelleğinde WCHAR'lar. Bu alanı boş sonlandırma karakter içerir.|LPDWORD|  
|`pwzProcessorArchitecture`|Uygulama dağıtımı, bildirimden işlemci mimarisinden belirten bir NULL ile sonlandırılmış dize almak için arabellek için işaretçi.|LPWSTR|  
|`pdwArchitectureBufferLength`|Bir işaretçi uzunluğu bir DWORD `pwzProcessorArchitecture` arabelleğinde WCHAR'lar.|LPDWORD|  
|`pwzApplicationManifestCodebase`|Uygulama bildiriminin bildirimindeki bir kod temelinde belirten bir NULL ile sonlandırılmış dize almak için arabellek için işaretçi.|LPWSTR|  
|`pdwCodebaseBufferLength`|Bir işaretçi uzunluğu bir DWORD `pwzApplicationManifestCodebase` arabelleğinde WCHAR'lar.|LPDWORD|  
|`pwzDeploymentProvider`|Arabellek için NULL ile sonlandırılmış bir dize almak için bir işaretçi bildirimi dağıtım sağlayıcısından varsa belirtir. Aksi takdirde, boş bir dize döndürülür.|LPWSTR|  
|`pdwProviderBufferLength`|Bir işaretçi uzunluğu bir DWORD `pwzProviderBufferLength`.|LPDWORD|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür; Aksi takdirde hata temsil eden HRESULT döndürür. Arabellek çok küçük olduğunda HRESULTFROMWIN32(ERROR_INSUFFICIENT_BUFFER) döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İşaretçileri null olmamalıdır. `pcwzActivationUrl` ve `pcwzPathToDeploymentManifest` boş olmamalıdır.  
  
 Etkinleştirme URL'sini temizlemek çağrı sahibinin sorumluluğundadır. Örneğin, kaçış ekleme gereken yerlere veya sorgu dizesi kaldırma karakter.  
  
 Giriş uzunluğunu sınırla çağrı sahibinin sorumluluğundadır. Örneğin, URL uzunluğu üst sınırı 2 KB'tır.  
  
## <a name="launchapplication"></a>LaunchApplication  
 Başlatır ve dağıtım URL'yi kullanarak bir uygulamayı yükler.  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|Tür|  
|---------------|-----------------|----------|  
|`deploymentUrl`|Dağıtım bildirimi URL'sini içeren bir NULL ile sonlandırılmış dizeye bir işaretçi.|LPCWSTR|  
|`data`|Daha sonraki kullanımlar için ayrılmıştır. NULL olmalıdır.|LPVOID|  
|`flags`|Daha sonraki kullanımlar için ayrılmıştır. 0 olmalıdır.|DWORD|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür; Aksi takdirde hata temsil eden HRESULT döndürür. Yönetilen bir özel durum oluşursa 0x80020009 (DISP_E_EXCEPTION) döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Deployment.Application.DeploymentServiceCom.CleanOnlineAppCache%2A>
