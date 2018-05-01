### <a name="marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a><span data-ttu-id="8fb2c-101">Marshal.SizeOf- und Marshal.PtrToStructure-Überladungen führen bei dynamischem Code zu Fehlern</span><span class="sxs-lookup"><span data-stu-id="8fb2c-101">Marshal.SizeOf and Marshal.PtrToStructure overloads break dynamic code</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8fb2c-102">Details</span><span class="sxs-lookup"><span data-stu-id="8fb2c-102">Details</span></span>|<span data-ttu-id="8fb2c-103">Ab .NET Framework 4.5.1 kann das dynamische Binden an die Methoden <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601>, <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601(%60%600)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Object)>,<xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Type)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr)> oder <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr,%60%600)> (z.B. über Windows PowerShell, IronPython oder das C#-Schlüsselwort „dynamic“) zu <code>MethodInvocationExceptions</code> führen, da neue Überladungen dieser Methoden hinzugefügt wurden, die für die Skript-Engines möglicherweise mehrdeutig sind.</span><span class="sxs-lookup"><span data-stu-id="8fb2c-103">Beginning in the .NET Framework 4.5.1, dynamically binding to the methods <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601>, <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601(%60%600)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Object)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Type)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr)>, or <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr,%60%600)>, (via Windows PowerShell, IronPython, or the C# dynamic keyword, for example) can result in <code>MethodInvocationExceptions</code> because new overloads of these methods have been added that may be ambiguous to the scripting engines.</span></span>|
|<span data-ttu-id="8fb2c-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="8fb2c-104">Suggestion</span></span>|<span data-ttu-id="8fb2c-105">Aktualisieren Sie die Skripts, um eindeutig anzugeben, welche Überladung verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="8fb2c-105">Update scripts to clearly indicate which overload should be used.</span></span> <span data-ttu-id="8fb2c-106">Dies kann in der Regel dadurch erreicht werden, dass die Typparameter der Methoden explizit zu <xref:System.Type> umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="8fb2c-106">This can typically done by explicitly casting the methods' type parameters as <xref:System.Type>.</span></span> <span data-ttu-id="8fb2c-107">Weitere Informationen und Beispiele zur Problemumgehung finden Sie über [diesen Link](https://support.microsoft.com/kb/2909958/).</span><span class="sxs-lookup"><span data-stu-id="8fb2c-107">See [this link](https://support.microsoft.com/kb/2909958/) for more detail and examples of how to workaround the issue.</span></span>|
|<span data-ttu-id="8fb2c-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="8fb2c-108">Scope</span></span>|<span data-ttu-id="8fb2c-109">Gering</span><span class="sxs-lookup"><span data-stu-id="8fb2c-109">Minor</span></span>|
|<span data-ttu-id="8fb2c-110">Version</span><span class="sxs-lookup"><span data-stu-id="8fb2c-110">Version</span></span>|<span data-ttu-id="8fb2c-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="8fb2c-111">4.5.1</span></span>|
|<span data-ttu-id="8fb2c-112">Typ</span><span class="sxs-lookup"><span data-stu-id="8fb2c-112">Type</span></span>|<span data-ttu-id="8fb2c-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="8fb2c-113">Runtime</span></span>|
