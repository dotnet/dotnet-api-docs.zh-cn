---
ms.openlocfilehash: b43d88a9e48278469fdc0c0d3422e91ae04dde28
ms.sourcegitcommit: 11d168140aa8fade0768c2a9dde3e3bcacfdfb7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "83888162"
---

<span data-ttu-id="461e1-101">但是，在调用 String.Format 方法时，不需要关注需要调用的特定重载\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="461e1-101">However, when calling the **String.Format** method, it is not necessary to focus on the particular overload that you want to call.</span></span> <span data-ttu-id="461e1-102">相反，可以借助包括一个或多个格式项的[复合格式字符串](/dotnet/standard/base-types/composite-formatting)调用方法。</span><span class="sxs-lookup"><span data-stu-id="461e1-102">Instead, you can call the method with a [composite format string](/dotnet/standard/base-types/composite-formatting) that includes one or more format items.</span></span> <span data-ttu-id="461e1-103">为每个格式项分配一个数字索引；第一个索引从 0 开始。</span><span class="sxs-lookup"><span data-stu-id="461e1-103">You assign each format item a numeric index; the first index starts at 0.</span></span> <span data-ttu-id="461e1-104">除了初始字符串，方法调用拥有的额外参数数应该与其拥有的索引值数相同。</span><span class="sxs-lookup"><span data-stu-id="461e1-104">In addition to the initial string, your method call should have as many additional arguments as it has index values.</span></span> <span data-ttu-id="461e1-105">例如，格式项有 0 和 1 两个索引的字符串应该有 2 个参数；索引为 0 到 5 的字符串应该有 6 个参数。</span><span class="sxs-lookup"><span data-stu-id="461e1-105">For example, a string whose format items have indexes of 0 and 1 should have 2 arguments; one with indexes 0 through 5 should have 6 arguments.</span></span> <span data-ttu-id="461e1-106">然后，你的语言编译器将会将方法调用解析为 String.Format 方法的特定重载\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="461e1-106">Your language compiler will then resolve your method call to a particular overload of the **String.Format** method.</span></span>   
 
<span data-ttu-id="461e1-107">有关使用 String.Format 方法的详细文档，请参阅 [String.Format 方法入门](#Starting)和[我调用哪个方法？](#FTaskList)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="461e1-107">For more detailed documentation on using the **String.Format** method, see [Getting started with the String.Format method](#Starting) and [Which method do I call?](#FTaskList).</span></span>    
