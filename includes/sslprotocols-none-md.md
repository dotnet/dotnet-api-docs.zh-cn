---
ms.openlocfilehash: 733bfb4740f3f274ba9ebb396749d313907d5fa6
ms.sourcegitcommit: 5ef0d02cb57c7153fd9d5417cdcad45665af832e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2019
ms.locfileid: "71139696"
---
<span data-ttu-id="930a8-101">从 .NET Framework 4.7 开始，此方法使用 <xref:System.Security.Authentication.SslProtocols.None> 进行身份验证，这允许操作系统选择要使用的最佳协议，并将其用于阻止不安全的协议。</span><span class="sxs-lookup"><span data-stu-id="930a8-101">Starting with .NET Framework 4.7, this method authenticates using <xref:System.Security.Authentication.SslProtocols.None>, which allows the operating system to choose the best protocol to use, and to block protocols that are not secure.</span></span> <span data-ttu-id="930a8-102">在 .NET Framework 4.6（以及安装了最新安全修补程序的 .NET Framework 4.5）中，允许的 TLS/SSL 协议版本为 1.2、1.1 和 1.0（除非通过编辑 Windows 注册表禁用强加密）。</span><span class="sxs-lookup"><span data-stu-id="930a8-102">In .NET Framework 4.6 (and .NET Framework 4.5 with the latest security patches installed), the allowed TLS/SSL protocols versions are 1.2, 1.1, and 1.0 (unless you disable strong cryptography by editing the Windows Registry).</span></span>
