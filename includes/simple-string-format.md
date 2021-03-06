---
ms.openlocfilehash: b43d88a9e48278469fdc0c0d3422e91ae04dde28
ms.sourcegitcommit: 11d168140aa8fade0768c2a9dde3e3bcacfdfb7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "83888162"
---

但是，在调用 String.Format 方法时，不需要关注需要调用的特定重载。 相反，可以借助包括一个或多个格式项的[复合格式字符串](/dotnet/standard/base-types/composite-formatting)调用方法。 为每个格式项分配一个数字索引；第一个索引从 0 开始。 除了初始字符串，方法调用拥有的额外参数数应该与其拥有的索引值数相同。 例如，格式项有 0 和 1 两个索引的字符串应该有 2 个参数；索引为 0 到 5 的字符串应该有 6 个参数。 然后，你的语言编译器将会将方法调用解析为 String.Format 方法的特定重载。   
 
有关使用 String.Format 方法的详细文档，请参阅 [String.Format 方法入门](#Starting)和[我调用哪个方法？](#FTaskList)。    
