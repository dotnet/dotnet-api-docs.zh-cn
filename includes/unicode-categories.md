---
ms.openlocfilehash: a34839b9cf9b85f6ab909d9d44039d68d6b17b34
ms.sourcegitcommit: e35871bd34c549fe37948635bef7c8520ab4dc08
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2020
ms.locfileid: "94329920"
---
.NET 维护自己的字符表及其相应的类别，这可确保在不同平台上运行的特定版本的 .NET 实现返回相同的字符类别信息。 在 Linux、macOS 或 Windows 19H1 或更高版本上运行的 .NET 5 以及在 Linux 和 macOS 上运行的 .NET Core 中，字符类别信息由 [Unicode 库的国际化组件](http://site.icu-project.org/) 提供。

下表列出了 .NET 版本及其字符类别所基于的 Unicode 标准。

|.NET 版本|Unicode 标准版本|
|----------------------------|-------------------------------------|
|.NET Framework 1.1|[Unicode 标准，版本 4.0.0](https://www.unicode.org/versions/Unicode4.0.0/)|
|.NET Framework 2.0|[Unicode 标准，版本 5.0.0](https://www.unicode.org/versions/Unicode5.0.0)|
|.NET Framework 3.5|[Unicode 标准，版本 5.0.0](https://www.unicode.org/versions/Unicode5.0.0)|
|.NET Framework 4|[Unicode 标准，版本 5.0.0](https://www.unicode.org/versions/Unicode5.0.0)|
|.NET Framework 4.5|[Unicode 标准，版本 6.3.0](https://www.unicode.org/versions/Unicode6.3.0/)|
|.NET Framework 4.51|[Unicode 标准，版本 6.3.0](https://www.unicode.org/versions/Unicode6.3.0/)|
|.NET Framework 4.52|[Unicode 标准，版本 6.3.0](https://www.unicode.org/versions/Unicode6.3.0/)|
|.NET Framework 4.6|[Unicode 标准，版本 6.3.0](https://www.unicode.org/versions/Unicode6.3.0/)|
|.NET Framework 4.61|[Unicode 标准，版本 6.3.0](https://www.unicode.org/versions/Unicode6.3.0/)|
|.NET Framework 4.6.2 及更高版本|[Unicode 标准，版本 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/)|
|.NET Core (所有版本) 和 .NET 5 +|[Unicode 标准，版本 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/)|
