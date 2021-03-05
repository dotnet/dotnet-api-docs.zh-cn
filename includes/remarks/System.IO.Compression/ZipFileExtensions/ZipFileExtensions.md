---
ms.openlocfilehash: 1af9ce8cec811e07e0efaa475c002201530b8d7b
ms.sourcegitcommit: 9f423345753728e8cad38d4a22663a109e69ea91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "102091509"
---
<span data-ttu-id="aff50-101"><xref:System.IO.Compression.ZipFileExtensions>类只包含扩展和类的静态方法 <xref:System.IO.Compression.ZipArchive> <xref:System.IO.Compression.ZipArchiveEntry> 。</span><span class="sxs-lookup"><span data-stu-id="aff50-101">The <xref:System.IO.Compression.ZipFileExtensions> class contains only static methods that extend the <xref:System.IO.Compression.ZipArchive> and <xref:System.IO.Compression.ZipArchiveEntry> classes.</span></span> <span data-ttu-id="aff50-102">不创建类的实例 <xref:System.IO.Compression.ZipFileExtensions> ; 相反，您可以从或的实例使用这些方法 <xref:System.IO.Compression.ZipArchive> <xref:System.IO.Compression.ZipArchiveEntry> 。</span><span class="sxs-lookup"><span data-stu-id="aff50-102">You do not create an instance of the <xref:System.IO.Compression.ZipFileExtensions> class; instead, you use these methods from instances of <xref:System.IO.Compression.ZipArchive> or <xref:System.IO.Compression.ZipArchiveEntry>.</span></span>

<span data-ttu-id="aff50-103">若要使用扩展方法，必须 `System.IO.Compression.FileSystem` 在项目中引用程序集。</span><span class="sxs-lookup"><span data-stu-id="aff50-103">To use the extension methods, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span> <span data-ttu-id="aff50-104">`System.IO.Compression.FileSystem`程序集在 Windows 8.x 应用商店应用中不可用。</span><span class="sxs-lookup"><span data-stu-id="aff50-104">The `System.IO.Compression.FileSystem` assembly is not available in Windows 8.x Store apps.</span></span> <span data-ttu-id="aff50-105">因此， <xref:System.IO.Compression.ZipFileExtensions> 和 <xref:System.IO.Compression.ZipFile> 类 (在 `System.IO.Compression.FileSystem` 程序集) 中都不能在 Windows 8.x 应用商店应用中使用。</span><span class="sxs-lookup"><span data-stu-id="aff50-105">Therefore, the <xref:System.IO.Compression.ZipFileExtensions> and <xref:System.IO.Compression.ZipFile> classes (both of which are in the `System.IO.Compression.FileSystem` assembly) are not available in Windows 8.x Store apps.</span></span> <span data-ttu-id="aff50-106">在 Windows 8.x 应用商店应用中，使用、、和中的方法来处理压缩的文件 <xref:System.IO.Compression.ZipArchive> <xref:System.IO.Compression.ZipArchiveEntry> <xref:System.IO.Compression.DeflateStream> <xref:System.IO.Compression.GZipStream> 。</span><span class="sxs-lookup"><span data-stu-id="aff50-106">In Windows 8.x Store apps, you work with compressed files by using the methods in <xref:System.IO.Compression.ZipArchive>, <xref:System.IO.Compression.ZipArchiveEntry>, <xref:System.IO.Compression.DeflateStream>, and <xref:System.IO.Compression.GZipStream>.</span></span>

<span data-ttu-id="aff50-107"><xref:System.IO.Compression.ZipFileExtensions>类包含四个扩展的方法 <xref:System.IO.Compression.ZipArchive> ：</span><span class="sxs-lookup"><span data-stu-id="aff50-107">The <xref:System.IO.Compression.ZipFileExtensions> class contains four methods that extend <xref:System.IO.Compression.ZipArchive>:</span></span>

-   <xref:System.IO.Compression.ZipFileExtensions.CreateEntryFromFile%28System.IO.Compression.ZipArchive%2CSystem.String%2CSystem.String%29>

-   <xref:System.IO.Compression.ZipFileExtensions.CreateEntryFromFile%28System.IO.Compression.ZipArchive%2CSystem.String%2CSystem.String%2CSystem.IO.Compression.CompressionLevel%29>

-   <xref:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%28System.IO.Compression.ZipArchive%2CSystem.String%29>

-   <xref:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%28System.IO.Compression.ZipArchive%2CSystem.String%2CSystem.Boolean%29>

<span data-ttu-id="aff50-108"><xref:System.IO.Compression.ZipFileExtensions>类包含两个扩展的方法 <xref:System.IO.Compression.ZipArchiveEntry> ：</span><span class="sxs-lookup"><span data-stu-id="aff50-108">The <xref:System.IO.Compression.ZipFileExtensions> class contains two methods that extend <xref:System.IO.Compression.ZipArchiveEntry>:</span></span>

-   <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%28System.IO.Compression.ZipArchiveEntry%2CSystem.String%29>

-   <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%28System.IO.Compression.ZipArchiveEntry%2CSystem.String%2CSystem.Boolean%29>

## <a name="examples"></a><span data-ttu-id="aff50-109">示例</span><span class="sxs-lookup"><span data-stu-id="aff50-109">Examples</span></span>

<span data-ttu-id="aff50-110">下面的示例演示如何从现有文件在 zip 存档中创建新条目，并将存档内容提取到目录中。</span><span class="sxs-lookup"><span data-stu-id="aff50-110">The following example shows how to create a new entry in a zip archive from an existing file, and extract the contents of the archive to a directory.</span></span>

[!code-csharp[System.IO.Compression.ZipArchive#3](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program3.cs#3)]
[!code-vb[System.IO.Compression.ZipArchive#3](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program3.vb#3)]

<span data-ttu-id="aff50-111">下面的示例演示如何循环访问 zip 存档的内容并提取扩展名为 .txt 的文件。</span><span class="sxs-lookup"><span data-stu-id="aff50-111">The following example shows how to iterate through the contents of a zip archive and extract files that have a .txt extension.</span></span>

[!code-csharp[System.IO.Compression.ZipArchive#1](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]
  