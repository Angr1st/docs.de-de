---
title: Selektive Serialisierung
ms.date: 08/07/2017
dev_langs:
- CSharp
helpviewer_keywords:
- serialization, selective serialization
- binary serialization, selective serialization
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
ms.openlocfilehash: af608031a661037b89c9783ac2451a6b536f9cd4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731386"
---
# <a name="selective-serialization"></a>Selektive Serialisierung
Eine Klasse enthält oft Felder, die nicht serialisiert werden sollten. Angenommen, eine Klasse speichert in einer Membervariablen eine Thread-ID. Wenn die Klasse deserialisiert wird, wird der Thread, dessen ID bei der Serialisierung der Klasse gespeichert wurde, möglicherweise nicht mehr ausgeführt. Daher ist es nicht sinnvoll, diesen Wert zu serialisieren. Sie können verhindern, dass Membervariablen serialisiert werden, indem Sie sie wie folgt mit dem [NonSerialized](xref:System.NonSerializedAttribute)-Attribut markieren.  
  
```csharp  
[Serializable]  
public class MyObject   
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```

Legen Sie nach Möglichkeit jedes Objekt, das sicherheitsrelevante Daten enthalten kann, als nicht serialisierbar fest. Wenn das Objekt serialisiert werden muss, wenden Sie das `NonSerialized`-Attribut auf bestimmte Felder an, die vertrauliche Daten speichern. Wenn diese Felder nicht von der Serialisierung ausgeschlossen werden, werden die darin gespeicherten Daten für jeglichen Code verfügbar gemacht, der zur Serialisierung berechtigt ist. Weitere Informationen zum Schreiben von sicherem Serialisierungscode finden Sie unter [Sicherheit und Serialisierung](../../../docs/framework/misc/security-and-serialization.md).

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a>Siehe auch

- [Binäre Serialisierung](binary-serialization.md)
- [XML- und SOAP-Serialisierung](xml-and-soap-serialization.md)
- [Sicherheit und Serialisierung](../../../docs/framework/misc/security-and-serialization.md)
