---
title: 'Vorgehensweise: Abfragen von LINQ to XML mit XPath (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: e1f69a20-1efa-452d-9089-c472fa84b3d5
ms.openlocfilehash: 754b3c4d1f14f2f78b5688f13ab679bc01798a6c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54615989"
---
# <a name="how-to-query-linq-to-xml-using-xpath-visual-basic"></a>Vorgehensweise: Abfragen von LINQ to XML mit XPath (Visual Basic)
Dieses Thema führt Sie in die Erweiterungsmethoden ein, mit denen Sie zum Abfragen einer XML-Struktur XPath verwenden können. Ausführliche Informationen zum Verwenden dieser Erweiterungsmethoden finden Sie unter <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.  
  
 Sofern Sie keinen besonderen Grund dafür haben, Abfragen mit XPath zu schreiben, z. B. weil in großem Maße Legacy-Code verwendet wird, wird die Verwendung von XPath mit LINQ to XML nicht empfohlen. XPath-Abfragen sind nicht so leistungsfähig wie [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfragen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine kleine XML-Struktur und verwendet zum Auswählen eines Satzes von Elementen <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A>.  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>1</Child1>  
        <Child1>2</Child1>  
        <Child1>3</Child1>  
        <Child2>4</Child2>  
        <Child2>5</Child2>  
        <Child2>6</Child2>  
    </Root>  
  
Dim list As IEnumerable(Of XElement) = root.XPathSelectElements("./Child2")  
For Each el As XElement In list  
    Console.WriteLine(el)  
Next  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  
## <a name="see-also"></a>Siehe auch
- [Erweiterte Abfragetechniken (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
