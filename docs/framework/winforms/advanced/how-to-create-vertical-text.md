---
title: 'Vorgehensweise: Erstellen von vertikalem Text'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- Windows Forms, drawing vertical text
- strings [Windows Forms], drawing vertical
- vertical text [Windows Forms], drawing
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
ms.openlocfilehash: 720e343f1b3b20fe3df96a03fbd67ee473ec13f6
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2019
ms.locfileid: "58125407"
---
# <a name="how-to-create-vertical-text"></a>Vorgehensweise: Erstellen von vertikalem Text
Sie können eine <xref:System.Drawing.StringFormat> Objekt, um anzugeben, dass der Text vertikal oder horizontal gezeichnet werden soll.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel weist den Wert <xref:System.Drawing.StringFormatFlags.DirectionVertical> auf die <xref:System.Drawing.StringFormat.FormatFlags%2A> Eigenschaft eine <xref:System.Drawing.StringFormat> Objekt. Dass <xref:System.Drawing.StringFormat> Objekt wird zum Übergeben der <xref:System.Drawing.Graphics.DrawString%2A> Methode der <xref:System.Drawing.Graphics> Klasse. Der Wert <xref:System.Drawing.StringFormatFlags.DirectionVertical> ist ein Mitglied der <xref:System.Drawing.StringFormatFlags> Enumeration.  
  
 Die folgende Abbildung zeigt den vertikalen Text an: 
  
 ![Grafik, die-Schriftart Text zeigt.](./media/how-to-create-vertical-text/vertical-font-text-graphic.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e` , d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch
- [Vorgehensweise: Zeichnen von Text mit GDI](how-to-draw-text-with-gdi.md)
