---
ms.openlocfilehash: fa70d34f3547beeca2bc21b83fb0fa0ebdd9f740
ms.sourcegitcommit: 0e407cf5ebbf9baaa2f56c752538e544cb4b443d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98697895"
---
> [!CAUTION]
> - `System.Drawing`不建议将命名空间用于新的开发，因为它在 Windows 服务、ASP.NET Core 和 ASP.NET 中不受支持。 尝试使用其中 `System.Drawing` 一种应用程序类型中的类可能会导致运行时异常并降低服务性能。 建议的替代项包括 [ImageSharp](https://github.com/SixLabors/ImageSharp)、 [SkiaSharp](https://github.com/mono/SkiaSharp)和 [Windows 映像组件](/windows/desktop/wic/-wic-about-windows-imaging-codec)。
> - 在 Windows 上， `System.Drawing` 依赖于作为操作系统一部分附带的 GDI + 本机库。 某些 Windows Sku，如 Windows Server Core 或 Windows Nano，不包含此本机库作为操作系统的一部分。 由于无法加载库，将在运行时引发异常。
