---
ms.openlocfilehash: 1cef593bb522c1f49edd0cdcbaf6716c059c1ec6
ms.sourcegitcommit: 98adf68e9ecf7a9832b6f036ddac3996ac8836a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2020
ms.locfileid: "92558041"
---
> [!CAUTION]
> - `System.Drawing`不建议将命名空间用于新的开发，因为 Windows 或 ASP.NET 服务中不支持该命名空间，并且该命名空间不跨平台。 建议将[ImageSharp](https://github.com/SixLabors/ImageSharp)和[SkiaSharp](https://github.com/mono/SkiaSharp)作为替代方法。
> - 在 Windows 上， `System.Drawing` 依赖于作为操作系统一部分附带的 GDI + 本机库。 某些 Windows Sku，如 Windows Server Core 或 Windows Nano，不包含此本机库作为操作系统的一部分。 由于无法加载库，将在运行时引发异常。