---
ms.openlocfilehash: 31677a20dbf9105215f3fa34af79a809343d0b13
ms.sourcegitcommit: 9f423345753728e8cad38d4a22663a109e69ea91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "102091535"
---
> [!IMPORTANT]
>  <span data-ttu-id="dd1ba-101">若要使用 <xref:System.IO.Compression.ZipFile> 类，必须 `System.IO.Compression.FileSystem` 在项目中添加对程序集的引用; 否则，在尝试编译时将收到以下错误消息： **名称 "ZipFile" 在当前上下文中不存在**。</span><span class="sxs-lookup"><span data-stu-id="dd1ba-101">To use the <xref:System.IO.Compression.ZipFile> class, you must add a reference to the `System.IO.Compression.FileSystem` assembly in your project; otherwise, you'll get the following error message when trying to compile : **The name 'ZipFile' does not exist in the current context**.</span></span> <span data-ttu-id="dd1ba-102">有关如何在 Visual Studio 中添加对项目的引用的详细信息，请参阅 [如何：使用引用管理器添加或删除引用](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager)。</span><span class="sxs-lookup"><span data-stu-id="dd1ba-102">For more information on how to add a reference to your project in Visual Studio, see [How to: Add or Remove References By Using the Reference Manager](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).</span></span>

<span data-ttu-id="dd1ba-103">操作 zip 存档及其文件的方法分布于三个类： <xref:System.IO.Compression.ZipFile> 、 <xref:System.IO.Compression.ZipArchive> 和 <xref:System.IO.Compression.ZipArchiveEntry> 。</span><span class="sxs-lookup"><span data-stu-id="dd1ba-103">The methods for manipulating zip archives and their files are spread across three classes: <xref:System.IO.Compression.ZipFile>, <xref:System.IO.Compression.ZipArchive> and <xref:System.IO.Compression.ZipArchiveEntry>.</span></span>

|<span data-ttu-id="dd1ba-104">收件人...</span><span class="sxs-lookup"><span data-stu-id="dd1ba-104">To...</span></span>|<span data-ttu-id="dd1ba-105">使用...</span><span class="sxs-lookup"><span data-stu-id="dd1ba-105">Use...</span></span>|
|---------|----------|
|<span data-ttu-id="dd1ba-106">从目录创建 zip 存档</span><span class="sxs-lookup"><span data-stu-id="dd1ba-106">Create a zip archive from a directory</span></span>|<xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType>|
|<span data-ttu-id="dd1ba-107">将 zip 存档的内容提取到目录</span><span class="sxs-lookup"><span data-stu-id="dd1ba-107">Extract the contents of a zip archive to a directory</span></span>|<xref:System.IO.Compression.ZipFile.ExtractToDirectory%2A?displayProperty=nameWithType>|
|<span data-ttu-id="dd1ba-108">将新文件添加到现有 zip 存档</span><span class="sxs-lookup"><span data-stu-id="dd1ba-108">Add new files to an existing zip archive</span></span>|<xref:System.IO.Compression.ZipArchive.CreateEntry%2A?displayProperty=nameWithType>|
|<span data-ttu-id="dd1ba-109">在 zip 存档中检索文件</span><span class="sxs-lookup"><span data-stu-id="dd1ba-109">Retrieve a file in a zip archive</span></span>|<xref:System.IO.Compression.ZipArchive.GetEntry%2A?displayProperty=nameWithType>|
|<span data-ttu-id="dd1ba-110">检索 zip 存档中的所有文件</span><span class="sxs-lookup"><span data-stu-id="dd1ba-110">Retrieve all of the files in a zip archive</span></span>|<xref:System.IO.Compression.ZipArchive.Entries%2A?displayProperty=nameWithType>|
|<span data-ttu-id="dd1ba-111">打开 zip 存档中包含的单个文件的流</span><span class="sxs-lookup"><span data-stu-id="dd1ba-111">To open a stream to an individual file contained in a zip archive</span></span>|<xref:System.IO.Compression.ZipArchiveEntry.Open%2A?displayProperty=nameWithType>|
|<span data-ttu-id="dd1ba-112">删除 zip 存档中的文件</span><span class="sxs-lookup"><span data-stu-id="dd1ba-112">Delete a file from a zip archive</span></span>|<xref:System.IO.Compression.ZipArchiveEntry.Delete%2A?displayProperty=nameWithType>|

<span data-ttu-id="dd1ba-113">不能在 <xref:System.IO.Compression.ZipFile> Windows 8.x  <xref:System.IO.Compression.ZipFileExtensions> 应用商店应用中使用或类。</span><span class="sxs-lookup"><span data-stu-id="dd1ba-113">You cannot use the <xref:System.IO.Compression.ZipFile> or  <xref:System.IO.Compression.ZipFileExtensions> classes  in Windows 8.x Store apps.</span></span> <span data-ttu-id="dd1ba-114">在 Windows 8.x 应用商店应用中，你应使用以下类来处理压缩的文件。</span><span class="sxs-lookup"><span data-stu-id="dd1ba-114">In Windows 8.x Store apps, you should use the following classes to work with compressed files.</span></span>

-   <xref:System.IO.Compression.ZipArchive>

-   <xref:System.IO.Compression.ZipArchiveEntry>

-   <xref:System.IO.Compression.DeflateStream>

-   <xref:System.IO.Compression.GZipStream>

## <a name="examples"></a><span data-ttu-id="dd1ba-115">示例</span><span class="sxs-lookup"><span data-stu-id="dd1ba-115">Examples</span></span>

<span data-ttu-id="dd1ba-116">此示例演示如何使用类创建和提取 zip 存档 <xref:System.IO.Compression.ZipFile> 。</span><span class="sxs-lookup"><span data-stu-id="dd1ba-116">This example shows how to create and extract a zip archive by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="dd1ba-117">它将文件夹的内容压缩为 zip 存档，然后将该内容提取到新文件夹中。</span><span class="sxs-lookup"><span data-stu-id="dd1ba-117">It compresses the contents of a folder into a zip archive, and then extracts that content to a new folder.</span></span>

> [!TIP]
>  <span data-ttu-id="dd1ba-118">若要使用 <xref:System.IO.Compression.ZipFile> 类，必须在项目中引用 `System.IO.Compression.FileSystem` 程序集。</span><span class="sxs-lookup"><span data-stu-id="dd1ba-118">To use the <xref:System.IO.Compression.ZipFile> class, you must reference the `System.IO.Compression.FileSystem` assembly in your project.</span></span>

[!code-csharp[System.IO.Compression.ZipFile#1](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]
