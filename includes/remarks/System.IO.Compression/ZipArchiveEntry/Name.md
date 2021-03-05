---
ms.openlocfilehash: e6f92cfac11807977ea79667cf36d2105171a442
ms.sourcegitcommit: 9f423345753728e8cad38d4a22663a109e69ea91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "102091704"
---
<xref:System.IO.Compression.ZipArchiveEntry.Name%2A>属性包含 <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A> 属性中遵循最后一个目录分隔符 () 的部分 \\ ，不包括子目录层次结构。 例如，如果使用方法在 zip 存档中创建两个条目， <xref:System.IO.Compression.ZipFileExtensions.CreateEntryFromFile%2A> 并提供 `NewEntry.txt` 作为第一个条目的名称，并且为第二个条目提供名称 `AddedFolder\\NewEntry.txt` ，则这两个条目都将包含 `NewEntry.txt` 在 <xref:System.IO.Compression.ZipArchiveEntry.Name%2A> 属性中。 第一项也包含 `NewEntry.txt` 在属性中 <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A> ，但第二个项将包含在 `AddedFolder\\NewEntry.txt` 属性中 <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A> 。

## <a name="examples"></a>示例

下面的示例演示如何从 zip 存档中检索项并评估这些项的属性。 它使用 <xref:System.IO.Compression.ZipArchiveEntry.Name%2A> 属性显示项的名称，并使用 <xref:System.IO.Compression.ZipArchiveEntry.Length%2A> 和 <xref:System.IO.Compression.ZipArchiveEntry.CompressedLength%2A> 属性来计算文件的压缩量。

[!code-csharp[System.IO.Compression.ZipArchiveEntry#1](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchiveentry/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveEntry#1](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchiveentry/vb/program1.vb#1)]
