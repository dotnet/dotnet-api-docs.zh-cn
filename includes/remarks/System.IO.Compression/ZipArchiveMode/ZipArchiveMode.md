---
ms.openlocfilehash: 4ceb75aa4a1641d8506aee84824eb59f23d1bf6a
ms.sourcegitcommit: 9f423345753728e8cad38d4a22663a109e69ea91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "102091600"
---
将模式设置为 "已读" 时，基础文件或流必须支持读取，但不支持查找。 如果基础文件或流支持查找，则会在请求时从存档中读取文件。 如果基础文件或流不支持查找，则整个存档保存在内存中。

将模式设置为 "创建" 时，基础文件或流必须支持写入，但不支持查找。 存档中的每个条目只能打开一次以进行写入。 如果创建单个条目，则会在数据可用时立即将数据写入基础流或文件。 如果创建多个项（例如通过调用 <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A> 方法），则会在创建所有项后将数据写入基础流或文件。

将模式设置为 "更新" 时，基础文件或流必须支持读取、写入和查找。 整个存档的内容保留在内存中，并且在释放存档之前，不会将任何数据写入到基础文件或流中。

以下方法包含一个名为 `mode` 的参数，该参数可用于指定存档模式：

-   <xref:System.IO.Compression.ZipArchive.%23ctor%28System.IO.Stream%2CSystem.IO.Compression.ZipArchiveMode%2CSystem.Boolean%29?displayProperty=nameWithType>

-   <xref:System.IO.Compression.ZipArchive.%23ctor%28System.IO.Stream%2CSystem.IO.Compression.ZipArchiveMode%29?displayProperty=nameWithType>

-   <xref:System.IO.Compression.ZipFile.Open%28System.String%2CSystem.IO.Compression.ZipArchiveMode%29?displayProperty=nameWithType>

## <a name="examples"></a>示例

下面的示例演示如何 `ZipArchiveMode` 在创建对象时指定一个值 <xref:System.IO.Compression.ZipArchive> 。

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]
