---
ms.openlocfilehash: 747e67ae17272e0f4118596bd0b9682caba10dbe
ms.sourcegitcommit: 9f423345753728e8cad38d4a22663a109e69ea91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "102091678"
---
当通过调用方法从现有文件创建新项时 <xref:System.IO.Compression.ZipFileExtensions.CreateEntryFromFile%2A> ，该项的属性将 <xref:System.IO.Compression.ZipArchiveEntry.LastWriteTime%2A> 自动设置为上次修改文件的时间。 当你通过调用方法以编程方式创建新项时 <xref:System.IO.Compression.ZipArchive.CreateEntry%2A> ， <xref:System.IO.Compression.ZipArchiveEntry.LastWriteTime%2A> 该项的属性将自动设置为执行时间。 如果你修改该条目，则必须显式设置 <xref:System.IO.Compression.ZipArchiveEntry.LastWriteTime%2A> 属性，前提是你希望该值反映最近更改的时间。

设置此属性时，该值将 <xref:System.DateTimeOffset> 转换为特定于 zip 存档的时间戳格式。 此格式支持两秒钟的解析。 最早允许的值为1980年1月 1 0:00:00 (午夜) 。 最新允许的值为 2107 12 月 31 23:59:58 () 午夜之前一秒钟。 如果上次写入时间的值无效，则属性将返回默认值1980年1月 1 0:00:00 (午夜) 。

## <a name="examples"></a>示例

下面的示例演示如何打开 zip 存档中的条目，对其进行修改，然后将 <xref:System.IO.Compression.ZipArchiveEntry.LastWriteTime%2A> 属性设置为当前时间。

[!code-csharp[System.IO.Compression.ZipArchiveEntry#2](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchiveentry/cs/program2.cs#2)]
[!code-vb[System.IO.Compression.ZipArchiveEntry#2](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchiveentry/vb/program2.vb#2)]
