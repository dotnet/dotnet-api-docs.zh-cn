---
ms.openlocfilehash: 1af9ce8cec811e07e0efaa475c002201530b8d7b
ms.sourcegitcommit: 9f423345753728e8cad38d4a22663a109e69ea91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "102091509"
---
<xref:System.IO.Compression.ZipFileExtensions>类只包含扩展和类的静态方法 <xref:System.IO.Compression.ZipArchive> <xref:System.IO.Compression.ZipArchiveEntry> 。 不创建类的实例 <xref:System.IO.Compression.ZipFileExtensions> ; 相反，您可以从或的实例使用这些方法 <xref:System.IO.Compression.ZipArchive> <xref:System.IO.Compression.ZipArchiveEntry> 。

若要使用扩展方法，必须 `System.IO.Compression.FileSystem` 在项目中引用程序集。 `System.IO.Compression.FileSystem`程序集在 Windows 8.x 应用商店应用中不可用。 因此， <xref:System.IO.Compression.ZipFileExtensions> 和 <xref:System.IO.Compression.ZipFile> 类 (在 `System.IO.Compression.FileSystem` 程序集) 中都不能在 Windows 8.x 应用商店应用中使用。 在 Windows 8.x 应用商店应用中，使用、、和中的方法来处理压缩的文件 <xref:System.IO.Compression.ZipArchive> <xref:System.IO.Compression.ZipArchiveEntry> <xref:System.IO.Compression.DeflateStream> <xref:System.IO.Compression.GZipStream> 。

<xref:System.IO.Compression.ZipFileExtensions>类包含四个扩展的方法 <xref:System.IO.Compression.ZipArchive> ：

-   <xref:System.IO.Compression.ZipFileExtensions.CreateEntryFromFile%28System.IO.Compression.ZipArchive%2CSystem.String%2CSystem.String%29>

-   <xref:System.IO.Compression.ZipFileExtensions.CreateEntryFromFile%28System.IO.Compression.ZipArchive%2CSystem.String%2CSystem.String%2CSystem.IO.Compression.CompressionLevel%29>

-   <xref:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%28System.IO.Compression.ZipArchive%2CSystem.String%29>

-   <xref:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%28System.IO.Compression.ZipArchive%2CSystem.String%2CSystem.Boolean%29>

<xref:System.IO.Compression.ZipFileExtensions>类包含两个扩展的方法 <xref:System.IO.Compression.ZipArchiveEntry> ：

-   <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%28System.IO.Compression.ZipArchiveEntry%2CSystem.String%29>

-   <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%28System.IO.Compression.ZipArchiveEntry%2CSystem.String%2CSystem.Boolean%29>

## <a name="examples"></a>示例

下面的示例演示如何从现有文件在 zip 存档中创建新条目，并将存档内容提取到目录中。

[!code-csharp[System.IO.Compression.ZipArchive#3](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program3.cs#3)]
[!code-vb[System.IO.Compression.ZipArchive#3](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program3.vb#3)]

下面的示例演示如何循环访问 zip 存档的内容并提取扩展名为 .txt 的文件。

[!code-csharp[System.IO.Compression.ZipArchive#1](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]
  