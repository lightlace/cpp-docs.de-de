---
title: "Optionen, ATL-Assistent f&#252;r Active Server Page-Komponenten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.asp.options"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Assistent für Active Server Page-Komponenten, Optionen"
ms.assetid: 54f34e26-53c7-4456-9675-cb86e356bde0
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Optionen, ATL-Assistent f&#252;r Active Server Page-Komponenten
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Auf dieser Seite des ATL\-Assistenten für Active Server Page\-Komponenten können Sie das Objekt effizienter gestalten und Unterstützung für die Fehlerbehebung hinzufügen.  
  
 Weitere Informationen zu ATL\-Projekten und ATL\-COM\-Klassen finden Sie unter [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md).  
  
 **Threadmodell**  
 Gibt die für die Threadverwaltung verwendete Methode an.  Das Projekt verwendet standardmäßig das Threadmodell **Apartment**.  
  
 Weitere Informationen finden Sie unter [Festlegen des Threadingmodells des Projekts](../../atl/specifying-the-threading-model-for-a-project-atl.md).  
  
|Option|Description|  
|------------|-----------------|  
|`Single`|Legt fest, dass das Objekt das Singlethreadingmodell verwendet.  Beim Singlethreadingmodell wird ein Objekt immer im primären COM\-Thread ausgeführt.  Weitere Informationen finden Sie unter [Singlethreaded Apartments](http://msdn.microsoft.com/library/windows/desktop/ms680112) und [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390).|  
|**Apartment**|Legt fest, dass das Objekt das Apartmentthreadingmodell verwendet.  Entspricht dem Singlethreadapartment.  Jedem Objekt einer Apartmentthreadkomponente wird während seiner Lebensdauer ein Apartment für den Thread zugewiesen. Für mehrere Objekte können jedoch auch mehrere Threads verwendet werden.  Jedes Apartment ist an einen bestimmten Thread gebunden und verfügt über eine Windows\-Nachrichtenverteilschleife \(Standard\).<br /><br /> Weitere Informationen finden Sie unter [Singlethreaded Apartments](http://msdn.microsoft.com/library/windows/desktop/ms680112).|  
|**Beides**|Je nach Threadtyp, von dem es erstellt wird, kann das Objekt sowohl das Apartment\- als auch das Freethreadingmodell verwenden.|  
|**Frei**|Legt fest, dass das Objekt das Freethreadingmodell verwendet.  Das Freethreadingmodell entspricht dem Multithreaded\-Apartmentmodell.  Weitere Informationen finden Sie unter [Multithreaded Apartments](http://msdn.microsoft.com/library/windows/desktop/ms693421).|  
|**Neutral** \(nur Windows 2000\)|Legt fest, dass das Objekt den Richtlinien für Multithreadapartments entspricht, jedoch beliebige Threads ausführen kann.|  
  
 **Aggregation**  
 Gibt an, ob das Objekt die [Aggregation](http://msdn.microsoft.com/library/windows/desktop/ms686558) verwendet.  Das aggregierte Objekt entscheidet, welche Schnittstellen Clients zur Verfügung gestellt werden. Das Verfügbarmachen erfolgt auf dieselbe Weise, als ob die Schnittstellen vom aggregierten Objekt implementiert worden wären.  Die Clients des aggregierten Objekts kommunizieren ausschließlich mit diesem Objekt.  
  
|Option|Description|  
|------------|-----------------|  
|**Ja**|Gibt an, dass das Objekt aggregiert werden kann.  Der Standardwert.|  
|**Nein**|Gibt an, dass das Objekt nicht aggregiert wird.|  
|**Nur**|Gibt an, dass das Objekt aggregiert werden muss.|  
  
 **Unterstützung**  
 \(Beschreibung des Elements wird später ergänzt\)  
  
|Option|Description|  
|------------|-----------------|  
|**ISupportErrorInfo**|Richtet die Unterstützung für die [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md)\-Schnittstelle ein, sodass das Objekt Fehlerinformationen an den Client zurückgeben kann.|  
|**Verbindungspunkte**|Aktiviert Verbindungspunkte für das Objekt, indem die Klasse des Objekts von [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) abgeleitet wird.|  
|**Free\-threaded Marshaler**|Erstellt einen freethreaded Marshaler, damit die Schnittstellenzeiger zwischen Threads innerhalb desselben Prozesses effizient gemarshallt werden können.  Bei Auswahl der Threadmodelle **Beides** oder **Frei** für das Projekt verfügbar.|  
  
## Siehe auch  
 [ATL\-Assistent für Active Server Page\-Komponenten](../../atl/reference/atl-active-server-page-component-wizard.md)   
 [ATL Active Server Page Component](../../atl/reference/adding-an-atl-active-server-page-component.md)