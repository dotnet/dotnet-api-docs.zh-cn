---
ms.openlocfilehash: 99b715f92b3efb466521aad00e8b88eb65cced4b
ms.sourcegitcommit: 9f423345753728e8cad38d4a22663a109e69ea91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "102091639"
---
<span data-ttu-id="21113-101">压缩操作通常涉及压缩速度和有效性。</span><span class="sxs-lookup"><span data-stu-id="21113-101">Compression operations usually involve a tradeoff between the speed and the effectiveness of compression.</span></span> <span data-ttu-id="21113-102">使用 <xref:System.IO.Compression.CompressionLevel> 枚举来指示在开发方案中更重要的因素：完成压缩操作的时间或压缩文件的大小。</span><span class="sxs-lookup"><span data-stu-id="21113-102">You use the <xref:System.IO.Compression.CompressionLevel> enumeration to indicate which factor is more important in your development scenario: the time to complete the compression operation or the size of the compressed file.</span></span> <span data-ttu-id="21113-103">这些值与特定的压缩级别无关;实现压缩的对象确定如何处理它们。</span><span class="sxs-lookup"><span data-stu-id="21113-103">These values do not correspond to specific compression levels; the object that implements compression determines how to handle them.</span></span>

<span data-ttu-id="21113-104">、、、和类的以下方法 <xref:System.IO.Compression.DeflateStream> <xref:System.IO.Compression.GZipStream> <xref:System.IO.Compression.ZipArchive> <xref:System.IO.Compression.ZipFile> <xref:System.IO.Compression.ZipFileExtensions> 包含一个名为 `compressionLevel` 的参数，可让你指定压缩级别：</span><span class="sxs-lookup"><span data-stu-id="21113-104">The following methods of the <xref:System.IO.Compression.DeflateStream>, <xref:System.IO.Compression.GZipStream>, <xref:System.IO.Compression.ZipArchive>, <xref:System.IO.Compression.ZipFile>, and <xref:System.IO.Compression.ZipFileExtensions> classes include a parameter named `compressionLevel` that lets you specify the compression level:</span></span>

-   <xref:System.IO.Compression.DeflateStream.%23ctor%28System.IO.Stream%2CSystem.IO.Compression.CompressionLevel%29?displayProperty=nameWithType>

-   <xref:System.IO.Compression.DeflateStream.%23ctor%28System.IO.Stream%2CSystem.IO.Compression.CompressionLevel%2CSystem.Boolean%29?displayProperty=nameWithType>

-   <xref:System.IO.Compression.GZipStream.%23ctor%28System.IO.Stream%2CSystem.IO.Compression.CompressionLevel%29?displayProperty=nameWithType>

-   <xref:System.IO.Compression.GZipStream.%23ctor%28System.IO.Stream%2CSystem.IO.Compression.CompressionLevel%2CSystem.Boolean%29?displayProperty=nameWithType>

-   <xref:System.IO.Compression.ZipArchive.CreateEntry%28System.String%2CSystem.IO.Compression.CompressionLevel%29?displayProperty=nameWithType>

-   <xref:System.IO.Compression.ZipFile.CreateFromDirectory%28System.String%2CSystem.String%2CSystem.IO.Compression.CompressionLevel%2CSystem.Boolean%29?displayProperty=nameWithType>

-   <xref:System.IO.Compression.ZipFileExtensions.CreateEntryFromFile%28System.IO.Compression.ZipArchive%2CSystem.String%2CSystem.String%2CSystem.IO.Compression.CompressionLevel%29?displayProperty=nameWithType>

## <a name="examples"></a><span data-ttu-id="21113-105">示例</span><span class="sxs-lookup"><span data-stu-id="21113-105">Examples</span></span>

<span data-ttu-id="21113-106">下面的示例演示如何在使用类创建 zip 存档时设置压缩级别 <xref:System.IO.Compression.ZipFile> 。</span><span class="sxs-lookup"><span data-stu-id="21113-106">The following example shows how to set the compression level when creating a zip archive by using the <xref:System.IO.Compression.ZipFile> class.</span></span>

[!code-csharp[System.IO.Compression.ZipFile#3](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program3.cs#3)]
[!code-vb[System.IO.Compression.ZipFile#3](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program3.vb#3)]

