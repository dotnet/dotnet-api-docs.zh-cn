---
ms.openlocfilehash: fd9a2abd111e15ed5a779f889acde732fc3f4fd4
ms.sourcegitcommit: 9f423345753728e8cad38d4a22663a109e69ea91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "102084944"
---

<span data-ttu-id="97864-101">此类表示 Deflate 算法，它是一种用于无损文件压缩和解压缩的行业标准算法。</span><span class="sxs-lookup"><span data-stu-id="97864-101">This class represents the Deflate algorithm, which is an industry-standard algorithm for lossless file compression and decompression.</span></span> <span data-ttu-id="97864-102">从 .NET Framework 4.5 开始， <xref:System.IO.Compression.DeflateStream> 类使用 zlib 库。</span><span class="sxs-lookup"><span data-stu-id="97864-102">Starting with the .NET Framework 4.5, the <xref:System.IO.Compression.DeflateStream> class uses the zlib library.</span></span> <span data-ttu-id="97864-103">因此，它提供了更好的压缩算法，在大多数情况下，它比在早期版本的 .NET Framework 中提供的压缩文件更小。</span><span class="sxs-lookup"><span data-stu-id="97864-103">As a result, it provides a better compression algorithm and, in most cases, a smaller compressed file than it provides in earlier versions of the .NET Framework.</span></span>

<span data-ttu-id="97864-104">此类本质上不提供将文件添加到 zip 存档或从 zip 存档中提取文件的功能。</span><span class="sxs-lookup"><span data-stu-id="97864-104">This class does not inherently provide functionality for adding files to or extracting files from zip archives.</span></span> <span data-ttu-id="97864-105">若要使用 zip 存档，请使用 <xref:System.IO.Compression.ZipArchive> 和 <xref:System.IO.Compression.ZipArchiveEntry> 类。</span><span class="sxs-lookup"><span data-stu-id="97864-105">To work with zip archives, use the <xref:System.IO.Compression.ZipArchive> and the <xref:System.IO.Compression.ZipArchiveEntry> classes.</span></span>

<span data-ttu-id="97864-106"><xref:System.IO.Compression.DeflateStream>类使用与类使用的 gzip 数据格式相同的压缩算法 <xref:System.IO.Compression.GZipStream> 。</span><span class="sxs-lookup"><span data-stu-id="97864-106">The <xref:System.IO.Compression.DeflateStream> class uses the same compression algorithm as the gzip data format used by the <xref:System.IO.Compression.GZipStream> class.</span></span>

<span data-ttu-id="97864-107">和中的压缩 <xref:System.IO.Compression.DeflateStream> 功能 <xref:System.IO.Compression.GZipStream> 作为流公开。</span><span class="sxs-lookup"><span data-stu-id="97864-107">The compression functionality in <xref:System.IO.Compression.DeflateStream> and <xref:System.IO.Compression.GZipStream> is exposed as a stream.</span></span> <span data-ttu-id="97864-108">数据逐字节读取，因此不能执行多个传递来确定压缩整个文件或大型数据块的最佳方法。</span><span class="sxs-lookup"><span data-stu-id="97864-108">Data is read on a byte-by-byte basis, so it is not possible to perform multiple passes to determine the best method for compressing entire files or large blocks of data.</span></span> <span data-ttu-id="97864-109"><xref:System.IO.Compression.DeflateStream>和 <xref:System.IO.Compression.GZipStream> 类最适用于未压缩的数据源。</span><span class="sxs-lookup"><span data-stu-id="97864-109">The <xref:System.IO.Compression.DeflateStream> and <xref:System.IO.Compression.GZipStream> classes are best used on uncompressed sources of data.</span></span> <span data-ttu-id="97864-110">如果源数据已压缩，使用这些类实际上可能会增加流的大小。</span><span class="sxs-lookup"><span data-stu-id="97864-110">If the source data is already compressed, using these classes may actually increase the size of the stream.</span></span>

## <a name="examples"></a><span data-ttu-id="97864-111">示例</span><span class="sxs-lookup"><span data-stu-id="97864-111">Examples</span></span>

<span data-ttu-id="97864-112">下面的示例演示如何使用 <xref:System.IO.Compression.DeflateStream> 类压缩和解压缩文件的目录。</span><span class="sxs-lookup"><span data-stu-id="97864-112">The following example shows how to use the <xref:System.IO.Compression.DeflateStream> class to compress and decompress a directory of files.</span></span>

[!code-csharp[IO.Compression.Deflate1#1](~/samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.Deflate1/CS/deflatetest.cs#1)]
[!code-vb[IO.Compression.Deflate1#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.Deflate1/VB/deflatetest.vb#1)]
