---
ms.openlocfilehash: c28e3f97e02079905d591a7f27dc8d68d603c0bf
ms.sourcegitcommit: 02dd069b9696eb4eee675b6541f86b2602076448
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "92325017"
---
<span data-ttu-id="18dd0-101">反斜杠 (\\) 是互斥体名称中的保留字符。</span><span class="sxs-lookup"><span data-stu-id="18dd0-101">The backslash (\\) is a reserved character in a mutex name.</span></span> <span data-ttu-id="18dd0-102">请勿在互斥体名称中使用反斜杠 (\\)，除非在终端服务器会话中使用互斥体的注释中另有规定。</span><span class="sxs-lookup"><span data-stu-id="18dd0-102">Don't use a backslash (\\) in a mutex name except as specified in the note on using mutexes in terminal server sessions.</span></span> <span data-ttu-id="18dd0-103">否则，即使互斥体的名称表示现有文件，也可能引发 <xref:System.IO.DirectoryNotFoundException>。</span><span class="sxs-lookup"><span data-stu-id="18dd0-103">Otherwise, a <xref:System.IO.DirectoryNotFoundException> may be thrown, even though the name of the mutex represents an existing file.</span></span>
