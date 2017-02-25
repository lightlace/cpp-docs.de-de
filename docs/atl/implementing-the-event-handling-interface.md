---
title: "Implementing the Event Handling Interface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, Ereignisbehandlung"
  - "Ereignisbehandlung, ATL"
  - "Schnittstellen, event and event sink"
ms.assetid: eb2a5b33-88dc-4ce3-bee0-c5c38ea050d7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Implementing the Event Handling Interface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL können Sie mit allen drei Elementen, die zum Behandeln von Ereignissen erforderlich sind: die Ereignisschnittstelle implementieren, die Ereignisquelle und das Abmelden der Ereignisquelle anmeldend.  Die genauen Schritte, die Sie ausführen, hängen vom Typ der Ereignisschnittstelle und den Leistungsanforderungen der Anwendung ab.  
  
 Die am häufigsten verwendeten Methoden der Implementierung einer Schnittstelle mit ATL sind:  
  
-   Von einer benutzerdefinierten Schnittstelle direkt berechnen.  
  
-   Ableiten von [IDispatchImpl](../atl/reference/idispatchimpl-class.md) für die duale Schnittstellen in einer Typbibliothek beschrieben.  
  
-   Ableiten von [IDispEventImpl](../atl/reference/idispeventimpl-class.md) für die Dispatchschnittstellen in einer Typbibliothek beschrieben.  
  
-   Ableiten von [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) für die Disp\-Schnittstellen beschrieben nicht in einer Typbibliothek oder, wenn Sie die Effizienz verbessern möchten, indem Sie nicht zur Laufzeit die Typinformationen laden.  
  
 Wenn Sie eine benutzerdefinierte oder eine duale Schnittstelle implementieren, sollten Sie die Ereignisquelle anmelden, indem Sie [AtlAdvise](../Topic/AtlAdvise.md) oder [CComPtrBase::Advise](../Topic/CComPtrBase::Advise.md) aufrufen.  Sie müssen das Cookie verfolgen, das durch den Aufruf sich zurückgegeben wird.  Aufruf [AtlUnadvise](../Topic/AtlUnadvise.md), um die Verbindung zu unterbrechen.  
  
 Wenn Sie eine Dispatchschnittstelle mithilfe `IDispEventImpl` oder `IDispEventSimpleImpl` implementieren, sollten Sie die Ereignisquelle anmelden, indem Sie [IDispEventSimpleImpl::DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md) aufrufen.  Aufruf [IDispEventSimpleImpl::DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md), um die Verbindung zu unterbrechen.  
  
 Wenn Sie `IDispEventImpl` als Basisklasse zusammengesetztes Steuerelement verwenden, werden die Ereignisquellen, die in der Senkenzuordnung aufgeführt sind, automatisch mit [CComCompositeControl::AdviseSinkMap](../Topic/CComCompositeControl::AdviseSinkMap.md) angemeldet und abgemeldet.  
  
 Die `IDispEventImpl` und `IDispEventSimpleImpl`\-Klassen verwalten das Cookie für Sie.  
  
## Siehe auch  
 [Ereignisbehandlung](../atl/event-handling-and-atl.md)