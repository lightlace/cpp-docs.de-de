---
title: "Event Handling Principles"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "duale Schnittstellen, event interfaces"
  - "Ereignisbehandlung, advising event sources"
  - "Ereignisbehandlung, dual event interfaces"
  - "Ereignisbehandlung, Implementieren"
  - "Schnittstellen, event and event sink"
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Event Handling Principles
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es gibt drei Schritte, die auf alle Ereignisbehandlung gemeinsam sind.  Sie benötigen:  
  
-   Implementieren Sie die Ereignisschnittstelle für das Objekt.  
  
-   Melden Sie sich die Ereignisquelle an, dass das Objekt Ereignisse empfangen will.  
  
-   Melden Sie sich die Ereignisquelle wenn die Anforderungen des Objekts nicht mehr, Ereignisse empfangen ab.  
  
 Die Methode, der Sie die Ereignisschnittstelle implementieren, hängt von seinem Typ ab.  Eine Ereignisschnittstelle kann vtable, dual oder eine Dispatchschnittstelle sein.  Sie ist bis zum Designer der Ereignisquelle, um die Schnittstelle zu definieren, sie hängt, um diese Schnittstelle zu implementieren.  
  
> [!NOTE]
>  Obwohl keine technischen Gründen gibt an, dass eine Ereignisschnittstelle nicht dual sein kann, gibt es einige gute entwicklungsspezifischen Gründe, die Verwendung von zu vermeiden verdoppelt.  Dies ist jedoch eine Entscheidung, die vom Designer\/die Implementierung der Ereignisquelle erfüllt ist.  Wenn Sie aus der Sicht des Ereignisses `sink` arbeiten, müssen Sie die Wahrscheinlichkeit zulassen, dass Sie möglicherweise keine Auswahl haben, aber eine duale Ereignisschnittstelle implementieren.  Weitere Informationen zu dualen Schnittstellen, finden Sie unter [Duale Schnittstellen und ATL](../atl/dual-interfaces-and-atl.md).  
  
 Die Anmeldung der Ereignisquelle kann in drei Schritte aufgegliedert werden:  
  
-   Fragen Sie das Quellobjekt für [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857) ab.  
  
-   Rufen Sie [IConnectionPointContainer::FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476) auf, das die IID der Ereignisschnittstelle übergeben wird, die für Sie.  Wenn erfolgreich, gibt dies die [die IConnectionPoint\-Schnittstelle](http://msdn.microsoft.com/library/windows/desktop/ms694318)\-Schnittstelle in einem Verbindungspunktobjekt zurück.  
  
-   Rufen Sie [IConnectionPoint::Advise](http://msdn.microsoft.com/library/windows/desktop/ms678815) auf, das **IUnknown** der Ereignissenke übergibt.  Wenn erfolgreich, gibt dieses `DWORD` ein Cookie zurück, das die Verbindung darstellt.  
  
 Sobald Sie erfolgreich das Interesse registriert haben, an, Ereignisse zu empfangen, werden Methoden auf der Ereignisschnittstelle des Objekts entsprechend den Ereignissen aufgerufen, die durch das Quellobjekt ausgelöst werden.  Wenn Sie nicht mehr Ereignisse empfangen müssen, können Sie das Cookie zurück zu dem Verbindungspunkt über [IConnectionPoint::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms686608) übergeben.  Dieses unterbricht die Verbindung zwischen Quelle und Senke.  
  
 Achten Sie darauf, dass Sie Bezugszyklen vermeiden, wenn Sie Ereignisse behandeln.  
  
## Siehe auch  
 [Ereignisbehandlung](../atl/event-handling-and-atl.md)