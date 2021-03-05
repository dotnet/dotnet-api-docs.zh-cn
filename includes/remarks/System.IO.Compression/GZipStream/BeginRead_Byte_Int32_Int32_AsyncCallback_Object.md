---
ms.openlocfilehash: 94390ca654e3ae4476442a72c9c3b7d1aa35fe48
ms.sourcegitcommit: 9f423345753728e8cad38d4a22663a109e69ea91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "102090300"
---
<span data-ttu-id="dd0c3-101">从 .NET Framework 4.5 开始，可以使用方法执行异步读取操作 <xref:System.IO.Stream.ReadAsync%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-101">Starting with the .NET Framework 4.5, you can perform asynchronous read operations by using the <xref:System.IO.Stream.ReadAsync%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="dd0c3-102"><xref:System.IO.Compression.GZipStream.BeginRead%2A>.NET Framework 4.5 中仍提供了方法来支持旧代码，但你可以使用新的异步方法更轻松地实现异步 i/o 操作。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-102">The <xref:System.IO.Compression.GZipStream.BeginRead%2A> method is still available in .NET Framework 4.5 to support legacy code; however, you can implement asynchronous I/O operations more easily by using the new async methods.</span></span> <span data-ttu-id="dd0c3-103">有关详细信息，请参阅[异步文件 I/O](/dotnet/standard/io/asynchronous-file-i-o)。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-103">For more information, see [Asynchronous File I/O](/dotnet/standard/io/asynchronous-file-i-o).</span></span>

<span data-ttu-id="dd0c3-104">将 <xref:System.IAsyncResult> 返回值传递到 <xref:System.IO.Compression.GZipStream.EndRead%2A> 流的方法以确定读取的字节数，以及释放用于读取的操作系统资源。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-104">Pass the <xref:System.IAsyncResult> return value to the <xref:System.IO.Compression.GZipStream.EndRead%2A> method of the stream to determine how many bytes were read and to release operating system resources used for reading.</span></span> <span data-ttu-id="dd0c3-105">可以通过在传递给的回调中使用调用或的相同代码来执行此操作 <xref:System.IO.Compression.GZipStream.BeginRead%2A> <xref:System.IO.Compression.GZipStream.BeginRead%2A> 。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-105">You can do this either by using the same code that called <xref:System.IO.Compression.GZipStream.BeginRead%2A> or in a callback passed to <xref:System.IO.Compression.GZipStream.BeginRead%2A>.</span></span>

<span data-ttu-id="dd0c3-106">发出异步读取或写入操作时，将更新流中的当前位置，而不是在 i/o 操作完成时进行更新。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-106">The current position in the stream is updated when the asynchronous read or write is issued, not when the I/O operation completes.</span></span>

<span data-ttu-id="dd0c3-107">多个同时进行的异步请求会导致不确定请求完成顺序。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-107">Multiple simultaneous asynchronous requests render the request completion order uncertain.</span></span>

<span data-ttu-id="dd0c3-108">使用 <xref:System.IO.Compression.GZipStream.CanRead%2A> 属性可确定当前 <xref:System.IO.Compression.GZipStream> 对象是否支持读取。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-108">Use the <xref:System.IO.Compression.GZipStream.CanRead%2A> property to determine whether the current <xref:System.IO.Compression.GZipStream> object supports reading.</span></span>

<span data-ttu-id="dd0c3-109">如果流已关闭或传递的参数无效，则会立即从中引发异常 <xref:System.IO.Compression.GZipStream.BeginRead%2A> 。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-109">If a stream is closed or you pass an invalid argument, exceptions are thrown immediately from <xref:System.IO.Compression.GZipStream.BeginRead%2A>.</span></span> <span data-ttu-id="dd0c3-110">在异步读取请求期间发生的错误（例如，i/o 请求过程中的磁盘故障）将在线程池线程上发生，并在调用时引发异常 <xref:System.IO.Compression.GZipStream.EndRead%2A> 。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-110">Errors that occur during an asynchronous read request, such as a disk failure during the I/O request, occur on the thread pool thread and throw exceptions when calling <xref:System.IO.Compression.GZipStream.EndRead%2A>.</span></span>

## <a name="examples"></a><span data-ttu-id="dd0c3-111">示例</span><span class="sxs-lookup"><span data-stu-id="dd0c3-111">Examples</span></span>

<span data-ttu-id="dd0c3-112">下面的代码示例演示如何使用 <xref:System.IO.Compression.GZipStream> 类压缩和解压缩文件。</span><span class="sxs-lookup"><span data-stu-id="dd0c3-112">The following code example shows how to use the <xref:System.IO.Compression.GZipStream> class to compress and decompress a file.</span></span>

[!code-csharp[IO.Compression.GZip1#1](~/samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]
