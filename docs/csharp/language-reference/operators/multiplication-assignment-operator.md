---
title: '*=-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 70461f79e714e44354fe4137e5360769fa048d3e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967385"
---
# <a name="-operator-c-reference"></a>Operator \*= (C#-Referenz)

Der Multiplikationszuweisungsoperator.

Ein Ausdruck mit dem Operator `*=`, z.B.

```csharp
x *= y
```

für die folgende Syntax:

```csharp
x = x * y
```

außer dass `x` nur einmal überprüft wird.

Für numerische Typen berechnet der [\*-Operator](multiplication-operator.md) das Produkt seiner Operanden.

Im folgenden Beispiel wird die Verwendung des `*=`-Operators veranschaulicht:

[!code-csharp-interactive[multiply and assign](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#MultiplyAndAssign)]

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Wenn ein benutzerdefinierter Typ den [Multiplikationsoperator](multiplication-operator.md) `*` [überlädt](../keywords/operator.md), wird auch der Multiplikationszuweisungsoperator `*=` implizit überladen. Ein benutzerdefinierter Typ kann den Multiplikationszuweisungsoperator nicht explizit überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Verbundzuweisung](~/_csharplang/spec/expressions.md#compound-assignment) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
