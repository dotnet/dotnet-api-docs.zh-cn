---
ms.openlocfilehash: e5842484d90338291971bc82d96bef912968ae4a
ms.sourcegitcommit: 9f423345753728e8cad38d4a22663a109e69ea91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "102090287"
---
<span data-ttu-id="0b14c-101">此类表示 gzip 数据格式，该格式使用适用于无损文件压缩和解压缩的行业标准算法。</span><span class="sxs-lookup"><span data-stu-id="0b14c-101">This class represents the gzip data format, which uses an industry-standard algorithm for lossless file compression and decompression.</span></span> <span data-ttu-id="0b14c-102">该格式包含用于检测数据损坏的循环冗余检查值。</span><span class="sxs-lookup"><span data-stu-id="0b14c-102">The format includes a cyclic redundancy check value for detecting data corruption.</span></span> <span data-ttu-id="0b14c-103">Gzip 数据格式使用与类相同的算法 <xref:System.IO.Compression.DeflateStream> ，但可以对其进行扩展以使用其他压缩格式。</span><span class="sxs-lookup"><span data-stu-id="0b14c-103">The gzip data format uses the same algorithm as the <xref:System.IO.Compression.DeflateStream> class, but can be extended to use other compression formats.</span></span> <span data-ttu-id="0b14c-104">此格式可以通过专利未涵盖的方式随时实现。</span><span class="sxs-lookup"><span data-stu-id="0b14c-104">The format can be readily implemented in a manner not covered by patents.</span></span>

<span data-ttu-id="0b14c-105">从 .NET Framework 4.5 开始， <xref:System.IO.Compression.DeflateStream> 类使用 zlib 库进行压缩。</span><span class="sxs-lookup"><span data-stu-id="0b14c-105">Starting with the .NET Framework 4.5, the <xref:System.IO.Compression.DeflateStream> class uses the zlib library for compression.</span></span> <span data-ttu-id="0b14c-106">因此，它提供了更好的压缩算法，在大多数情况下，它比在早期版本的 .NET Framework 中提供的压缩文件更小。</span><span class="sxs-lookup"><span data-stu-id="0b14c-106">As a result, it provides a better compression algorithm and, in most cases, a smaller compressed file than it provides in earlier versions of the .NET Framework.</span></span>

<span data-ttu-id="0b14c-107"><xref:System.IO.Compression.GZipStream>写入扩展名为 gz 的文件的压缩对象可使用许多常见的压缩工具进行解压缩; 但是，此类本质上不提供向 zip 存档添加文件或从中提取文件的功能。</span><span class="sxs-lookup"><span data-stu-id="0b14c-107">Compressed <xref:System.IO.Compression.GZipStream> objects written to a file with an extension of .gz can be decompressed using many common compression tools; however, this class does not inherently provide functionality for adding files to or extracting files from zip archives.</span></span>

<span data-ttu-id="0b14c-108">和中的压缩 <xref:System.IO.Compression.DeflateStream> 功能 <xref:System.IO.Compression.GZipStream> 作为流公开。</span><span class="sxs-lookup"><span data-stu-id="0b14c-108">The compression functionality in <xref:System.IO.Compression.DeflateStream> and <xref:System.IO.Compression.GZipStream> is exposed as a stream.</span></span> <span data-ttu-id="0b14c-109">数据逐字节读取，因此不能执行多个传递来确定压缩整个文件或大型数据块的最佳方法。</span><span class="sxs-lookup"><span data-stu-id="0b14c-109">Data is read on a byte-by-byte basis, so it is not possible to perform multiple passes to determine the best method for compressing entire files or large blocks of data.</span></span> <span data-ttu-id="0b14c-110"><xref:System.IO.Compression.DeflateStream>和 <xref:System.IO.Compression.GZipStream> 类最适用于未压缩的数据源。</span><span class="sxs-lookup"><span data-stu-id="0b14c-110">The <xref:System.IO.Compression.DeflateStream> and <xref:System.IO.Compression.GZipStream> classes are best used on uncompressed sources of data.</span></span> <span data-ttu-id="0b14c-111">如果源数据已压缩，使用这些类实际上可能会增加流的大小。</span><span class="sxs-lookup"><span data-stu-id="0b14c-111">If the source data is already compressed, using these classes may actually increase the size of the stream.</span></span>

## <a name="examples"></a><span data-ttu-id="0b14c-112">示例</span><span class="sxs-lookup"><span data-stu-id="0b14c-112">Examples</span></span>

<span data-ttu-id="0b14c-113">下面的示例演示如何使用 <xref:System.IO.Compression.GZipStream> 类压缩和解压缩文件的目录。</span><span class="sxs-lookup"><span data-stu-id="0b14c-113">The following example shows how to use the <xref:System.IO.Compression.GZipStream> class to compress and decompress a directory of files.</span></span>

[!code-csharp[IO.Compression.GZip1#1](~/samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]
