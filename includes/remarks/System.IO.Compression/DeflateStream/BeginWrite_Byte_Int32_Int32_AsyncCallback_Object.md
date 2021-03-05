---
ms.openlocfilehash: 53607fe7d1d4c5b6ff109575d13c4058d3b2bc1f
ms.sourcegitcommit: 9f423345753728e8cad38d4a22663a109e69ea91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "102084866"
---
从 .NET Framework 4.5 开始，可以使用方法执行异步写入操作 <xref:System.IO.Stream.WriteAsync%2A> 。 <xref:System.IO.Compression.DeflateStream.BeginWrite%2A>方法在 .NET Framework 4.5 中仍可用以支持旧代码，但你可以使用新的异步方法更轻松地实现异步 i/o 操作。 有关详细信息，请参阅[异步文件 I/O](/dotnet/standard/io/asynchronous-file-i-o)。

将 <xref:System.IAsyncResult> 当前方法返回的对象传递给 <xref:System.IO.Compression.DeflateStream.EndWrite%2A> ，以确保写入完成并适当释放资源。 可以通过在传递给的回调中使用调用或的相同代码来执行此操作 <xref:System.IO.Compression.DeflateStream.BeginWrite%2A> <xref:System.IO.Compression.DeflateStream.BeginWrite%2A> 。 如果在异步写入操作过程中发生错误，则在 <xref:System.IO.Compression.DeflateStream.EndWrite%2A> 使用此方法返回的调用之前，将不会引发异常 <xref:System.IAsyncResult> 。

如果流可写，则在流的末尾写入会扩展流。

发出异步读取或写入操作时，将更新流中的当前位置，而不是在 i/o 操作完成时进行更新。 多个同时进行的异步请求会导致不确定请求完成顺序。

使用 <xref:System.IO.Compression.DeflateStream.CanWrite%2A> 属性可确定当前 <xref:System.IO.Compression.DeflateStream> 对象是否支持写入。

如果流已关闭或传递的参数无效，则会立即从中引发异常 <xref:System.IO.Compression.DeflateStream.BeginWrite%2A> 。 在异步写入请求期间发生的错误（例如，i/o 请求过程中的磁盘故障）将在线程池线程上发生，并在调用时引发异常 <xref:System.IO.Compression.DeflateStream.EndWrite%2A> 。
