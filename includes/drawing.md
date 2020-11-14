---
ms.openlocfilehash: 1cef593bb522c1f49edd0cdcbaf6716c059c1ec6
ms.sourcegitcommit: 98adf68e9ecf7a9832b6f036ddac3996ac8836a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2020
ms.locfileid: "92558041"
---
> [!CAUTION]
> - <span data-ttu-id="96f22-101">`System.Drawing`不建议将命名空间用于新的开发，因为 Windows 或 ASP.NET 服务中不支持该命名空间，并且该命名空间不跨平台。</span><span class="sxs-lookup"><span data-stu-id="96f22-101">The `System.Drawing` namespace is not recommended for new development, due to not being supported within a Windows or ASP.NET service and it is not cross-platform.</span></span> <span data-ttu-id="96f22-102">建议将[ImageSharp](https://github.com/SixLabors/ImageSharp)和[SkiaSharp](https://github.com/mono/SkiaSharp)作为替代方法。</span><span class="sxs-lookup"><span data-stu-id="96f22-102">[ImageSharp](https://github.com/SixLabors/ImageSharp) and [SkiaSharp](https://github.com/mono/SkiaSharp) are recommended as alternatives.</span></span>
> - <span data-ttu-id="96f22-103">在 Windows 上， `System.Drawing` 依赖于作为操作系统一部分附带的 GDI + 本机库。</span><span class="sxs-lookup"><span data-stu-id="96f22-103">On Windows, `System.Drawing` depends on the GDI+ native library, which is shipped as part of the OS.</span></span> <span data-ttu-id="96f22-104">某些 Windows Sku，如 Windows Server Core 或 Windows Nano，不包含此本机库作为操作系统的一部分。</span><span class="sxs-lookup"><span data-stu-id="96f22-104">Some Windows SKUs, like Windows Server Core or Windows Nano, don't include this native library as part of the OS.</span></span> <span data-ttu-id="96f22-105">由于无法加载库，将在运行时引发异常。</span><span class="sxs-lookup"><span data-stu-id="96f22-105">Exceptions will be thrown at run time because the library can't be loaded.</span></span>