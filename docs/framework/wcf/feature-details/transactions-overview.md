---
title: Übersicht über Windows Communication Foundation-Transaktionen
ms.date: 03/30/2017
helpviewer_keywords:
- transactions [WCF]
- WCF, transactions
- Windows Communication Foundation, transactions
ms.assetid: c7757854-1207-4019-8b31-552578b7d570
ms.openlocfilehash: c58a5ebc033f75413a975e6b1de4ed71d23a141b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54548481"
---
# <a name="windows-communication-foundation-transactions-overview"></a>Übersicht über Windows-Kommunikationfoundation-Transaktionen
Transaktionen stellen eine Möglichkeit dar, mehrere Aktionen oder Vorgänge in eine einzelne unteilbare Ausführungseinheit zu gruppieren. Eine Transaktion ist eine Auflistung von Vorgängen mit den folgenden Eigenschaften:  
  
-   Unteilbarkeit. Dadurch wird sichergestellt, dass entweder alle unter einer bestimmten Transaktion ausgeführten Updates übernommen und dauerhaft gemacht werden oder abgebrochen und in ihren vorherigen Zustand zurückversetzt werden.  
  
-   Konsistenz. Dadurch wird sichergestellt, dass die unter einer bestimmten Transaktion vorgenommenen Änderungen eine Transformation von einem konsistenten Zustand zu einem anderen darstellen. Beispielsweise ändert eine Transaktion, bei der Geld von einem Girokonto auf ein Sparkonto überwiesen wird, die Geldmenge auf dem Bankkonto insgesamt nicht.  
  
-   Isolation Dadurch wird verhindert, dass eine Transaktion ungespeicherte Änderungen beobachtet, die zu anderen gleichzeitigen Transaktionen gehören. Isolation bietet eine Abstraktion von Parallelität und stellt gleichzeitig sicher, dass eine Transaktion keine unerwarteten Auswirkungen auf die Ausführung einer anderen Transaktion haben kann.  
  
-   Dauerhaftigkeit. Dies bedeutet, dass Updates verwalteter Ressourcen (z. B. eines Datensatzes in einer Datenbank) nach der Ausführung bei Fehlern dauerhaft sind.  
  
 Windows Communication Foundation (WCF) bietet einen umfangreichen Satz von Funktionen, mit die Sie verteilte Transaktionen in Ihrer Webdienstanwendung erstellen können.  
  
 WCF implementiert die Unterstützung für das WS-AtomicTransaction (WS-AT)-Protokoll, das WCF-Anwendungen, Transaktionen zu interoperablen Anwendungen ausführen können, z. B. interoperabler Webdienste, die mithilfe von drittanbietertechnologie erstellt werden können. WCF implementiert auch Unterstützung für das OLE Transactions-Protokoll, die in Szenarien, in denen keine interop-Funktionalität zum Aktivieren des Transaktionsflusses benötigen Sie verwendet werden können.  
  
 Sie können eine Anwendungskonfigurationsdatei verwenden, um Bindungen für das Aktivieren bzw. Deaktivieren des Transaktionsflusses zu konfigurieren sowie das gewünschte Transaktionsprotokoll auf einer Bindung festzulegen. Außerdem können Sie mit der Konfigurationsdatei Transaktionstimeouts auf Dienstebene festlegen. Weitere Informationen finden Sie unter [Transaktionsfluss aktivieren](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).  
  
 Mithilfe von Transaktionsattributen im <xref:System.ServiceModel>-Namespace können Sie die folgenden Aktionen ausführen:  
  
-   Konfigurieren von Transaktionstimeouts und Isolationsstufenfilterung mit dem <xref:System.ServiceModel.ServiceBehaviorAttribute>-Attribut.  
  
-   Aktivieren der Transaktionsfunktionalität und Konfigurieren des Transaktionsabschlussverhaltens mit dem <xref:System.ServiceModel.OperationBehaviorAttribute>-Attribut.  
  
-   Verwenden des <xref:System.ServiceModel.ServiceContractAttribute>-Attributs und <xref:System.ServiceModel.OperationContractAttribute>-Attributs für eine Vertragsmethode, um den Transaktionsfluss zu erfordern, zuzulassen oder zu verweigern.  
  
 Weitere Informationen finden Sie unter [ServiceModel-Transaktionsattribute](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md).  
  
## <a name="see-also"></a>Siehe auch
- [ServiceModel-Transaktionsattribute](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md)
- [Aktivieren des Transaktionsdatenflusses](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)
