---
title: 'Vorgehensweise: Animieren eines Popups'
ms.date: 03/30/2017
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
ms.openlocfilehash: ed5edf298e59d6a9adddc03fc21de1900c7ee8e9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372840"
---
# <a name="how-to-animate-a-popup"></a>Vorgehensweise: Animieren eines Popups
Dieses Beispiel zeigt zwei Methoden zum Animieren einer <xref:System.Windows.Controls.Primitives.Popup> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Controls.Primitives.PopupAnimation> Eigenschaft mit einem Wert von <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, bewirkt, dass die <xref:System.Windows.Controls.Primitives.Popup> auf "Folie-in" Wenn es angezeigt wird.  
  
 Um eine Rotation zu der <xref:System.Windows.Controls.Primitives.Popup>, in diesem Beispiel wird eine <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft für die <xref:System.Windows.Controls.Canvas>, dies ist das untergeordnete Element des der <xref:System.Windows.Controls.Primitives.Popup>.  
  
 Für die Transformation ordnungsgemäß funktioniert, muss die im Beispiel festgelegt die <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> Eigenschaft `true`. Darüber hinaus die <xref:System.Windows.FrameworkElement.Margin%2A> auf die <xref:System.Windows.Controls.Canvas> angeben Inhalts muss genügend Speicherplatz für die <xref:System.Windows.Controls.Primitives.Popup> gedreht.  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 Das folgende Beispiel zeigt wie eine <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis, das eintritt, wenn eine <xref:System.Windows.Controls.Button> geklickt wird, werden Trigger die <xref:System.Windows.Media.Animation.Storyboard> , beginnt die Animation.  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Controls.Primitives.BulletDecorator>
- <xref:System.Windows.Media.RotateTransform>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Controls.Primitives.Popup>
- [Themen zu Vorgehensweisen](popup-how-to-topics.md)
- [Übersicht über Popups](popup-overview.md)
