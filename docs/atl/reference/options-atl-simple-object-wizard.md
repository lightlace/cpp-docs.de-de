---
title: Optionen, ATL-Assistent für einfache Objekte | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.simple.options
dev_langs:
- C++
helpviewer_keywords:
- ATL Simple Object Wizard, options
ms.assetid: 125fe179-942d-4181-8b82-33e92e1fd779
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ffc38f5359b68b90f91a2643e1fbaa743a94e559
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="options-atl-simple-object-wizard"></a>Optionen, ATL-Assistent für einfache Objekte
Verwenden Sie diese Seite von der ATL-Assistent für einfache Objekte, um Effizienz und Fehler-Unterstützung für das Objekt zu entwerfen.  
  
 Weitere Informationen über ATL-Projekte und ATL-COM-Klassen finden Sie unter [ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md).  
  
 **Threadmodell**  
 Gibt die Methode für die Verwaltung von Threads an. Standardmäßig verwendet das Projekt **Apartment** threading.  
  
 Finden Sie unter [angeben des Threadingmodells des Projekts](../../atl/specifying-the-threading-model-for-a-project-atl.md) für Weitere Informationen.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|`Single`|Gibt an, dass das Objekt immer im primären COM-Thread ausgeführt wird. Finden Sie unter [Singlethreaded Apartments](http://msdn.microsoft.com/library/windows/desktop/ms680112) und [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) für Weitere Informationen.|  
|**Apartment**|Gibt an, dass das Objekt das Apartmentthreadingmodell verwendet. Entspricht dem Threadapartment. Jedes Objekt ein Singlethread-Apartment-Komponente ist ein Apartment für den Thread, für die Lebensdauer des Objekts zugewiesen. Allerdings können mehrere Threads für mehrere Objekte verwendet werden. Jedes Apartment für einen bestimmten Thread gebunden ist, und es wurde ein Nachrichtensystem für Windows (Standard).<br /><br /> Finden Sie unter [Singlethreaded Apartments](http://msdn.microsoft.com/library/windows/desktop/ms680112) für Weitere Informationen.|  
|**Beide**|Gibt an, dass das Objekt Apartment oder Freethreadings, kann je nachdem, welche Art von einem Thread erstellt werden wird.|  
|**Frei**|Gibt an, dass das Objekt Freethreadings verwendet. Freethreadings ist gleichbedeutend mit einem multithread Apartmentmodell. Finden Sie unter [Multithread-Apartments](http://msdn.microsoft.com/library/windows/desktop/ms693421) für Weitere Informationen.|  
|**Neutral**|Gibt an, dass das Objekt die Richtlinien für Multithread-Apartments folgt, aber sie können für jede Art von Thread ausgeführt.|  
  
 **Aggregation**  
 Gibt an, ob das Objekt verwendet [Aggregation](http://msdn.microsoft.com/library/windows/desktop/ms686558). Das Aggregatobjekt wählt der Schnittstellen verwenden, um für Clients verfügbar machen, und die Schnittstellen werden verfügbar gemacht, als wäre das Aggregatobjekt werden implementiert. Clients, der das Aggregatobjekt kommunizieren nur mit dem Object des Aggregats.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|Ja|Gibt an, dass das Objekt aggregiert werden kann. Der Standardwert.|  
|Nein|Gibt an, dass das Objekt nicht aggregiert wird.|  
|Nur|Gibt an, dass das Objekt aggregiert werden muss.|  
  
 **Interface**  
 Gibt den Typ der Schnittstelle, die das Objekt unterstützt. Das Objekt unterstützt standardmäßig eine duale Schnittstelle.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Dual**|Gibt an, dass das Objekt eine duale Schnittstelle unterstützt (die Vtable hat benutzerdefinierte Oberfläche Funktionen plus späte Bindung `IDispatch` Methoden). Ermöglicht sowohl COM-Clients und [Automatisierungscontroller](../../mfc/automation-clients.md) Zugriff auf das Objekt. Der Standardwert.|  
|**Benutzerdefiniert**|Gibt an, dass das Objekt eine benutzerdefinierte Schnittstelle unterstützt (die Vtable enthält benutzerdefinierte Oberfläche Funktionen). Eine benutzerdefinierte Schnittstelle kann insbesondere über Prozessgrenzen hinweg schneller als eine duale Schnittstelle sein.<br /><br /> -   **Automatisierung kompatibel** Automatisierungscontroller ermöglicht Zugriff auf ein Objekt, das die benutzerdefinierte Schnittstelle unterstützt.|  
  
 **Unterstützung**  
 Gibt die zusätzliche Unterstützung für das Objekt an.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**ISupportErrorInfo**|Unterstützung für die [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) Benutzeroberfläche, sodass das Objekt Fehlerinformationen an den Client zurückgegeben werden kann.|  
|**Verbindungspunkte**|Ermöglicht die Verbindungspunkte für Ihr Objekt durch machen die Klasse des Objekts abgeleitet [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md).|  
|**Freethread-Marshaller**|Erstellt ein Freethread-Marshaller-Objekt zum Marshallen von Schnittstellenzeigern effizient zwischen Threads im selben Prozess. Verfügbar, mit der Angabe von Objekt **sowohl** als Threadingmodell.|  
|**"IObjectWithSite" (Unterstützung von Internet Explorer-Objekt)**|Implementiert [IObjectWithSiteImpl](../../atl/reference/iobjectwithsiteimpl-class.md), stellt eine einfache Möglichkeit, um die Kommunikation zwischen einem Objekt und seinem Standort in einem Container zu unterstützen.|  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-Assistent für einfache Objekte](../../atl/reference/atl-simple-object-wizard.md)   
 [Einfaches ATL-Objekt](../../atl/reference/adding-an-atl-simple-object.md)   
 [In-Process-Server Threadingprobleme](http://msdn.microsoft.com/library/windows/desktop/ms687205)

