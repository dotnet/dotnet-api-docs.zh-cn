---
ms.openlocfilehash: e5842484d90338291971bc82d96bef912968ae4a
ms.sourcegitcommit: 9f423345753728e8cad38d4a22663a109e69ea91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "102090287"
---
此类表示 gzip 数据格式，该格式使用适用于无损文件压缩和解压缩的行业标准算法。 该格式包含用于检测数据损坏的循环冗余检查值。 Gzip 数据格式使用与类相同的算法 <xref:System.IO.Compression.DeflateStream> ，但可以对其进行扩展以使用其他压缩格式。 此格式可以通过专利未涵盖的方式随时实现。

从 .NET Framework 4.5 开始， <xref:System.IO.Compression.DeflateStream> 类使用 zlib 库进行压缩。 因此，它提供了更好的压缩算法，在大多数情况下，它比在早期版本的 .NET Framework 中提供的压缩文件更小。

<xref:System.IO.Compression.GZipStream>写入扩展名为 gz 的文件的压缩对象可使用许多常见的压缩工具进行解压缩; 但是，此类本质上不提供向 zip 存档添加文件或从中提取文件的功能。

和中的压缩 <xref:System.IO.Compression.DeflateStream> 功能 <xref:System.IO.Compression.GZipStream> 作为流公开。 数据逐字节读取，因此不能执行多个传递来确定压缩整个文件或大型数据块的最佳方法。 <xref:System.IO.Compression.DeflateStream>和 <xref:System.IO.Compression.GZipStream> 类最适用于未压缩的数据源。 如果源数据已压缩，使用这些类实际上可能会增加流的大小。

## <a name="examples"></a>示例

下面的示例演示如何使用 <xref:System.IO.Compression.GZipStream> 类压缩和解压缩文件的目录。

[!code-csharp[IO.Compression.GZip1#1](~/samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]
