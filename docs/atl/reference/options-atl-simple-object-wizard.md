---
title: Optionen, ATL-Assistent für einfache Objekte | Microsoft-Dokumentation
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
ms.openlocfilehash: 7a337ceffbbfb1577b58fea2f60213cd79052b00
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861368"
---
# <a name="options-atl-simple-object-wizard"></a>Optionen, ATL-Assistent für einfache Objekte

Verwenden Sie auf dieser Seite des der ATL-Assistent für einfache Objekte, um Effizienz und Fehler-Unterstützung für das Objekt zu entwerfen.

Weitere Informationen zu ATL-Projekte und ATL-COM-Klassen finden Sie unter [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md).

- **Threading-Modell**

   Gibt die Methode für die Verwaltung von Threads. Standardmäßig verwendet das Projekt **Apartment** threading.

   Finden Sie unter [angeben des Projekts. Threading-Modell](../../atl/specifying-the-threading-model-for-a-project-atl.md) für Weitere Informationen.

   |Option|Beschreibung|
   |------------|-----------------|
   |**Single**|Gibt an, dass das Objekt immer im primären COM-Thread ausgeführt wird. Finden Sie unter [Single-Threaded-Apartments](/windows/desktop/com/single-threaded-apartments) und [InprocServer32](/windows/desktop/com/inprocserver32) für Weitere Informationen.|
   |**Apartment**|Gibt an, dass das Objekt Apartmentthreading für Anwendungen verwendet. Äquivalent zu einzelnen Threadapartment. Jedes Objekt einer Apartmentthread-Komponente wird ein Apartment für den Thread, für die Lebensdauer des Objekts zugewiesen. mehrere Threads können jedoch für mehrere Objekte verwendet werden. Jedes Apartment an einem bestimmten Thread gebunden ist und verfügt über ein Windows-Nachrichtensystem (Standard).<br /><br /> Finden Sie unter [Single-Threaded-Apartments](/windows/desktop/com/single-threaded-apartments) für Weitere Informationen.|
   |**Beide**|Gibt an, dass das Objekt aus, welche Art von einem Thread Erstellung je Apartment oder freies threading, verwenden kann.|
   |**kostenlos**|Gibt an, dass das Objekt freies threading verwendet. Freies threading ist gleichbedeutend mit einem multithread Apartmentmodell. Finden Sie unter [Multithread-Apartments](/windows/desktop/com/multithreaded-apartments) für Weitere Informationen.|
   |**Neutral**|Gibt an, dass das Objekt den Richtlinien für Multithread-Apartments folgt, jedoch können für jede Art von Thread durchgeführt.|

- **Aggregation**

   Gibt an, ob das Objekt verwendet [Aggregation](/windows/desktop/com/aggregation). Das Aggregatobjekt wählt die Schnittstellen verwenden, um für Clients verfügbar zu machen, und die Schnittstellen werden verfügbar gemacht, als sei das Aggregatobjekt diese implementiert. Clients des aggregierten Objekts kommunizieren nur mit aggregierten Objekts.

   |Option|Beschreibung|
   |------------|-----------------|
   |**Ja**|Gibt an, dass das Objekt aggregiert werden kann. Der Standardwert.|
   |**No**|Gibt an, dass das Objekt nicht aggregiert werden.|
   |**Nur**|Gibt an, dass das Objekt aggregiert werden muss.|

- **Interface**

   Gibt den Typ der Schnittstelle, die das Objekt unterstützt. Das Objekt unterstützt standardmäßig eine duale Schnittstelle.

   |Option|Beschreibung|
   |------------|-----------------|
   |**Dual**|Gibt an, dass das Objekt eine duale Schnittstelle unterstützt (die Vtable besitzt, benutzerdefinierte Funktionen sowie die späte Bindung `IDispatch` Methoden). Ermöglicht es COM-Clients und [Automatisierungscontroller](../../mfc/automation-clients.md) auf das Objekt zuzugreifen. Der Standardwert.|
   |**Benutzerdefiniert**|Gibt an, dass das Objekt eine benutzerdefinierte Schnittstelle unterstützt (die Vtable hat benutzerdefinierte Funktionen). Eine benutzerdefinierte Schnittstelle kann vor allem über Prozessgrenzen hinweg schneller als das duale Schnittstelle sein.<br /><br /> - **Automatisierungskompatibel** Automatisierungscontroller ermöglicht Zugriff auf ein Objekt, das die benutzerdefinierte Schnittstelle unterstützt.|

- **Unterstützung**

   Gibt zusätzliche Unterstützung für das Objekt an.

   |Option|Beschreibung|
   |------------|-----------------|
   |**ISupportErrorInfo**|Stellt die Unterstützung der [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) Schnittstelle, damit das Objekt Fehlerinformationen an den Client zurückgeben kann.|
   |**Verbindungspunkte**|Ermöglicht der Verbindungspunkte für das Objekt, indem Sie machen die Klasse des Objekts abgeleitet [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md).|
   |**Freethread-Marshaller**|Erstellt ein Freethread-Marshaller-Objekt zum Marshallen der Schnittstellenzeiger effizient zwischen Threads im selben Prozess. Zur Angabe der Objekt **sowohl** als Threadingmodell.|
   |**IObjectWithSite** (Unterstützung für Internet Explorer-Objekt)|Implementiert [IObjectWithSiteImpl](../../atl/reference/iobjectwithsiteimpl-class.md), dem bietet es sich um eine einfache Möglichkeit, um die Kommunikation zwischen einem Objekt und seinem Standort in einem Container zu unterstützen.|

## <a name="see-also"></a>Siehe auch

[ATL-Assistent für einfache Objekte](../../atl/reference/atl-simple-object-wizard.md)<br/>
[ATL Simple Object (Einfaches ATL-Objekt)](../../atl/reference/adding-an-atl-simple-object.md)<br/>
[In-Process-Server, Threadingprobleme](/windows/desktop/com/in-process-server-threading-issues)

