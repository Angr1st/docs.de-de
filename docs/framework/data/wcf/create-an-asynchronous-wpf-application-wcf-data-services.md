---
title: 'Vorgehensweise: Erstellen einer asynchronen Windows Presentation Framework-Anwendung (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, asynchronous operations
ms.assetid: 834614df-1427-4839-b0be-90f68e5afffd
ms.openlocfilehash: 89a4d1c244e69098971e87957f308f9a30ade6d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676639"
---
# <a name="how-to-create-an-asynchronous-windows-presentation-framework-application-wcf-data-services"></a>Vorgehensweise: Erstellen einer asynchronen Windows Presentation Framework-Anwendung (WCF Data Services)
Mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] können Sie aus einem Datendienst abgerufene Daten an Benutzeroberflächenelemente einer WPF (Windows Presentation Framework)-Anwendung binden. Weitere Informationen finden Sie unter [Binden von Daten an Steuerelemente](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md). Sie können auch Vorgänge für den Datendienst asynchron, ausführen, die die Anwendung weiterhin beim Warten auf einer Antwort auf eine datendienstanforderung reagieren zu können. Anwendungen für Silverlight sind erforderlich, um asynchron auf den Datendienst zuzugreifen. Weitere Informationen finden Sie unter [asynchrone Vorgänge](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
 In diesem Thema wird gezeigt, wie asynchron auf einen Datendienst zugegriffen wird und die Ergebnisse an Elemente einer WPF-Anwendung gebunden werden. In den Beispielen in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Clientdatendienstklassen verwendet. Dieser Dienst und die clientdatenklassen werden erstellt, wenn Sie die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende XAML-Code definiert das Fenster der WPF-Anwendung.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingAsyncXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml#wpfdatabindingasyncxaml)]  
  
## <a name="example"></a>Beispiel  
 Die folgende Code-Behind-Seite für die XAML-Datei führt mit dem Datendienst eine asynchrone Abfrage aus und bindet die Ergebnisse an Elemente im WPF-Fenster.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerordersasync.xaml.cs#wpfdatabindingasync)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml.vb#wpfdatabindingasync)]  
  
## <a name="see-also"></a>Siehe auch
- [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
