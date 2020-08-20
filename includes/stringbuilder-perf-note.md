---
ms.openlocfilehash: 903ac4ecb57e3a8e02a4f65ecfa6f9e77a552f45
ms.sourcegitcommit: 5ef0d02cb57c7153fd9d5417cdcad45665af832e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2019
ms.locfileid: "71139676"
---
<span data-ttu-id="85367-101">在以下情况下，通过 <xref:System.Text.StringBuilder.Chars%2A> 属性使用基于字符的索引可能会非常缓慢：</span><span class="sxs-lookup"><span data-stu-id="85367-101">Using character-based indexing with the <xref:System.Text.StringBuilder.Chars%2A> property can be extremely slow under the following conditions:</span></span>

- <span data-ttu-id="85367-102"><xref:System.Text.StringBuilder> 实例很大（例如，它由数以万计的字符组成）。</span><span class="sxs-lookup"><span data-stu-id="85367-102">The <xref:System.Text.StringBuilder> instance is large (for example, it consists of several tens of thousands of characters).</span></span>
- <span data-ttu-id="85367-103"><xref:System.Text.StringBuilder>“比较笨重”。</span><span class="sxs-lookup"><span data-stu-id="85367-103">The <xref:System.Text.StringBuilder> is "chunky."</span></span> <span data-ttu-id="85367-104">即，对方法（例如 <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>）的重复调用会自动扩展对象的 <xref:System.Text.StringBuilder.Capacity%2A?displayProperty=nameWithType> 属性并为其分配新的内存区块。</span><span class="sxs-lookup"><span data-stu-id="85367-104">That is, repeated calls to methods such as <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> have automatically expanded the object's <xref:System.Text.StringBuilder.Capacity%2A?displayProperty=nameWithType> property and allocated new chunks of memory to it.</span></span>

<span data-ttu-id="85367-105">因为每次字符访问都会遍历区块的整个链接列表以查找要索引到的正确缓冲区，所以性能受到严重影响。</span><span class="sxs-lookup"><span data-stu-id="85367-105">Performance is severely impacted because each character access walks the entire linked list of chunks to find the correct buffer to index into.</span></span>

> [!NOTE]
>  <span data-ttu-id="85367-106">即使对于大型“笨重的”<xref:System.Text.StringBuilder> 对象，使用 <xref:System.Text.StringBuilder.Chars%2A> 属性对一个或少量字符进行基于索引的访问几乎不影响性能；一般情况下，它是 0(n) 操作\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="85367-106">Even for a large "chunky" <xref:System.Text.StringBuilder> object, using the <xref:System.Text.StringBuilder.Chars%2A> property for index-based access to one or a small number of characters has a negligible performance impact; typically, it is an **0(n)** operation.</span></span> <span data-ttu-id="85367-107">当迭代 <xref:System.Text.StringBuilder> 对象中的字符时，会对性能造成显著的影响，这是 O(n^2) 操作\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="85367-107">The significant performance impact occurs when iterating the characters in the <xref:System.Text.StringBuilder> object, which is an **O(n^2)** operation.</span></span> 

<span data-ttu-id="85367-108">如果通过 <xref:System.Text.StringBuilder> 对象在使用基于字符的索引时遇到性能问题，可以使用以下任一解决方法：</span><span class="sxs-lookup"><span data-stu-id="85367-108">If you encounter performance issues when using character-based indexing with <xref:System.Text.StringBuilder> objects, you can use any of the following workarounds:</span></span>

- <span data-ttu-id="85367-109">通过调用 <xref:System.Text.StringBuilder.ToString%2A> 方法，将 <xref:System.Text.StringBuilder> 实例转换为 <xref:System.String>，然后访问字符串中的字符。</span><span class="sxs-lookup"><span data-stu-id="85367-109">Convert the <xref:System.Text.StringBuilder> instance to a <xref:System.String> by calling the <xref:System.Text.StringBuilder.ToString%2A> method, then access the characters in the string.</span></span>

- <span data-ttu-id="85367-110">将现有的 <xref:System.Text.StringBuilder> 对象的内容复制到新的预调整大小的 <xref:System.Text.StringBuilder> 对象。</span><span class="sxs-lookup"><span data-stu-id="85367-110">Copy the contents of the existing <xref:System.Text.StringBuilder> object to a new pre-sized <xref:System.Text.StringBuilder> object.</span></span> <span data-ttu-id="85367-111">由于新的 <xref:System.Text.StringBuilder> 对象并不笨重，因此可以提升性能。</span><span class="sxs-lookup"><span data-stu-id="85367-111">Performance improves because the new <xref:System.Text.StringBuilder> object is not chunky.</span></span> <span data-ttu-id="85367-112">例如：</span><span class="sxs-lookup"><span data-stu-id="85367-112">For example:</span></span>

   ```csharp
   // sbOriginal is the existing StringBuilder object
   var sbNew = new StringBuilder(sbOriginal.ToString(), sbOriginal.Length);
   ```
   ```vb
   ' sbOriginal is the existing StringBuilder object
   Dim sbNew = New StringBuilder(sbOriginal.ToString(), sbOriginal.Length)
   ```
- <span data-ttu-id="85367-113">通过调用 <xref:System.Text.StringBuilder.%23ctor(System.Int32)> 构造函数，将 <xref:System.Text.StringBuilder> 对象的初始容量设置为约等于其最大预期大小的值。</span><span class="sxs-lookup"><span data-stu-id="85367-113">Set the initial capacity of the <xref:System.Text.StringBuilder> object to a value that is approximately equal to its maximum expected size by calling the <xref:System.Text.StringBuilder.%23ctor(System.Int32)> constructor.</span></span> <span data-ttu-id="85367-114">请注意，即使 <xref:System.Text.StringBuilder> 很少达到其最大容量，它仍会分配整个内存块。</span><span class="sxs-lookup"><span data-stu-id="85367-114">Note that this allocates the entire block of memory even if the <xref:System.Text.StringBuilder> rarely reaches its maximum capacity.</span></span>
