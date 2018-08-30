---
title: Optionen, ATL Active Server Page-Komponenten-Assistent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.asp.options
dev_langs:
- C++
helpviewer_keywords:
- ATL Active Server Page Component Wizard, options
ms.assetid: 54f34e26-53c7-4456-9675-cb86e356bde0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 29a5209eb05958861a5c021f48bff1bf36654115
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205443"
---
# <a name="options-atl-active-server-page-component-wizard"></a>Optionen, ATL-Assistent für Active Server Page-Komponenten
Verwenden Sie auf dieser Seite des ATL-Assistenten für Active Server Page-Komponente, um Effizienz und Fehler-Unterstützung für das Objekt zu entwerfen.  
  
 Weitere Informationen zu ATL-Projekte und ATL-COM-Klassen finden Sie unter [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md).  
  
 **Threading-Modell**  
 Gibt die Methode für die Verwaltung von Threads. Standardmäßig verwendet das Projekt **Apartment** threading.  
  
 Finden Sie unter [angeben des Projekts. Threading-Modell](../../atl/specifying-the-threading-model-for-a-project-atl.md) für Weitere Informationen.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Single**|Gibt an, dass das Objekt, das einzelne threading-Modell verwendet. Im einzelnen threading-Modell wird ein Objekt immer im primären COM-Thread ausgeführt. Finden Sie unter [Single-Threaded-Apartments](/windows/desktop/com/single-threaded-apartments) und [InprocServer32](/windows/desktop/com/inprocserver32) für Weitere Informationen.|  
|**Apartment**|Gibt an, dass das Objekt Apartmentthreading für Anwendungen verwendet. Äquivalent zu einzelnen Threadapartment. Jedes Objekt einer Apartmentthread-Komponente wird ein Apartment für den Thread, für die Lebensdauer des Objekts zugewiesen. mehrere Threads können jedoch für mehrere Objekte verwendet werden. Jedes Apartment an einem bestimmten Thread gebunden ist und verfügt über ein Windows-Nachrichtensystem (Standard).<br /><br /> Finden Sie unter [Single-Threaded-Apartments](/windows/desktop/com/single-threaded-apartments) für Weitere Informationen.|  
|**Beide**|Gibt an, dass das Objekt aus, welche Art von einem Thread Erstellung je Apartment oder freies threading, verwenden kann.|  
|**kostenlos**|Gibt an, dass das Objekt freies threading verwendet. Freies threading ist gleichbedeutend mit einem multithread Apartmentmodell. Finden Sie unter [Multithread-Apartments](/windows/desktop/com/multithreaded-apartments) für Weitere Informationen.|  
|**Neutral**|Gibt an, dass das Objekt den Richtlinien für Multithread-Apartments folgt, jedoch können für jede Art von Thread durchgeführt.|  
  
 **Aggregation**  
 Gibt an, ob das Objekt verwendet [Aggregation](/windows/desktop/com/aggregation). Das Aggregatobjekt wählt die Schnittstellen verwenden, um für Clients verfügbar zu machen, und die Schnittstellen werden verfügbar gemacht, als sei das Aggregatobjekt diese implementiert. Clients des aggregierten Objekts kommunizieren nur mit aggregierten Objekts.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Ja**|Gibt an, dass das Objekt aggregiert werden kann. Der Standardwert.|  
|**No**|Gibt an, dass das Objekt nicht aggregiert werden.|  
|**Nur**|Gibt an, dass das Objekt aggregiert werden muss.|  
  
 **Unterstützung**  
 (Elementbeschreibung hinzugefügt werden)  
  
|Option|Beschreibung|  
|------------|-----------------|  
|`ISupportErrorInfo`|Stellt die Unterstützung der [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) Schnittstelle, damit das Objekt Fehlerinformationen an den Client zurückgeben kann.|  
|**Verbindungspunkte**|Ermöglicht der Verbindungspunkte für das Objekt, indem Sie machen die Klasse des Objekts abgeleitet [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md).|  
|**Freethread-Marshaller**|Erstellt ein Freethread-Marshaller-Objekt zum Marshallen der Schnittstellenzeiger effizient zwischen Threads im selben Prozess. Verfügbar für das Objekt angeben **sowohl** oder **Free** als Threadingmodell.|  
  
## <a name="see-also"></a>Siehe auch  
 [ATL Active Server Page-Komponenten-Assistent](../../atl/reference/atl-active-server-page-component-wizard.md)   
 [ATL Active Server Page-Komponente](../../atl/reference/adding-an-atl-active-server-page-component.md)

