---
title: "Optionen, ATL-Assistent f&#252;r einfache Objekte"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.simple.options"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Assistent für einfache Objekte, Optionen"
ms.assetid: 125fe179-942d-4181-8b82-33e92e1fd779
caps.latest.revision: 14
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Optionen, ATL-Assistent f&#252;r einfache Objekte
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Auf dieser Seite des ATL\-Assistenten für einfache Objekte können Sie das Objekt effizienter gestalten und Unterstützung für die Fehlerbehebung hinzufügen.  
  
 Weitere Informationen zu ATL\-Projekten und ATL\-COM\-Klassen finden Sie unter [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md).  
  
 **Threadmodell**  
 Gibt die für die Threadverwaltung verwendete Methode an.  Das Projekt verwendet standardmäßig das Threadmodell **Apartment**.  
  
 Weitere Informationen finden Sie unter [Festlegen des Threadingmodells des Projekts](../../atl/specifying-the-threading-model-for-a-project-atl.md).  
  
|Option|Description|  
|------------|-----------------|  
|`Single`|Das Objekt wird immer im primären COM\-Thread ausgeführt.  Weitere Informationen finden Sie unter [Singlethreaded Apartments](http://msdn.microsoft.com/library/windows/desktop/ms680112) und [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390).|  
|**Apartment**|Legt fest, dass das Objekt das Apartmentthreadingmodell verwendet.  Entspricht dem Singlethreadapartment.  Jedem Objekt einer Apartmentthreadkomponente wird während seiner Lebensdauer ein Apartment für den Thread zugewiesen. Für mehrere Objekte können jedoch auch mehrere Threads verwendet werden.  Jedes Apartment ist an einen bestimmten Thread gebunden und verfügt über eine Windows\-Nachrichtenverteilschleife \(Standard\).<br /><br /> Weitere Informationen finden Sie unter [Singlethreaded Apartments](http://msdn.microsoft.com/library/windows/desktop/ms680112).|  
|**Beides**|Je nach Threadtyp, von dem es erstellt wird, kann das Objekt sowohl das Apartment\- als auch das Freethreadingmodell verwenden.|  
|**Frei**|Legt fest, dass das Objekt das Freethreadingmodell verwendet.  Das Freethreadingmodell entspricht dem Multithreaded\-Apartmentmodell.  Weitere Informationen finden Sie unter [Multithreaded Apartments](http://msdn.microsoft.com/library/windows/desktop/ms693421).|  
|**Neutral** \(nur Windows 2000\)|Legt fest, dass das Objekt den Richtlinien für Multithreadapartments entspricht, jedoch beliebige Threads ausführen kann.|  
  
 **Aggregation**  
 Gibt an, ob das Objekt die [Aggregation](http://msdn.microsoft.com/library/windows/desktop/ms686558) verwendet.  Das aggregierte Objekt entscheidet, welche Schnittstellen Clients zur Verfügung gestellt werden. Das Verfügbarmachen erfolgt auf dieselbe Weise, als ob die Schnittstellen vom aggregierten Objekt implementiert worden wären.  Die Clients des aggregierten Objekts kommunizieren ausschließlich mit diesem Objekt.  
  
|Option|Description|  
|------------|-----------------|  
|Ja|Gibt an, dass das Objekt aggregiert werden kann.  Der Standardwert.|  
|Nein|Gibt an, dass das Objekt nicht aggregiert wird.|  
|Nur|Gibt an, dass das Objekt aggregiert werden muss.|  
  
 **Interface**  
 Gibt den Typ der Schnittstelle an, die vom Objekt unterstützt wird.  Das Objekt unterstützt standardmäßig eine duale Schnittstelle.  
  
|Option|Description|  
|------------|-----------------|  
|**Dual**|Gibt an, dass das Objekt eine duale Schnittstelle unterstützt \(die **vtable** des Objekts enthält benutzerdefinierte Schnittstellenfunktionen sowie `IDispatch`\-Methoden für spätes Binden\).  Ermöglicht sowohl COM\-Clients als auch [Automatisierungscontrollern](../../mfc/automation-clients.md) den Zugriff auf das Objekt.  Der Standardwert.|  
|**Benutzerdefiniert**|Gibt an, dass das Objekt eine benutzerdefinierte Schnittstelle unterstützt \(die **vtable** des Objekts enthält benutzerdefinierte Schnittstellenfunktionen\).  Eine benutzerdefinierte Schnittstelle ist, insbesondere über Prozessgrenzen hinweg, schneller als eine duale Schnittstelle.<br /><br /> -   **Automatisierungskompatibel** ermöglicht Automatisierungscontrollern, um auf ein Objekt zuzugreifen, das die benutzerdefinierte Schnittstellenunterstützung verfügt.|  
  
 **Unterstützung**  
 Gibt an, ob das Objekt über zusätzliche Unterstützung verfügt.  
  
|Option|Description|  
|------------|-----------------|  
|**ISupportErrorInfo**|Richtet die Unterstützung für die [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md)\-Schnittstelle ein, sodass das Objekt Fehlerinformationen an den Client zurückgeben kann.|  
|**Verbindungspunkte**|Aktiviert Verbindungspunkte für das Objekt, indem die Klasse des Objekts von [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) abgeleitet wird.|  
|**Free\-threaded Marshaler**|Erstellt einen freethreaded Marshaler, damit die Schnittstellenzeiger zwischen Threads innerhalb desselben Prozesses effizient gemarshallt werden können.  Verfügbar für das Objekt, das **Beides** als Threadingmodell angibt.|  
|**IObjectWithSite \(IE\-Objektunterstützung\)**|Implementiert [IObjectWithSiteImpl](../../atl/reference/iobjectwithsiteimpl-class.md) und bietet dadurch eine einfache Möglichkeit, die Kommunikation zwischen einem Objekt und seiner Site innerhalb eines Containers zu unterstützen.|  
  
## Siehe auch  
 [ATL\-Assistent für einfache Objekte](../../atl/reference/atl-simple-object-wizard.md)   
 [ATL Simple Object](../../atl/reference/adding-an-atl-simple-object.md)   
 [Probleme bei prozessinternem Serverthreading](http://msdn.microsoft.com/library/windows/desktop/ms687205)