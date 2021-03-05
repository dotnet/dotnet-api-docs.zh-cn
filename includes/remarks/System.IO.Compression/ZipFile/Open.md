---
ms.openlocfilehash: eb9dfd561a5d716c7f7b45fe4b31e9c1a9539dfa
ms.sourcegitcommit: 9f423345753728e8cad38d4a22663a109e69ea91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "102091548"
---
将参数设置为时，将以 `mode` <xref:System.IO.Compression.ZipArchiveMode.Read> <xref:System.IO.FileMode.Open?displayProperty=nameWithType> 文件模式值打开存档。 如果存档不存在，则 <xref:System.IO.FileNotFoundException> 会引发异常。 将 `mode` 参数设置为 <xref:System.IO.Compression.ZipArchiveMode.Read> 等效于调用 <xref:System.IO.Compression.ZipFile.OpenRead%2A> 方法。

将参数设置为时，将以 `mode` <xref:System.IO.Compression.ZipArchiveMode.Create> <xref:System.IO.FileMode.CreateNew?displayProperty=nameWithType> 文件模式值打开存档。 如果存档已存在， <xref:System.IO.IOException> 则会引发。

将参数设置为时，将以 `mode` <xref:System.IO.Compression.ZipArchiveMode.Update> <xref:System.IO.FileMode.OpenOrCreate?displayProperty=nameWithType> 文件模式值打开存档。 如果存档存在，则将其打开。 可以修改现有条目并创建新条目。 如果存档不存在，则创建新的存档;但是，在模式下创建 zip 存档 <xref:System.IO.Compression.ZipArchiveMode.Update> 并不像在模式中创建它那样高效 <xref:System.IO.Compression.ZipArchiveMode.Create> 。

当你打开要读取的 zip 存档文件并 `entryNameEncoding` 将设置为时 `null` ，将根据以下规则对条目名称进行解码：

-   如果未设置本地文件头的通用位标志 (的语言编码标记) 未设置，则使用当前系统默认代码页对项名称进行解码。

-   如果设置了语言编码标志，则使用 UTF-8 对条目名称进行解码。

当你打开 zip 存档文件以进行读取，并 `entryNameEncoding` 将设置为之外的值时 `null` ，将根据以下规则对条目名称进行解码：

-   如果未设置语言编码标志，则使用指定的 `entryNameEncoding` 对项名称进行解码。

-   如果设置了语言编码标志，则使用 UTF-8 对条目名称进行解码。

当你写入存档文件并且将 `entryNameEncoding` 设置为时 `null` ，将根据以下规则对条目名称进行编码：

-   对于包含 ASCII 范围外的字符的条目名称，设置语言编码标志，并使用 UTF-8 对条目名称进行编码。

-   对于仅包含 ASCII 字符的条目名称，未设置语言编码标志，并且通过使用当前系统默认代码页对条目名称进行编码。

当你写入存档文件并且 `entryNameEncoding` 将设置为之外的值时 `null` ，将使用指定的将 `entryNameEncoding` 输入名称编码为个字节。 仅当指定的编码为 UTF-8 编码时，才设置本地文件头) 的常规用途位标志 (的语言编码标志。
