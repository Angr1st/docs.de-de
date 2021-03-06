---
title: 'Vorgehensweise: Formatieren des DataGrid-Steuerelements in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], DataGrid control
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- columns [Windows Forms], formatting in DataGrid control
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
ms.openlocfilehash: 696fdc09d285e0a04148e82b0cece6108b7d5a45
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705908"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a>Vorgehensweise: Formatieren des DataGrid-Steuerelements in Windows Forms
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Verschiedene Farben zu verschiedenen Teilen der Anwendung eine <xref:System.Windows.Forms.DataGrid> steuern können, stellen die Informationen in der er leichter zu lesen und interpretieren. Farbe kann in Zeilen und Spalten angewendet werden. Zeilen und Spalten können auch ausgeblendet oder angezeigt, die in Ihrem eigenen Ermessen.  
  
 Es gibt drei grundlegende Aspekte der Formatierung der <xref:System.Windows.Forms.DataGrid> Steuerelement. Sie können festlegen, dass Eigenschaften zu, um einen Standardstil herzustellen, in dem Daten angezeigt werden. Auf dieser Basis können Sie die Möglichkeit, die bestimmte Tabellen zur Laufzeit angezeigt werden, klicken Sie dann anpassen. Abschließend können Sie ändern, welche Spalten im Raster als auch die Farben angezeigt werden, und andere, die Formatierung wird angezeigt.  
  
 Als ersten Schritt bei der Formatierung ein Datenraster, können Sie festlegen, der Eigenschaften der <xref:System.Windows.Forms.DataGrid> selbst. Diese Farbe und Format-Auswahl bilden eine Basis, die aus der Sie dann abhängig von der Tabellen und Spalten angezeigt, können Änderungen vornehmen.  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Herstellen einen Standardstil für das DataGrid-Steuerelement  
  
1.  Legen Sie die folgenden Eigenschaften nach Bedarf:  
  
    |Eigenschaft|Beschreibung|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|Die <xref:System.Windows.Forms.DataGrid.BackColor%2A> Eigenschaft definiert die Farbe der geraden Zeilen des Rasters. Beim Festlegen der <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> -Eigenschaft auf eine andere Farbe, jeder anderen Zeile in dieser neuen Farbe festgelegt ist (Zeilen, 1, 3, 5 und So weiter).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Die Hintergrundfarbe der geraden Zeilen des Rasters (Zeilen 0, 2, 4, 6 und So weiter).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Während der <xref:System.Windows.Forms.DataGrid.BackColor%2A> und <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> Eigenschaften bestimmt die Farbe der Zeilen im Raster die <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> Eigenschaft bestimmt die Farbe des der Datenblattzeilen, der nur sichtbar, wenn das Raster unten ein Bildlauf durchgeführt wird, oder wenn nur wenige Zeilen enthält das Raster.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Die Rahmenart des Datenblatts, eines der <xref:System.Windows.Forms.BorderStyle> -Enumerationswerte fest.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Die Hintergrundfarbe des Datenblatts fensterbeschriftung unmittelbar oberhalb des Rasters angezeigt wird.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Die Schriftart der Beschriftung am oberen Rand des Rasters.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Die Hintergrundfarbe der fensterbeschriftung des Datenblatts.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|Die Schriftart verwendet, um den Text im Raster anzuzeigen.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Die Farbe der Schriftart, die von den Daten in den Zeilen im Datenraster angezeigt werden soll.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Die Farbe der Datenblattlinien im Datenraster.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Der Stil der Linien zwischen den Zellen des Rasters, eines der <xref:System.Windows.Forms.DataGridLineStyle> -Enumerationswerte fest.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Die Hintergrundfarbe der Zeilen- und Spaltenüberschriften.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Die Schriftart für Spaltenköpfe verwendet.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Die Vordergrundfarbe der Spaltenköpfe des Datenblatts, einschließlich des Texts der Spaltenüberschrift, und die plus-/Minus-Symbole (zum Erweitern von Zeilen, wenn mehrere verknüpfte Tabellen angezeigt werden).|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Die Farbe des Texts, der alle Links im Datenraster, einschließlich Links zu untergeordneten Tabellen, Name der Beziehung und So weiter.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|In einer untergeordneten Tabelle ist dies die Hintergrundfarbe der übergeordneten Zeilen.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|In einer untergeordneten Tabelle ist dies die Vordergrundfarbe der übergeordneten Zeilen.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Bestimmt, ob die Tabellen- und Spaltennamen in der übergeordneten Zeile, von angezeigt werden der <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> Enumeration.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Die Standardbreite der Spalten des Rasters in Pixel. Legen Sie diese Eigenschaft vor dem Zurücksetzen der <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> Eigenschaften (entweder separat oder über die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode), oder die Eigenschaft hat keine Auswirkungen.<br /><br /> Die Eigenschaft kann nicht auf einen Wert kleiner als 0 festgelegt werden.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Die Zeilenhöhe (in Pixel) von Zeilen im Raster. Legen Sie diese Eigenschaft vor dem Zurücksetzen der <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> Eigenschaften (entweder separat oder über die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode), oder die Eigenschaft hat keine Auswirkungen.<br /><br /> Die Eigenschaft kann nicht auf einen Wert kleiner als 0 festgelegt werden.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Die Breite der Zeilenheader des Rasters.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Wenn eine Zeile oder Zelle ausgewählt ist, ist dies die Farbe des Hintergrunds.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Wenn eine Zeile oder Zelle ausgewählt ist, ist dies die Vordergrundfarbe darstellt.|  
  
    > [!NOTE]
    >  Beachten Sie, wenn die Farben der Steuerelemente anpassen, dass es möglich ist, die das Steuerelement aufgrund einer schlechten Farbauswahl (z. B. "Red" und "Grün") nicht möglich ist. Verwenden Sie die Farben, die auf die **Systemfarben** Palette, um dieses Problem zu vermeiden.  
  
     Die folgenden Verfahren wird davon ausgegangen, das Formular enthält ein <xref:System.Windows.Forms.DataGrid> -Steuerelement an eine Datentabelle gebunden. Weitere Informationen finden Sie unter [Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a>So legen Sie den Stil für Tabellen und Spalten einer Datentabelle programmgesteuert fest  
  
1.  Erstellen einer neuen Tabellenformatvorlage, und seine Eigenschaften festlegen.  
  
2.  Erstellen Sie ein Spaltenformat und festlegen Sie seine Eigenschaften.  
  
3.  Fügen Sie das Spaltenformat Auflistung Spaltenformate das Tabellenformat an.  
  
4.  Fügen Sie das Format der zur Auflistung für das Datenraster Tabelle Stile hinzu.  
  
5.  Erstellen Sie im folgenden Beispiel wird eine Instanz eines neuen <xref:System.Windows.Forms.DataGridTableStyle> und legen Sie dessen <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> Eigenschaft.  
  
6.  Erstellen Sie eine neue Instanz der ein **GridColumnStyle** und legen Sie dessen **%MappingName** (und einige andere Eigenschaften Layout und die Anzeige).  
  
7.  Wiederholen Sie die Schritte 2 bis 6 für jedes Spaltenformat, die Sie erstellen möchten.  
  
     Im folgende Beispiel wird veranschaulicht, wie eine <xref:System.Windows.Forms.DataGridTextBoxColumn> wird erstellt, weil ein Name, der in der Spalte angezeigt werden. Außerdem hinzugefügt werden, dem das Spaltenformat den <xref:System.Windows.Forms.GridColumnStylesCollection> des Tabellenformats, und Sie fügen das Tabellenformat an die <xref:System.Windows.Forms.GridTableStylesCollection> im Datenraster.  
  
    ```vb  
    Private Sub CreateAuthorFirstNameColumn()  
       ' Add a GridTableStyle and set the MappingName   
       ' to the name of the DataTable.  
       Dim TSAuthors As New DataGridTableStyle()  
       TSAuthors.MappingName = "Authors"  
  
       ' Add a GridColumnStyle and set the MappingName   
       ' to the name of a DataColumn in the DataTable.   
       ' Set the HeaderText and Width properties.   
       Dim TCFirstName As New DataGridTextBoxColumn()  
       TCFirstName.MappingName = "AV_FName"  
       TCFirstName.HeaderText = "First Name"  
       TCFirstName.Width = 75  
       TSAuthors.GridColumnStyles.Add(TCFirstName)  
  
       ' Add the DataGridTableStyle instance to   
       ' the GridTableStylesCollection.   
       myDataGrid.TableStyles.Add(TSAuthors)  
    End Sub  
    ```  
  
    ```csharp  
    private void addCustomDataTableStyle()  
    {  
       // Add a GridTableStyle and set the MappingName   
       // to the name of the DataTable.  
       DataGridTableStyle TSAuthors = new DataGridTableStyle();  
       TSAuthors.MappingName = "Authors";  
  
       // Add a GridColumnStyle and set the MappingName   
       // to the name of a DataColumn in the DataTable.   
       // Set the HeaderText and Width properties.   
       DataGridColumnStyle TCFirstName = new DataGridTextBoxColumn();  
       TCFirstName.MappingName = " AV_FName";  
       TCFirstName.HeaderText = "First Name";  
       TCFirstName.Width = 75;  
       TSAuthors.GridColumnStyles.Add(TCFirstName);  
  
       // Add the DataGridTableStyle instance to   
       // the GridTableStylesCollection.   
       dataGrid1.TableStyles.Add(TSAuthors);  
    }  
    ```  
  
    ```cpp  
    private:  
       void addCustomDataTableStyle()  
       {  
          // Add a GridTableStyle and set the MappingName   
          // to the name of the DataTable.  
          DataGridTableStyle^ TSAuthors = new DataGridTableStyle();  
          TSAuthors->MappingName = "Authors";  
  
          // Add a GridColumnStyle and set the MappingName   
          // to the name of a DataColumn in the DataTable.   
          // Set the HeaderText and Width properties.   
          DataGridColumnStyle^ TCFirstName = gcnew DataGridTextBoxColumn();  
          TCFirstName->MappingName = "AV_FName";  
          TCFirstName->HeaderText = "First Name";  
          TCFirstName->Width = 75;  
          TSAuthors->GridColumnStyles->Add(TCFirstName);  
  
          // Add the DataGridTableStyle instance to   
          // the GridTableStylesCollection.   
          dataGrid1->TableStyles->Add(TSAuthors);  
       }  
    ```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [Vorgehensweise: Löschen oder Ausblenden von Spalten im DataGrid-Steuerelement in Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [DataGrid-Steuerelement](datagrid-control-windows-forms.md)
