---
ms.openlocfilehash: ee2b3146c493bccfd00f3da3bf5e53cd82c38689
ms.sourcegitcommit: 0889e849406dc7546327ee408ec724fccd468268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2021
ms.locfileid: "99064969"
---
> [!NOTE]
> **仅 .NET Framework：** 当你在中使用星号通配符 `searchPattern` 并指定三个字符的文件扩展名（例如 ".txt"）时 \* ，此方法还会返回扩展名以指定扩展名 *开头* 的文件。 例如，搜索模式 " \* .xls" 同时返回 "book.xls" 和 "book.xlsx"。 仅当搜索模式中使用了星号并且提供的文件扩展名正好为三个字符时，才会发生此行为。 如果使用问号通配符而不是星号，则此方法只返回与指定的文件扩展名完全匹配的文件。 下表描述了 .NET Framework 中的这种异常。
>
> | 目录中的文件  | 搜索模式 | .NET 5 + 返回   | .NET Framework 返回  |
> |---------------------|----------------|-------------------|-------------------------|
> | file.ai、node.js   | * ai           | file.ai           | file.ai                 |
> | book.xls，book.xlsx | * .xls          | book.xls          | **book.xls，book.xlsx** |
> | file.ai、node.js   | ?.ai           | file.ai           | file.ai                 |
> | book.xls，book.xlsx | ?.xls          | book.xls          | book.xls                |
