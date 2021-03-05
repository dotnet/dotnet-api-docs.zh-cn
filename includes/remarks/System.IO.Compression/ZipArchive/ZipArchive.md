---
ms.openlocfilehash: 3e3bdbd22f3d20ce35972ff68a8d5ce7db7d53aa
ms.sourcegitcommit: 9f423345753728e8cad38d4a22663a109e69ea91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "102076764"
---
操作 zip 存档及其文件条目的方法分布于三个类： <xref:System.IO.Compression.ZipFile> 、 <xref:System.IO.Compression.ZipArchive> 和 <xref:System.IO.Compression.ZipArchiveEntry> 。

|功能|使用|
|--------|---------|
|从目录创建 zip 存档|<xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType>|
|将 zip 存档的内容提取到目录|<xref:System.IO.Compression.ZipFile.ExtractToDirectory%2A?displayProperty=nameWithType>|
|将新文件添加到现有 zip 存档|<xref:System.IO.Compression.ZipArchive.CreateEntry%2A?displayProperty=nameWithType>|
|从 zip 存档中检索文件|<xref:System.IO.Compression.ZipArchive.GetEntry%2A?displayProperty=nameWithType>|
|检索 zip 存档中的所有文件|<xref:System.IO.Compression.ZipArchive.Entries%2A?displayProperty=nameWithType>|
|打开 zip 存档中包含的单个文件的流|<xref:System.IO.Compression.ZipArchiveEntry.Open%2A?displayProperty=nameWithType>|
|删除 zip 存档中的文件|<xref:System.IO.Compression.ZipArchiveEntry.Delete%2A?displayProperty=nameWithType>|

当你创建新项时，该文件将被压缩并添加到 zip 包。 使用 <xref:System.IO.Compression.ZipArchive.CreateEntry%2A> 方法，可以在添加项时指定目录层次结构。 在 zip 包中包含新项的相对路径。 例如，使用相对路径创建新条目将 `AddedFolder\NewFile.txt` 在名为 AddedFolder 的目录中创建一个压缩的文本文件。

如果在 `System.IO.Compression.FileSystem` 项目中引用程序集，则可以从类的类) 访问四个扩展方法 (<xref:System.IO.Compression.ZipFileExtensions> <xref:System.IO.Compression.ZipArchive> ： <xref:System.IO.Compression.ZipFileExtensions.CreateEntryFromFile(System.IO.Compression.ZipArchive,System.String,System.String)> 、 <xref:System.IO.Compression.ZipFileExtensions.CreateEntryFromFile(System.IO.Compression.ZipArchive,System.String,System.String,System.IO.Compression.CompressionLevel)> 、 <xref:System.IO.Compression.ZipFileExtensions.ExtractToDirectory(System.IO.Compression.ZipArchive,System.String)> 和 <xref:System.IO.Compression.ZipFileExtensions.ExtractToDirectory(System.IO.Compression.ZipArchive,System.String,System.Boolean)> (，.net Core 2.0 和更高版本) 中提供了该方法。 使用这些扩展方法可以将项的内容压缩和解压缩到文件中。 此 `System.IO.Compression.FileSystem` 程序集不适用于 Windows 8.x 应用商店应用。 在 Windows 8.x 应用商店应用程序中，可以使用或类压缩和解压缩文件 <xref:System.IO.Compression.DeflateStream> <xref:System.IO.Compression.GZipStream> ，也可以使用 Windows 运行时类型的 [压缩](https://go.microsoft.com/fwlink/p/?LinkID=246357) 程序和 [解压缩](https://go.microsoft.com/fwlink/p/?LinkID=246358)程序。

## <a name="examples"></a>示例

第一个示例演示如何使用流创建新条目并写入该条目。

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

下面的示例演示如何打开 zip 存档并循环访问项的集合。

[!code-csharp[System.IO.Compression.ZipArchive#1](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

第三个示例演示如何使用扩展方法从现有文件在 zip 存档中创建新条目，并提取存档内容。 必须引用 `System.IO.Compression.FileSystem` 程序集才能执行此代码。

[!code-csharp[System.IO.Compression.ZipArchive#3](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program3.cs#3)]
[!code-vb[System.IO.Compression.ZipArchive#3](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program3.vb#3)]
