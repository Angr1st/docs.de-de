---
title: 'Vorgehensweise: Binden eines Windows Forms-Kombinationsfeld oder das ListBox-Steuerelement an Daten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], binding to controls
- list boxes [Windows Forms], data binding
- ComboBox control [Windows Forms], data binding
- data binding [Windows Forms], combo boxes
- ListBox control [Windows Forms], data binding
- combo boxes [Windows Forms], data binding
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- data-bound controls [Windows Forms], Windows Forms
ms.assetid: dfd7f081-8bea-4a41-86a3-86a1934828ef
ms.openlocfilehash: c8eb224cbb8ec7ab271edaed8bb25f9cc7fb8ddc
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709925"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a>Vorgehensweise: Binden eines Windows Forms-Kombinationsfeld oder das ListBox-Steuerelement an Daten
Sie binden die <xref:System.Windows.Forms.ComboBox> und <xref:System.Windows.Forms.ListBox> auf Daten für Aufgaben wie das Durchsuchen von Daten in einer Datenbank eingeben neuer Daten, oder Bearbeiten vorhandener Daten.  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a>Zum Binden eines ComboBox-Steuerelements oder ListBox-Steuerelements  
  
1.  Legen Sie die `DataSource` Eigenschaft, um ein Datenquellenobjekt. Mögliche Datenquellen umfassen eine <xref:System.Windows.Forms.BindingSource> an Daten, einer Datentabelle, eine Data source View, ein Dataset gebunden ist, eine Datenansicht Manager, ein Array oder eine beliebige Klasse, die implementiert die <xref:System.Collections.IList> Schnittstelle. Weitere Informationen finden Sie unter [von Windows Forms unterstützte Datenquellen](../data-sources-supported-by-windows-forms.md).  
  
2.  Wenn Sie in eine Tabelle binden, legen Sie die `DisplayMember` -Eigenschaft auf den Namen einer Spalte in der Datenquelle.  
  
     \- oder –  
  
     Wenn Sie eine Bindung eine <xref:System.Collections.IList>, legen Sie eine öffentliche Eigenschaft des Typs in der Liste der Anzeigemember.  
  
    ```vb  
    Private Sub BindComboBox()  
      ComboBox1.DataSource = DataSet1.Tables("Suppliers")  
      ComboBox1.DisplayMember = "ProductName"  
    End Sub  
    ```  
  
    ```csharp  
    private void BindComboBox()  
    {  
      comboBox1.DataSource = dataSet1.Tables["Suppliers"];  
      comboBox1.DisplayMember = "ProductName";  
    }  
    ```  
  
    > [!NOTE]
    >  Wenn Sie eine Datenquelle gebunden sind, die nicht implementiert die <xref:System.ComponentModel.IBindingList> Schnittstelle, z. B. eine <xref:System.Collections.ArrayList>, Daten für das gebundene Steuerelement werden nicht aktualisiert werden, wenn die Datenquelle aktualisiert wird. Z. B. Wenn Sie über ein Kombinationsfeld gebunden ein <xref:System.Collections.ArrayList> und Daten werden hinzugefügt, um die <xref:System.Collections.ArrayList>, diese neue Elemente werden nicht im Kombinationsfeld angezeigt. Sie können jedoch erzwingen, dass im Kombinationsfeld aktualisiert werden, durch den Aufruf der <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> und <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> Methoden für die Instanz der <xref:System.Windows.Forms.BindingContext> Klasse an die das Steuerelement gebunden ist.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Windows Forms-Datenbindung](../windows-forms-data-binding.md)
- [Datenbindung und Windows Forms](../data-binding-and-windows-forms.md)
- [Windows Forms-Steuerelemente zum Auflisten von Optionen](windows-forms-controls-used-to-list-options.md)
