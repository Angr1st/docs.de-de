---
title: <remarks> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 5065d43a0d3262ebe89d25351f791022bfd87077
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502565"
---
# <a name="remarks-visual-basic"></a>\<remarks> (Visual Basic)
Gibt einen Abschnitt "Hinweise" für das Element an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a>Parameter  
 `description`  
 Eine Beschreibung des Members  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `<remarks>` Tag, das Hinzufügen von Informationen zu einem Typ, die mit angegebene Informationen ergänzen [ \<summary >](../../../visual-basic/language-reference/xmldoc/summary.md).  
  
 Diese Informationen werden im Objektkatalog angezeigt. Weitere Informationen zu den Objektkatalog, finden Sie unter [Anzeigen der Codestruktur](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<remarks>` -Tag erläutert, was die `UpdateRecord` Methode.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Siehe auch
- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
