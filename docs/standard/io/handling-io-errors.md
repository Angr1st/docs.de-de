---
title: Behandeln von E/A-Fehlern in .NET
ms.date: 08/27/2018
ms.technology: dotnet-standard
ms.topic: article
helpviewer_keywords:
- I/O, exception handling
- I/O, errors
author: rpetrusha
ms.author: ronpet
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 50dee427913e1ec94a06f1202966bb0f7f5f2099
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2018
ms.locfileid: "46696416"
---
# <a name="handling-io-errors-in-net"></a><span data-ttu-id="14658-102">Behandeln von E/A-Fehlern in .NET</span><span class="sxs-lookup"><span data-stu-id="14658-102">Handling I/O errors in .NET</span></span>

<span data-ttu-id="14658-103">Über die Ausnahmen hinaus, die bei jedem Methodenaufruf ausgelöst werden können (wie etwa eine <xref:System.OutOfMemoryException>, wenn ein System unter Stress steht, oder eine <xref:System.NullReferenceException> aufgrund eines Programmierfehlers), können Methoden des .NET-Dateisystems die folgenden Ausnahmen auslösen:</span><span class="sxs-lookup"><span data-stu-id="14658-103">In addition to the exceptions that can be thrown in any method call (such as an <xref:System.OutOfMemoryException> when a system is stressed or an <xref:System.NullReferenceException> due to programmer error), .NET file system methods can throw the following exceptions:</span></span>

- <span data-ttu-id="14658-104"><xref:System.IO.IOException?displayProperty=nameWithType>, die Basisklasse aller <xref:System.IO>-Ausnahmetypen.</span><span class="sxs-lookup"><span data-stu-id="14658-104"><xref:System.IO.IOException?displayProperty=nameWithType>, the base class of all <xref:System.IO> exception types.</span></span> <span data-ttu-id="14658-105">Sie wird für Fehler ausgelöst, deren Rückgabecodes aus dem Betriebssystem sich nicht direkt anderen Ausnahmetypen zuordnen lassen.</span><span class="sxs-lookup"><span data-stu-id="14658-105">It is thrown for errors whose return codes from the operating system don't directly map to any other exception type.</span></span>
- <span data-ttu-id="14658-106"><xref:System.IO.FileNotFoundException?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="14658-106"><xref:System.IO.FileNotFoundException?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="14658-107"><xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="14658-107"><xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="14658-108"><xref:System.IO.DriveNotFoundException??displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="14658-108"><xref:System.IO.DriveNotFoundException??displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="14658-109"><xref:System.IO.PathTooLongException?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="14658-109"><xref:System.IO.PathTooLongException?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="14658-110"><xref:System.OperationCanceledException?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="14658-110"><xref:System.OperationCanceledException?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="14658-111"><xref:System.UnauthorizedAccessException?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="14658-111"><xref:System.UnauthorizedAccessException?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="14658-112"><xref:System.ArgumentException?displayProperty=nameWithType>, die für ungültige Zeichen in Pfaden für .NET Framework und .NET Core 2.0 sowie frühere Versionen ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="14658-112"><xref:System.ArgumentException?displayProperty=nameWithType>, which is thrown for invalid path characters on .NET Framework and on .NET Core 2.0 and previous versions.</span></span>
- <span data-ttu-id="14658-113"><xref:System.NotSupportedException?displayProperty=nameWithType>, die für ungültige Doppelpunkte in .NET Framework ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="14658-113"><xref:System.NotSupportedException?displayProperty=nameWithType>, which is thrown for invalid colons in .NET Framework.</span></span>
- <span data-ttu-id="14658-114"><xref:System.Security.SecurityException?displayProperty=nameWithType>, die für Anwendungen ausgelöst wird, die mit eingeschränkter Vertrauenswürdigkeit ausgeführt werden und denen lediglich die erforderlichen Berechtigungen für .NET Framework fehlen.</span><span class="sxs-lookup"><span data-stu-id="14658-114"><xref:System.Security.SecurityException?displayProperty=nameWithType>, which is thrown for applications running in limited trust that lack the necessary permissions on .NET Framework only.</span></span> <span data-ttu-id="14658-115">(Volle Vertrauenswürdigkeit stellt in .NET Framework den Standard dar.)</span><span class="sxs-lookup"><span data-stu-id="14658-115">(Full trust is the default on .NET Framework.)</span></span>

## <a name="mapping-error-codes-to-exceptions"></a><span data-ttu-id="14658-116">Zuordnen von Fehlercodes zu Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="14658-116">Mapping error codes to exceptions</span></span>

<span data-ttu-id="14658-117">Da das Dateisystem eine Betriebssystemressource ist, umschließen E/A-Methoden sowohl in .NET Core als auch in .NET Framework Aufrufe an das zugrundeliegende Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="14658-117">Because the file system is an operating system resource, I/O methods in both .NET Core and .NET Framework wrap calls to the underlying operating system.</span></span> <span data-ttu-id="14658-118">Wenn in Code, der vom Betriebssystem ausgeführt wird, ein E/A-Fehler auftritt, gibt das Betriebssystem Fehlerinformationen zu der .NET-E/A-Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="14658-118">When an I/O error occurs in code executed by the operating system, the operating system returns error information to the .NET I/O method.</span></span> <span data-ttu-id="14658-119">Die Methode übersetzt dann die Fehlerinformationen, normalerweise in Form eines Fehlercodes, in einen .NET-Ausnahmetyp.</span><span class="sxs-lookup"><span data-stu-id="14658-119">The method then translates the error information, typically in the form of an error code, into a .NET exception type.</span></span> <span data-ttu-id="14658-120">In den meisten Fällen erfolgt dies durch direktes Übersetzen des Fehlercodes in den entsprechenden Ausnahmetyp; es wird keine besondere Zuordnung des Fehlers auf der Grundlage des Kontexts des Methodenaufrufs vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="14658-120">In most cases, it does this by directly translating the error code into its corresponding exception type; it does not perform any special mapping of the error based on the context of the method call.</span></span>

<span data-ttu-id="14658-121">Beispielsweise wird im Windows-Betriebssystem ein Methodenaufruf, der den Fehlercode `ERROR_FILE_NOT_FOUND` (oder 0x02) zurückgibt, einer <xref:System.IO.FileNotFoundException> zugeordnet, und der Fehlercode `ERROR_PATH_NOT_FOUND` (oder 0x03) wird einer <xref:System.IO.DirectoryNotFoundException> zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="14658-121">For example, on the Windows operating system, a method call that returns an error code of `ERROR_FILE_NOT_FOUND` (or 0x02) maps to a <xref:System.IO.FileNotFoundException>, and an error code of `ERROR_PATH_NOT_FOUND` (or 0x03) maps to a <xref:System.IO.DirectoryNotFoundException>.</span></span>

<span data-ttu-id="14658-122">Die genauen Umstände, unter denen das Betriebssystem bestimmte Fehlercodes zurückgibt, sind aber häufig undokumentiert oder schlecht dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="14658-122">However, the precise conditions under which the operating system returns particular error codes is often undocumented or poorly documented.</span></span> <span data-ttu-id="14658-123">Daher können unerwartete Ausnahmen auftreten.</span><span class="sxs-lookup"><span data-stu-id="14658-123">As a result, unexpected exceptions can occur.</span></span> <span data-ttu-id="14658-124">Wenn Sie beispielsweise mit einem Verzeichnis anstelle einer Datei arbeiten, könnten Sie annehmen, dass die Angabe eines falschen Verzeichnispfads für den <xref:System.IO.DirectoryInfo.%23ctor%2A?displayProperty=nameWithType>-Konstruktor eine <xref:System.IO.DirectoryNotFoundException> auslöst.</span><span class="sxs-lookup"><span data-stu-id="14658-124">For example, because you are working with a directory rather than a file, you would expect that providing an invalid directory path to the <xref:System.IO.DirectoryInfo.%23ctor%2A?displayProperty=nameWithType> constructor throws a <xref:System.IO.DirectoryNotFoundException>.</span></span> <span data-ttu-id="14658-125">Es kann aber ebenso gut eine <xref:System.IO.FileNotFoundException> auslösen.</span><span class="sxs-lookup"><span data-stu-id="14658-125">However, it may also throw a <xref:System.IO.FileNotFoundException>.</span></span>

## <a name="exception-handling-in-io-operations"></a><span data-ttu-id="14658-126">Ausnahmebehandlung in E/A-Vorgängen</span><span class="sxs-lookup"><span data-stu-id="14658-126">Exception handling in I/O operations</span></span>

<span data-ttu-id="14658-127">Aufgrund dieses Rückgriffs auf das Betriebssystem können identische Ausnahmebedingungen (wie etwa der Fehler des nicht gefundenen Verzeichnisses in unserem Beispiel) dazu führen, dass eine E/A-Methode irgendeine aus der gesamten Klasse der E/A-Ausnahmen auslöst.</span><span class="sxs-lookup"><span data-stu-id="14658-127">Because of this reliance on the operating system, identical exception conditions (such as the directory not found error in our example) can result in an I/O method throwing any one of the entire class of I/O exceptions.</span></span> <span data-ttu-id="14658-128">Das bedeutet, dass beim Aufrufen von E/A-APIs Ihr Code in der Lage sein sollte, die meisten oder alle diese Ausnahmen zu behandeln, wie in der folgenden Tabelle dargestellt:</span><span class="sxs-lookup"><span data-stu-id="14658-128">This means that, when calling I/O APIs, your code should be prepared to handle most or all of these exceptions, as shown in the following table:</span></span>

| <span data-ttu-id="14658-129">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="14658-129">Exception type</span></span> | <span data-ttu-id="14658-130">.NET Core</span><span class="sxs-lookup"><span data-stu-id="14658-130">.NET Core</span></span> | <span data-ttu-id="14658-131">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="14658-131">.NET Framework</span></span> |
|---|---|---|
| <xref:System.IO.IOException> | <span data-ttu-id="14658-132">Ja</span><span class="sxs-lookup"><span data-stu-id="14658-132">Yes</span></span> | <span data-ttu-id="14658-133">Ja</span><span class="sxs-lookup"><span data-stu-id="14658-133">Yes</span></span> |
| <xref:System.IO.FileNotFoundException> | <span data-ttu-id="14658-134">Ja</span><span class="sxs-lookup"><span data-stu-id="14658-134">Yes</span></span> | <span data-ttu-id="14658-135">Ja</span><span class="sxs-lookup"><span data-stu-id="14658-135">Yes</span></span> |
| <xref:System.IO.DirectoryNotFoundException> | <span data-ttu-id="14658-136">Ja</span><span class="sxs-lookup"><span data-stu-id="14658-136">Yes</span></span> | <span data-ttu-id="14658-137">Ja</span><span class="sxs-lookup"><span data-stu-id="14658-137">Yes</span></span> |
| <xref:System.IO.DriveNotFoundException?> | <span data-ttu-id="14658-138">Ja</span><span class="sxs-lookup"><span data-stu-id="14658-138">Yes</span></span> | <span data-ttu-id="14658-139">Ja</span><span class="sxs-lookup"><span data-stu-id="14658-139">Yes</span></span> |
| <xref:System.IO.PathTooLongException> | <span data-ttu-id="14658-140">Ja</span><span class="sxs-lookup"><span data-stu-id="14658-140">Yes</span></span> | <span data-ttu-id="14658-141">Ja</span><span class="sxs-lookup"><span data-stu-id="14658-141">Yes</span></span> |
| <xref:System.OperationCanceledException> | <span data-ttu-id="14658-142">Ja</span><span class="sxs-lookup"><span data-stu-id="14658-142">Yes</span></span> | <span data-ttu-id="14658-143">Ja</span><span class="sxs-lookup"><span data-stu-id="14658-143">Yes</span></span> |
| <xref:System.UnauthorizedAccessException> | <span data-ttu-id="14658-144">Ja</span><span class="sxs-lookup"><span data-stu-id="14658-144">Yes</span></span> | <span data-ttu-id="14658-145">Ja</span><span class="sxs-lookup"><span data-stu-id="14658-145">Yes</span></span> |
| <xref:System.ArgumentException> | <span data-ttu-id="14658-146">.NET Core 2.0 und früher</span><span class="sxs-lookup"><span data-stu-id="14658-146">.NET Core 2.0 and earlier</span></span>| <span data-ttu-id="14658-147">Ja</span><span class="sxs-lookup"><span data-stu-id="14658-147">Yes</span></span> |
| <xref:System.NotSupportedException> | <span data-ttu-id="14658-148">Nein</span><span class="sxs-lookup"><span data-stu-id="14658-148">No</span></span> | <span data-ttu-id="14658-149">Ja</span><span class="sxs-lookup"><span data-stu-id="14658-149">Yes</span></span> |
| <xref:System.Security.SecurityException> | <span data-ttu-id="14658-150">Nein</span><span class="sxs-lookup"><span data-stu-id="14658-150">No</span></span> | <span data-ttu-id="14658-151">Eingeschränkte Vertrauenswürdigkeit</span><span class="sxs-lookup"><span data-stu-id="14658-151">Limited trust only</span></span> |

## <a name="handling-ioexception"></a><span data-ttu-id="14658-152">Behandlung von IOException</span><span class="sxs-lookup"><span data-stu-id="14658-152">Handling IOException</span></span>

<span data-ttu-id="14658-153">Als Basisklasse für Ausnahmen im Namespace <xref:System.IO> wird <xref:System.IO.IOException> auch für jeden Fehlercode ausgelöst, der sich keinem vordefinierten Ausnahmetyp zuordnen lässt.</span><span class="sxs-lookup"><span data-stu-id="14658-153">As the base class for exceptions in the <xref:System.IO> namespace, <xref:System.IO.IOException> is also thrown for any error code that does not map to a predefined exception type.</span></span> <span data-ttu-id="14658-154">Das bedeutet, dass sie von jedem E/A-Vorgang ausgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="14658-154">This means that it can be thrown by any I/O operation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14658-155">Da <xref:System.IO.IOException> die Basisklasse der anderen Ausnahmetypen im Namespace <xref:System.IO> ist, sollten Sie sie nach der Behandlung der anderen Ausnahmen im E/A-Zusammenhang in einem `catch`-Block behandeln.</span><span class="sxs-lookup"><span data-stu-id="14658-155">Because <xref:System.IO.IOException> is the base class of the other exception types in the <xref:System.IO> namespace, you should handle in a `catch` block after you've handled the other I/O-related exceptions.</span></span>

<span data-ttu-id="14658-156">Seit .NET Core 2.1 wurden darüber hinaus die Gültigkeitsprüfungen von Pfaden (um beispielsweise sicherzustellen, dass keine ungültigen Zeichen in einem Pfad vorhanden sind) entfernt, und die Runtime löst eine Ausnahme aus, die von einem Fehlercode des Betriebssystems anstelle seines eigenen Validierungscodes zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="14658-156">In addition, starting with .NET Core 2.1, validation checks for path correctness (for example, to ensure that invalid characters are not present in a path) have been removed, and the runtime throws an exception mapped from an operating system error code rather than from its own validation code.</span></span> <span data-ttu-id="14658-157">In diesem Fall ist die Ausnahme, die mit der größten Wahrscheinlichkeit ausgelöst wird, <xref:System.IO.IOException>; allerdings könnte auch jeder andere Ausnahmetyp ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="14658-157">The most likely exception to be thrown in this case is an <xref:System.IO.IOException>, although any other exception type could also be thrown.</span></span>

<span data-ttu-id="14658-158">Beachten Sie, dass Sie in Ihrem Fehlerbehandlungscode die <xref:System.IO.IOException> immer zuletzt behandeln sollten.</span><span class="sxs-lookup"><span data-stu-id="14658-158">Note that, in your exception handling code, you should always handle the <xref:System.IO.IOException> last.</span></span> <span data-ttu-id="14658-159">Da sie die Basisklasse aller anderen EA-Ausnahmen bildet, werden sonst die Catch-Blöcke von abgeleiteten Klassen nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="14658-159">Otherwise, because it is the base class of all other IO exceptions, the catch blocks of derived classes will not be evaluated.</span></span>

<span data-ttu-id="14658-160">Im Fall einer <xref:System.IO.IOException> können Sie zusätzliche Fehlerinformationen aus der Eigenschaft [IOException.HResult](xref:System.Exception.HResult) abrufen.</span><span class="sxs-lookup"><span data-stu-id="14658-160">In the case of an <xref:System.IO.IOException>, you can get additional error information from the [IOException.HResult](xref:System.Exception.HResult) property.</span></span> <span data-ttu-id="14658-161">Um den HResult-Wert in einen Win32-Fehlercode zu konvertieren, entfernen Sie die oberen 16 Bits des 32-Bit-Werts.</span><span class="sxs-lookup"><span data-stu-id="14658-161">To convert the HResult value to a Win32 error code, you strip out the upper 16 bits of the 32-bit value.</span></span> <span data-ttu-id="14658-162">In der folgenden Tabelle sind Fehlercodes aufgelistet, die von einer <xref:System.IO.IOException> umschlossen werden können.</span><span class="sxs-lookup"><span data-stu-id="14658-162">The following table lists error codes that may be wrapped in an <xref:System.IO.IOException>.</span></span>

| <span data-ttu-id="14658-163">HResult</span><span class="sxs-lookup"><span data-stu-id="14658-163">HResult</span></span> | <span data-ttu-id="14658-164">Konstante</span><span class="sxs-lookup"><span data-stu-id="14658-164">Constant</span></span> | <span data-ttu-id="14658-165">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="14658-165">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="14658-166">ERROR_SHARING_VIOLATION</span><span class="sxs-lookup"><span data-stu-id="14658-166">ERROR_SHARING_VIOLATION</span></span> | <span data-ttu-id="14658-167">32</span><span class="sxs-lookup"><span data-stu-id="14658-167">32</span></span> | <span data-ttu-id="14658-168">Der Dateiname fehlt, oder die Datei oder das Verzeichnis wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="14658-168">The file name is missing, or the file or directory is in use.</span></span> |
| <span data-ttu-id="14658-169">ERROR_FILE_EXISTS</span><span class="sxs-lookup"><span data-stu-id="14658-169">ERROR_FILE_EXISTS</span></span> | <span data-ttu-id="14658-170">80</span><span class="sxs-lookup"><span data-stu-id="14658-170">80</span></span> | <span data-ttu-id="14658-171">Die Datei ist bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="14658-171">The file already exists.</span></span> |
| <span data-ttu-id="14658-172">ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="14658-172">ERROR_INVALID_PARAMETER</span></span> | <span data-ttu-id="14658-173">87</span><span class="sxs-lookup"><span data-stu-id="14658-173">87</span></span> | <span data-ttu-id="14658-174">Ein der Methode übergebenes Argument ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="14658-174">An argument supplied to the method is invalid.</span></span> |
| <span data-ttu-id="14658-175">ERROR_ALREADY_EXISTS</span><span class="sxs-lookup"><span data-stu-id="14658-175">ERROR_ALREADY_EXISTS</span></span> | <span data-ttu-id="14658-176">183</span><span class="sxs-lookup"><span data-stu-id="14658-176">183</span></span> | <span data-ttu-id="14658-177">Die Datei oder das Verzeichnis ist bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="14658-177">The file or directory already exists.</span></span> |

<span data-ttu-id="14658-178">Sie können diese mithilfe einer `When`-Klausel in einer catch-Anweisung behandeln, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="14658-178">You can handle these using a `When` clause in a catch statement, as the following example shows.</span></span>

[!code-csharp[io-exception-handling](~/samples/snippets/standard/io/io-exceptions/cs/io-exceptions.cs)]
[!code-vb[io-exception-handling](~/samples/snippets/standard/io/io-exceptions/vb/io-exceptions.vb)]

## <a name="see-also"></a><span data-ttu-id="14658-179">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14658-179">See also</span></span>

- [<span data-ttu-id="14658-180">Behandeln und Auslösen von Ausnahmen in .NET</span><span class="sxs-lookup"><span data-stu-id="14658-180">Handling and throwing exceptions in .NET</span></span>](../exceptions/index.md)
- [<span data-ttu-id="14658-181">Ausnahmebehandlung (Task Parallel Library)</span><span class="sxs-lookup"><span data-stu-id="14658-181">Exception handling (Task Parallel Library)</span></span>](../parallel-programming/exception-handling-task-parallel-library.md)
- [<span data-ttu-id="14658-182">Bewährte Methoden für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="14658-182">Best practices for exceptions</span></span>](../exceptions/best-practices-for-exceptions.md)
- [<span data-ttu-id="14658-183">Gewusst wie: Verwenden spezifischer Ausnahmen in einem Catch-Block</span><span class="sxs-lookup"><span data-stu-id="14658-183">How to use specific exceptions in a catch block</span></span>](../exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)