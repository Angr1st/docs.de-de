---
title: 'Vorgehensweise: Verwenden des Master-/Detailmusters mit hierarchischen XML-Daten'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: 2b1ed34fe363f44a3a9eb80dc56d721868329717
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378105"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a>Vorgehensweise: Verwenden des Master-/Detailmusters mit hierarchischen XML-Daten
Dieses Beispiel zeigt, wie Sie das Master / Detail-Szenario mit implementieren [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Data-Version des Beispiels ausführlicher [verwenden Sie die Master-/ Detailmusters mit hierarchischen Daten](how-to-use-the-master-detail-pattern-with-hierarchical-data.md). In diesem Beispiel werden die Daten aus der Datei sind `League.xml`. Hinweis wie die dritte <xref:System.Windows.Controls.ListBox> Steuerelement verfolgt die Änderungen der Auswahl in der zweiten <xref:System.Windows.Controls.ListBox> durch Bindung an die <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> Eigenschaft.  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.HierarchicalDataTemplate>
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
