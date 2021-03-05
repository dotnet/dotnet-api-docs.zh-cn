---
ms.openlocfilehash: 31677a20dbf9105215f3fa34af79a809343d0b13
ms.sourcegitcommit: 9f423345753728e8cad38d4a22663a109e69ea91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "102091535"
---
> [!IMPORTANT]
>  若要使用 <xref:System.IO.Compression.ZipFile> 类，必须 `System.IO.Compression.FileSystem` 在项目中添加对程序集的引用; 否则，在尝试编译时将收到以下错误消息： **名称 "ZipFile" 在当前上下文中不存在**。 有关如何在 Visual Studio 中添加对项目的引用的详细信息，请参阅 [如何：使用引用管理器添加或删除引用](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager)。

操作 zip 存档及其文件的方法分布于三个类： <xref:System.IO.Compression.ZipFile> 、 <xref:System.IO.Compression.ZipArchive> 和 <xref:System.IO.Compression.ZipArchiveEntry> 。

|收件人...|使用...|
|---------|----------|
|从目录创建 zip 存档|<xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType>|
|将 zip 存档的内容提取到目录|<xref:System.IO.Compression.ZipFile.ExtractToDirectory%2A?displayProperty=nameWithType>|
|将新文件添加到现有 zip 存档|<xref:System.IO.Compression.ZipArchive.CreateEntry%2A?displayProperty=nameWithType>|
|在 zip 存档中检索文件|<xref:System.IO.Compression.ZipArchive.GetEntry%2A?displayProperty=nameWithType>|
|检索 zip 存档中的所有文件|<xref:System.IO.Compression.ZipArchive.Entries%2A?displayProperty=nameWithType>|
|打开 zip 存档中包含的单个文件的流|<xref:System.IO.Compression.ZipArchiveEntry.Open%2A?displayProperty=nameWithType>|
|删除 zip 存档中的文件|<xref:System.IO.Compression.ZipArchiveEntry.Delete%2A?displayProperty=nameWithType>|

不能在 <xref:System.IO.Compression.ZipFile> Windows 8.x  <xref:System.IO.Compression.ZipFileExtensions> 应用商店应用中使用或类。 在 Windows 8.x 应用商店应用中，你应使用以下类来处理压缩的文件。

-   <xref:System.IO.Compression.ZipArchive>

-   <xref:System.IO.Compression.ZipArchiveEntry>

-   <xref:System.IO.Compression.DeflateStream>

-   <xref:System.IO.Compression.GZipStream>

## <a name="examples"></a>示例

此示例演示如何使用类创建和提取 zip 存档 <xref:System.IO.Compression.ZipFile> 。 它将文件夹的内容压缩为 zip 存档，然后将该内容提取到新文件夹中。

> [!TIP]
>  若要使用 <xref:System.IO.Compression.ZipFile> 类，必须在项目中引用 `System.IO.Compression.FileSystem` 程序集。

[!code-csharp[System.IO.Compression.ZipFile#1](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]
