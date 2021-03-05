---
ms.openlocfilehash: 961780639415afe5125b3effff236c1264ae4cd0
ms.sourcegitcommit: 9f423345753728e8cad38d4a22663a109e69ea91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "102091691"
---
Zip 存档包含每个压缩文件的条目。 <xref:System.IO.Compression.ZipArchiveEntry>利用类，您可以检查项的属性，打开或删除该项。 打开某个条目时，可以通过写入该压缩文件的流来修改压缩的文件。

用于处理 zip 存档及其文件条目的方法分布于三个类： <xref:System.IO.Compression.ZipFile> 、 <xref:System.IO.Compression.ZipArchive> 和 <xref:System.IO.Compression.ZipArchiveEntry> 。

|收件人...|使用...|
|---------|----------|
|从目录创建 zip 存档|<xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType>|
|将 zip 存档的内容提取到目录|<xref:System.IO.Compression.ZipFile.ExtractToDirectory%2A?displayProperty=nameWithType>|
|将新文件添加到现有 zip 存档|<xref:System.IO.Compression.ZipArchive.CreateEntry%2A?displayProperty=nameWithType>|
|在 zip 存档中检索文件|<xref:System.IO.Compression.ZipArchive.GetEntry%2A?displayProperty=nameWithType>|
|检索 zip 存档中的所有文件|<xref:System.IO.Compression.ZipArchive.Entries%2A?displayProperty=nameWithType>|
|打开 zip 存档中包含的单个文件的流|<xref:System.IO.Compression.ZipArchiveEntry.Open%2A?displayProperty=nameWithType>|
|删除 zip 存档中的文件|<xref:System.IO.Compression.ZipArchiveEntry.Delete%2A?displayProperty=nameWithType>|

如果在 `System.IO.Compression.FileSystem` 项目中引用程序集，则可以访问类的两个扩展方法 <xref:System.IO.Compression.ZipArchiveEntry> 。 这些方法是 <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%28System.IO.Compression.ZipArchiveEntry%2CSystem.String%29> 和 <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%28System.IO.Compression.ZipArchiveEntry%2CSystem.String%2CSystem.Boolean%29> ，它们使你能够将项的内容解压缩到文件中。 `System.IO.Compression.FileSystem`程序集在 Windows 8 中不可用。 在 Windows 8.x 应用商店应用程序中，可以使用或解压缩存档的内容 <xref:System.IO.Compression.DeflateStream> <xref:System.IO.Compression.GZipStream> ，也可以使用 Windows 运行时类型 [压缩程序](https://go.microsoft.com/fwlink/p/?LinkId=246357) 和 [解压缩](https://go.microsoft.com/fwlink/?LinkId=246358) 程序来压缩和解压缩文件。

## <a name="examples"></a>示例

第一个示例演示如何在 zip 存档中创建新项并对其进行写入。

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

第二个示例演示如何使用 <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%28System.IO.Compression.ZipArchiveEntry%2CSystem.String%29> 扩展方法。 `System.IO.Compression.FileSystem`若要执行代码，必须在项目中引用程序集。

[!code-csharp[System.IO.Compression.ZipArchive#1](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

