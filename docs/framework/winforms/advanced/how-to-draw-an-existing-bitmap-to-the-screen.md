---
title: 'Vorgehensweise: Zeichnen einer vorhandenen Bitmap auf dem Bildschirm'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
ms.openlocfilehash: a23026e0ac377294e3e4356d341c45d31b4ecd79
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724439"
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a>Vorgehensweise: Zeichnen einer vorhandenen Bitmap auf dem Bildschirm
Sie können ein vorhandenes Image ganz einfach auf dem Bildschirm zeichnen. Zunächst müssen Sie erstellen eine <xref:System.Drawing.Bitmap> Objekt mit dem Bitmapkonstruktor, der einen Dateinamen akzeptiert <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>. Dieser Konstruktor akzeptiert die Images mit mehrere verschiedene Dateiformate einschließlich BMP, GIF, JPEG, PNG und TIFF. Nach der Erstellung der <xref:System.Drawing.Bitmap> Objekt, und übergeben, die <xref:System.Drawing.Bitmap> -Objekt an die <xref:System.Drawing.Graphics.DrawImage%2A> Methode eine <xref:System.Drawing.Graphics> Objekt.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird eine <xref:System.Drawing.Bitmap> Objekt aus einem JPEG-Datei und zeichnet dann die Bitmap mit der linken oberen Ecke auf ("60", "10").  
  
 Die folgende Abbildung zeigt die Bitmap gezeichnet, die an der angegebenen Position.  
  
 ![Abbildung Position](./media/csimageposition1.png "csimageposition1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](working-with-images-bitmaps-icons-and-metafiles.md)
