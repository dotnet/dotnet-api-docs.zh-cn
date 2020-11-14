---
ms.openlocfilehash: 903ac4ecb57e3a8e02a4f65ecfa6f9e77a552f45
ms.sourcegitcommit: 02dd069b9696eb4eee675b6541f86b2602076448
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "92324610"
---
在以下情况下，通过 <xref:System.Text.StringBuilder.Chars%2A> 属性使用基于字符的索引可能会非常缓慢：

- <xref:System.Text.StringBuilder> 实例很大（例如，它由数以万计的字符组成）。
- <xref:System.Text.StringBuilder>“比较笨重”。 即，对方法（例如 <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>）的重复调用会自动扩展对象的 <xref:System.Text.StringBuilder.Capacity%2A?displayProperty=nameWithType> 属性并为其分配新的内存区块。

因为每次字符访问都会遍历区块的整个链接列表以查找要索引到的正确缓冲区，所以性能受到严重影响。

> [!NOTE]
>  即使对于大型“笨重的”<xref:System.Text.StringBuilder> 对象，使用 <xref:System.Text.StringBuilder.Chars%2A> 属性对一个或少量字符进行基于索引的访问几乎不影响性能；一般情况下，它是 0(n) 操作。 当迭代 <xref:System.Text.StringBuilder> 对象中的字符时，会对性能造成显著的影响，这是 O(n^2) 操作。 

如果通过 <xref:System.Text.StringBuilder> 对象在使用基于字符的索引时遇到性能问题，可以使用以下任一解决方法：

- 通过调用 <xref:System.Text.StringBuilder.ToString%2A> 方法，将 <xref:System.Text.StringBuilder> 实例转换为 <xref:System.String>，然后访问字符串中的字符。

- 将现有的 <xref:System.Text.StringBuilder> 对象的内容复制到新的预调整大小的 <xref:System.Text.StringBuilder> 对象。 由于新的 <xref:System.Text.StringBuilder> 对象并不笨重，因此可以提升性能。 例如：

   ```csharp
   // sbOriginal is the existing StringBuilder object
   var sbNew = new StringBuilder(sbOriginal.ToString(), sbOriginal.Length);
   ```
   ```vb
   ' sbOriginal is the existing StringBuilder object
   Dim sbNew = New StringBuilder(sbOriginal.ToString(), sbOriginal.Length)
   ```
- 通过调用 <xref:System.Text.StringBuilder.%23ctor(System.Int32)> 构造函数，将 <xref:System.Text.StringBuilder> 对象的初始容量设置为约等于其最大预期大小的值。 请注意，即使 <xref:System.Text.StringBuilder> 很少达到其最大容量，它仍会分配整个内存块。
