---
ms.openlocfilehash: fd9a2abd111e15ed5a779f889acde732fc3f4fd4
ms.sourcegitcommit: 9f423345753728e8cad38d4a22663a109e69ea91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "102084944"
---

此类表示 Deflate 算法，它是一种用于无损文件压缩和解压缩的行业标准算法。 从 .NET Framework 4.5 开始， <xref:System.IO.Compression.DeflateStream> 类使用 zlib 库。 因此，它提供了更好的压缩算法，在大多数情况下，它比在早期版本的 .NET Framework 中提供的压缩文件更小。

此类本质上不提供将文件添加到 zip 存档或从 zip 存档中提取文件的功能。 若要使用 zip 存档，请使用 <xref:System.IO.Compression.ZipArchive> 和 <xref:System.IO.Compression.ZipArchiveEntry> 类。

<xref:System.IO.Compression.DeflateStream>类使用与类使用的 gzip 数据格式相同的压缩算法 <xref:System.IO.Compression.GZipStream> 。

和中的压缩 <xref:System.IO.Compression.DeflateStream> 功能 <xref:System.IO.Compression.GZipStream> 作为流公开。 数据逐字节读取，因此不能执行多个传递来确定压缩整个文件或大型数据块的最佳方法。 <xref:System.IO.Compression.DeflateStream>和 <xref:System.IO.Compression.GZipStream> 类最适用于未压缩的数据源。 如果源数据已压缩，使用这些类实际上可能会增加流的大小。

## <a name="examples"></a>示例

下面的示例演示如何使用 <xref:System.IO.Compression.DeflateStream> 类压缩和解压缩文件的目录。

[!code-csharp[IO.Compression.Deflate1#1](~/samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.Deflate1/CS/deflatetest.cs#1)]
[!code-vb[IO.Compression.Deflate1#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.Deflate1/VB/deflatetest.vb#1)]
