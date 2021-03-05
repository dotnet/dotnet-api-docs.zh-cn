---
ms.openlocfilehash: ae6b2daec9316401b06f01ceb8337ea76f8b3708
ms.sourcegitcommit: 9f423345753728e8cad38d4a22663a109e69ea91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "102091665"
---
<xref:System.IO.Compression.ZipArchiveEntry.FullName%2A>属性包含 zip 存档中某个条目的相对路径，包括子目录层次结构。  (相反， <xref:System.IO.Compression.ZipArchiveEntry.Name%2A> 属性仅包含条目的名称，不包括子目录层次结构。 ) 例如，如果使用方法在 zip 存档中创建两个条目， <xref:System.IO.Compression.ZipFileExtensions.CreateEntryFromFile%2A> 并提供 `NewEntry.txt` 作为第一个条目的名称，并且 `AddedFolder\\NewEntry.txt` 为第二个条目提供，则这两个条目都将包含 `NewEntry.txt` 在属性中 <xref:System.IO.Compression.ZipArchiveEntry.Name%2A> 。 第一项也包含 `NewEntry.txt` 在属性中 <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A> ，但第二个项将包含在 `AddedFolder\\NewEntry.txt` 属性中 <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A> 。

可以指定任意字符串作为条目的路径，包括指定无效路径和绝对路径的字符串。 因此， <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A> 属性可能包含格式不正确的值。 提取 zip 存档的内容时，无效路径或绝对路径可能会导致异常。

## <a name="examples"></a>示例

下面的示例演示如何循环访问 .zip 文件的内容，并提取包含 .txt 扩展名的文件。

[!code-csharp[System.IO.Compression.ZipArchive#1](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

