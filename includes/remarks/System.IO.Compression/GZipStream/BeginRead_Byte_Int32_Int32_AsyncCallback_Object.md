---
ms.openlocfilehash: 94390ca654e3ae4476442a72c9c3b7d1aa35fe48
ms.sourcegitcommit: 9f423345753728e8cad38d4a22663a109e69ea91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "102090300"
---
从 .NET Framework 4.5 开始，可以使用方法执行异步读取操作 <xref:System.IO.Stream.ReadAsync%2A?displayProperty=nameWithType> 。 <xref:System.IO.Compression.GZipStream.BeginRead%2A>.NET Framework 4.5 中仍提供了方法来支持旧代码，但你可以使用新的异步方法更轻松地实现异步 i/o 操作。 有关详细信息，请参阅[异步文件 I/O](/dotnet/standard/io/asynchronous-file-i-o)。

将 <xref:System.IAsyncResult> 返回值传递到 <xref:System.IO.Compression.GZipStream.EndRead%2A> 流的方法以确定读取的字节数，以及释放用于读取的操作系统资源。 可以通过在传递给的回调中使用调用或的相同代码来执行此操作 <xref:System.IO.Compression.GZipStream.BeginRead%2A> <xref:System.IO.Compression.GZipStream.BeginRead%2A> 。

发出异步读取或写入操作时，将更新流中的当前位置，而不是在 i/o 操作完成时进行更新。

多个同时进行的异步请求会导致不确定请求完成顺序。

使用 <xref:System.IO.Compression.GZipStream.CanRead%2A> 属性可确定当前 <xref:System.IO.Compression.GZipStream> 对象是否支持读取。

如果流已关闭或传递的参数无效，则会立即从中引发异常 <xref:System.IO.Compression.GZipStream.BeginRead%2A> 。 在异步读取请求期间发生的错误（例如，i/o 请求过程中的磁盘故障）将在线程池线程上发生，并在调用时引发异常 <xref:System.IO.Compression.GZipStream.EndRead%2A> 。

## <a name="examples"></a>示例

下面的代码示例演示如何使用 <xref:System.IO.Compression.GZipStream> 类压缩和解压缩文件。

[!code-csharp[IO.Compression.GZip1#1](~/samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]
