---
title: "Optionen, ATL-Assistent für Active Server Page-Komponenten | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.codewiz.class.atl.asp.options
dev_langs: C++
helpviewer_keywords: ATL Active Server Page Component Wizard, options
ms.assetid: 54f34e26-53c7-4456-9675-cb86e356bde0
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6564b340458ae7e9a8e137d2338ba68b3e729a0f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="options-atl-active-server-page-component-wizard"></a>Optionen, ATL-Assistent für Active Server Page-Komponenten
Verwenden Sie diese Seite des ATL-Assistenten für Active Server Page-Komponente, um Effizienz und Fehler-Unterstützung für das Objekt zu entwerfen.  
  
 Weitere Informationen über ATL-Projekte und ATL-COM-Klassen finden Sie unter [ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md).  
  
 **Threadmodell**  
 Gibt die Methode für die Verwaltung von Threads an. Standardmäßig verwendet das Projekt **Apartment** threading.  
  
 Finden Sie unter [angeben des Threadingmodells des Projekts](../../atl/specifying-the-threading-model-for-a-project-atl.md) für Weitere Informationen.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|`Single`|Gibt an, dass das Objekt der einzelne Threadingmodell verwendet. In den einzelnen Threadingmodell wird ein Objekt immer im primären COM-Thread ausgeführt. Finden Sie unter [Singlethreaded Apartments](http://msdn.microsoft.com/library/windows/desktop/ms680112) und [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) für Weitere Informationen.|  
|**Apartment**|Gibt an, dass das Objekt das Apartmentthreadingmodell verwendet. Entspricht dem Threadapartment. Jedes Objekt ein Singlethread-Apartment-Komponente ist ein Apartment für den Thread, für die Lebensdauer des Objekts zugewiesen. Allerdings können mehrere Threads für mehrere Objekte verwendet werden. Jedes Apartment für einen bestimmten Thread gebunden ist, und es wurde ein Nachrichtensystem für Windows (Standard).<br /><br /> Finden Sie unter [Singlethreaded Apartments](http://msdn.microsoft.com/library/windows/desktop/ms680112) für Weitere Informationen.|  
|**Beide**|Gibt an, dass das Objekt Apartment oder Freethreadings, kann je nachdem, welche Art von einem Thread erstellt werden wird.|  
|**Frei**|Gibt an, dass das Objekt Freethreadings verwendet. Freethreadings ist gleichbedeutend mit einem multithread Apartmentmodell. Finden Sie unter [Multithread-Apartments](http://msdn.microsoft.com/library/windows/desktop/ms693421) für Weitere Informationen.|  
|**Neutrale** (nur Windows 2000)|Gibt an, dass das Objekt die Richtlinien für Multithread-Apartments folgt, aber sie können für jede Art von Thread ausgeführt.|  
  
 **Aggregation**  
 Gibt an, ob das Objekt verwendet [Aggregation](http://msdn.microsoft.com/library/windows/desktop/ms686558). Das Aggregatobjekt wählt der Schnittstellen verwenden, um für Clients verfügbar machen, und die Schnittstellen werden verfügbar gemacht, als wäre das Aggregatobjekt werden implementiert. Clients, der das Aggregatobjekt kommunizieren nur mit dem Object des Aggregats.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Ja**|Gibt an, dass das Objekt aggregiert werden kann. Der Standardwert.|  
|**No**|Gibt an, dass das Objekt nicht aggregiert wird.|  
|**Nur**|Gibt an, dass das Objekt aggregiert werden muss.|  
  
 **Unterstützung**  
 (Beschreibung Element hinzugefügt werden)  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**ISupportErrorInfo**|Unterstützung für die [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) Benutzeroberfläche, sodass das Objekt Fehlerinformationen an den Client zurückgegeben werden kann.|  
|**Verbindungspunkte**|Ermöglicht die Verbindungspunkte für Ihr Objekt durch machen die Klasse des Objekts abgeleitet [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md).|  
|**Freethread-Marshaller**|Erstellt ein Freethread-Marshaller-Objekt zum Marshallen von Schnittstellenzeigern effizient zwischen Threads im selben Prozess. Verfügbar für das Objekt entweder **beide** oder **frei** als Threadingmodell.|  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-Assistent für Active Server Page-Komponenten](../../atl/reference/atl-active-server-page-component-wizard.md)   
 [ATL Active Server Page-Komponenten](../../atl/reference/adding-an-atl-active-server-page-component.md)

