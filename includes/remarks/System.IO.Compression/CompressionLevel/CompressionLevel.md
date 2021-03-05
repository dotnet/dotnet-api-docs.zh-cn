---
ms.openlocfilehash: 99b715f92b3efb466521aad00e8b88eb65cced4b
ms.sourcegitcommit: 9f423345753728e8cad38d4a22663a109e69ea91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "102091639"
---
压缩操作通常涉及压缩速度和有效性。 使用 <xref:System.IO.Compression.CompressionLevel> 枚举来指示在开发方案中更重要的因素：完成压缩操作的时间或压缩文件的大小。 这些值与特定的压缩级别无关;实现压缩的对象确定如何处理它们。

、、、和类的以下方法 <xref:System.IO.Compression.DeflateStream> <xref:System.IO.Compression.GZipStream> <xref:System.IO.Compression.ZipArchive> <xref:System.IO.Compression.ZipFile> <xref:System.IO.Compression.ZipFileExtensions> 包含一个名为 `compressionLevel` 的参数，可让你指定压缩级别：

-   <xref:System.IO.Compression.DeflateStream.%23ctor%28System.IO.Stream%2CSystem.IO.Compression.CompressionLevel%29?displayProperty=nameWithType>

-   <xref:System.IO.Compression.DeflateStream.%23ctor%28System.IO.Stream%2CSystem.IO.Compression.CompressionLevel%2CSystem.Boolean%29?displayProperty=nameWithType>

-   <xref:System.IO.Compression.GZipStream.%23ctor%28System.IO.Stream%2CSystem.IO.Compression.CompressionLevel%29?displayProperty=nameWithType>

-   <xref:System.IO.Compression.GZipStream.%23ctor%28System.IO.Stream%2CSystem.IO.Compression.CompressionLevel%2CSystem.Boolean%29?displayProperty=nameWithType>

-   <xref:System.IO.Compression.ZipArchive.CreateEntry%28System.String%2CSystem.IO.Compression.CompressionLevel%29?displayProperty=nameWithType>

-   <xref:System.IO.Compression.ZipFile.CreateFromDirectory%28System.String%2CSystem.String%2CSystem.IO.Compression.CompressionLevel%2CSystem.Boolean%29?displayProperty=nameWithType>

-   <xref:System.IO.Compression.ZipFileExtensions.CreateEntryFromFile%28System.IO.Compression.ZipArchive%2CSystem.String%2CSystem.String%2CSystem.IO.Compression.CompressionLevel%29?displayProperty=nameWithType>

## <a name="examples"></a>示例

下面的示例演示如何在使用类创建 zip 存档时设置压缩级别 <xref:System.IO.Compression.ZipFile> 。

[!code-csharp[System.IO.Compression.ZipFile#3](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program3.cs#3)]
[!code-vb[System.IO.Compression.ZipFile#3](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program3.vb#3)]

