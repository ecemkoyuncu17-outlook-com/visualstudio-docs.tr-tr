---
title: Mip-map oluşturma çeşidi | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 3b4b3583-0b01-4f5d-aacb-3f96d19111d9
caps.latest.revision: 9
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 3ac567677776c225008a581cc4d5de85ec2c882d
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63383959"
---
# <a name="mip-map-generation-variant"></a>Mip-map Oluşturma Çeşidi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Mip eşlemeleri hedefleri işlenmeyebilir dokular üzerinde sağlar.  
  
## <a name="interpretation"></a>Yorumu  
 Mip eşlemeleri öncelikle dokular küçültme altında diğer ad kullanımı yapıları ortadan kaldırmak için önceden hesaplama daha küçük sürümleri doku tarafından kullanılır. Bu ek doku, GPU bellek tüketmesine rağmen — yaklaşık % 33 daha fazla orijinal dokununkinden — Bunlar ayrıca GPU doku önbelleğe daha fazla kendi yüzey alanını en uygun ve içerikleri daha yüksek kullanımına ulaşmak için daha verimli.  
  
 3B görünümleri için bellek işleme performansını hem de görüntü kalitesini artırmak için ek dokular depolamak kullanılabilir olduğunda mip eşlemeleri öneririz.  
  
 Bu değişken bir önemli bir performans kazancı gösteriyorsa, mip eşlemeleri etkinleştirme ve en iyi doku önbelleğe alma verilmemiş olmadan dokular kullandığınızı gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Mip-map oluşturma yapılan her çağrı üzerinde zorunlu `ID3D11Device::CreateTexture2D` kaynak doku oluşturur. Mip-map oluşturma D3D11_TEXTUR2D_DESC nesneden olduğunda özellikle zorlanır `pDesc` olan değişmeyen bir gölgelendirici kaynak; açıklar:  
  
- Yalnızca D3D11_BIND_SHADER_RESOURCE bayrağı ayarlanmış BindFlags üye var.  
  
- Kullanım üye D3D11_USAGE_DEFUALT ya da D3D11_USAGE_IMMUTABLE ayarlanır.  
  
- CPUAccessFlags üyesi (CPU erişim yok) 0 olarak ayarlanır.  
  
- (Hiçbir çok örnekli düzgünleştirme (MSAA)) 1 olarak ayarlayın, sayım üyesi SampleDesc üye var.  
  
- MipLevels üyesi (hiçbir mevcut mip-map) 1 olarak ayarlanır.  
  
  İlk veri uygulama tarafından sağlandığında, doku biçimiyle otomatik mip-map oluşturma desteklemesi gerekir — D3D11_FORMAT_SUPPORT_MIP_AUTOGEN tarafından belirlenen şekilde — biçimi BC1, BC2 veya BC3; olmadığı sürece Aksi halde doku değiştirilmez ve ilk veri sağlandığında mip eşlemeleri oluşturulur.  
  
  Mip eşlemeleri bir doku için otomatik olarak oluşturulmuş, çağrılar `ID3D11Device::CreateShaderResourceView` MIP zinciri doku Örnekleme sırasında kullanılacak kayıttan yürütme sırasında değiştirilir.  
  
## <a name="example"></a>Örnek  
 **Mip-map oluşturma** değişken bu kodu kullanarak yeniden oluşturduğunuzda:  
  
```  
D3D11_TEXTURE2D_DESC texture_description;  
  
// ...  
  
texture_description.MipLevels = 0; // generate a full mipchain  
  
std::vector<D3D11_SUBRESOURCE_DATA> initial_data(num_mips);  
  
for (auto&& mip_level : initial_data)  
{  
    // fill mip_level with the application-supplied initial data  
}  
  
d3d_device->CreateTexture2D(&texture_description, initial_data.data(), &texture)  
```  
  
 Tam bir MIP zincir olan bir doku oluşturmak için `D3D11_TEXTURE2D_DESC::MipLevels` 0. MIP düzeylerini tam bir MIP zincir sayısıdır floor(log2(n) + 1), burada n, en büyük boyut dokunun.  
  
 İlk veri sağladığınızda unutmayın `CreateTexture2D`, her MIP düzeyini D3D11_SUBRESOURCE_DATA nesnesini sağlamanız gerekir.  
  
> [!NOTE]
> Kendi MIP düzeyi içeriği otomatik olarak üretmek yerine sağlamak istiyorsanız, doku bir görüntü kullanarak MIP eşlemeli dokular destekleyen Düzenleyicisi'ni ve ardından dosyayı yüklemek oluşturup gerekir MIP düzeylerine geçirmek `CreateTexture2D`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yarı/Çeyrek Doku Boyutları Çeşidi](../debugger/half-quarter-texture-dimensions-variant.md)
