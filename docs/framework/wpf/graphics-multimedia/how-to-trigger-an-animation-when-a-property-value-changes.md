---
title: 'Vorgehensweise: Auslösen einer Animation, wenn sich eine Eigenschaft ändert'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
ms.openlocfilehash: 87f7525755556301fec3f00da612fc5262f1f533
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356142"
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a>Vorgehensweise: Auslösen einer Animation, wenn sich eine Eigenschaft ändert
Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Trigger> zu einem <xref:System.Windows.Media.Animation.Storyboard> bei Änderung eines Eigenschaftswerts. Sie können eine <xref:System.Windows.Trigger> innerhalb einer <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, oder <xref:System.Windows.DataTemplate>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Trigger> zum Animieren der <xref:System.Windows.UIElement.Opacity%2A> von einer <xref:System.Windows.Controls.Button> beim seine <xref:System.Windows.UIElement.IsMouseOver%2A> Eigenschaft `true`.  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 Eigenschaft angewendete Animationen <xref:System.Windows.Trigger> Objekte verhalten sich komplexer als <xref:System.Windows.EventTrigger> Animationen oder Animationen Einstieg <xref:System.Windows.Media.Animation.Storyboard> Methoden.  Sie "übergeben" mit Animationen definiert, die von anderen <xref:System.Windows.Trigger> Objekte, aber verfassen mit <xref:System.Windows.EventTrigger> und Methoden ausgelösten Animationen.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Trigger>
- [Übersicht über die Verfahren zur Animation von Eigenschaften](property-animation-techniques-overview.md)
- [Übersicht über Storyboards](storyboards-overview.md)
