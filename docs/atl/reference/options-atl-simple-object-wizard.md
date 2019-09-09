---
title: Optionen, ATL-Assistent für einfache Objekte
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.simple.options
helpviewer_keywords:
- ATL Simple Object Wizard, options
ms.assetid: 125fe179-942d-4181-8b82-33e92e1fd779
ms.openlocfilehash: e92f4909907645fc317590fbcc3601887346c642
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495159"
---
# <a name="options-atl-simple-object-wizard"></a>Optionen, ATL-Assistent für einfache Objekte

Verwenden Sie diese Seite des ATL-Assistenten für einfache Objekte, um eine größere Effizienz und Fehler Unterstützung für das-Objekt zu entwerfen.

Weitere Informationen zu ATL-Projekten und ATL-COM-Klassen finden Sie unter [ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md).

- **Threadingmodell**

   Gibt die Methode zum Verwalten von Threads an. Standardmäßig verwendet das Projekt **Apartment** Threading.

   Weitere Informationen finden Sie unter [Angeben des Threadingmodells für ein Projekt](../../atl/specifying-the-threading-model-for-a-project-atl.md).

   |Option|Beschreibung|
   |------------|-----------------|
   |**Single**|Gibt an, dass das Objekt immer im primären com-Thread ausgeführt wird. Weitere Informationen finden Sie unter [Single Thread Apartments](/windows/win32/com/single-threaded-apartments) und [InProcServer32](/windows/win32/com/inprocserver32) .|
   |**Apartment**|Gibt an, dass das Objekt Apartment Threading verwendet. Äquivalent zu Single Thread Apartment. Jedem Objekt einer Apartment Thread Komponente wird für die Lebensdauer des Objekts ein Apartment für den Thread zugewiesen. Es können jedoch mehrere Threads für mehrere-Objekte verwendet werden. Jedes Apartment ist mit einem bestimmten Thread verknüpft und verfügt über eine Windows-Nachrichten Pumpe (Standard).<br /><br /> Weitere Informationen finden Sie unter [Single Thread-Apartments](/windows/win32/com/single-threaded-apartments) .|
   |**Zwar**|Gibt an, dass das-Objekt je nach Art des erstellten Threads entweder Apartment oder freies Threading verwenden kann.|
   |**Kosten**|Gibt an, dass das Objekt freies Threading verwendet. Ein kostenloses Threading entspricht einem Multithread-Apartment Modell. Weitere Informationen finden Sie unter [Multithread-Apartments](/windows/win32/com/multithreaded-apartments) .|
   |**Neutral**|Gibt an, dass das-Objekt den Richtlinien für multithreadwohnungen folgt, aber es kann in jeder Art von Thread ausgeführt werden.|

- **Aggregation**

   Gibt an, ob das Objekt [Aggregationen](/windows/win32/com/aggregation)verwendet. Das Aggregat Objekt wählt aus, welche Schnittstellen für Clients verfügbar gemacht werden, und die Schnittstellen werden so verfügbar gemacht, als ob das Aggregat Objekt Sie implementiert hat. Clients des Aggregat Objekts kommunizieren nur mit dem Aggregat Objekt.

   |Option|Beschreibung|
   |------------|-----------------|
   |**Ja**|Gibt an, dass das Objekt aggregiert werden kann. Der Standardwert.|
   |**No**|Gibt an, dass das Objekt nicht aggregiert wird.|
   |**Nur**|Gibt an, dass das Objekt aggregiert werden muss.|

- **Interface**

   Gibt den Typ der Schnittstelle an, die vom Objekt unterstützt wird. Standardmäßig unterstützt das Objekt eine duale Schnittstelle.

   |Option|Beschreibung|
   |------------|-----------------|
   |**Dual**|Gibt an, dass das-Objekt eine duale Schnittstelle unterstützt (die Vtable verfügt über Benutzer `IDispatch` definierte Schnittstellen Funktionen und Methoden mit späterer Bindung). Ermöglicht sowohl com-Clients als auch [Automatisierungs Controllern](../../mfc/automation-clients.md) den Zugriff auf das Objekt. Der Standardwert.|
   |**Benutzerdefiniert**|Gibt an, dass das Objekt eine benutzerdefinierte Schnittstelle unterstützt (seine vtable enthält benutzerdefinierte Schnittstellenfunktionen). Eine benutzerdefinierte Schnittstelle kann schneller sein als eine duale Schnittstelle, insbesondere über Prozessgrenzen hinweg.<br /><br /> - **Automatisierungs kompatibel** Ermöglicht Automatisierungs Controllern den Zugriff auf ein Objekt, das über die benutzerdefinierte Schnittstellen Unterstützung verfügt.|

- **Unterstützung**

   Gibt zusätzliche Unterstützung für das-Objekt an.

   |Option|Beschreibung|
   |------------|-----------------|
   |**ISupportErrorInfo**|Erstellt Unterstützung für die [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md)-Schnittstelle, damit das Objekt Fehlerinformationen an den Client zurückgeben kann.|
   |**Verbindungspunkte**|Aktiviert Verbindungspunkte für Ihr Objekt, indem die Klasse des Objekts von [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)abgeleitet wird.|
   |**Frei Thread-Mars Haller**|Erstellt ein Freethread-Mars Haller-Objekt zum effizienten Mars Hallen von Schnittstellen Zeigern zwischen Threads im gleichen Prozess. Verfügbar für ein Objekt, das **beide** als Threading Modell angibt.|
   |**IObjectWithSite** (IE-Objekt Unterstützung)|Implementiert [IObjectWithSiteImpl](../../atl/reference/iobjectwithsiteimpl-class.md), das eine einfache Möglichkeit bietet, die Kommunikation zwischen einem Objekt und seiner Website in einem Container zu unterstützen.|

## <a name="see-also"></a>Siehe auch

[ATL-Assistent für einfache Objekte](../../atl/reference/atl-simple-object-wizard.md)<br/>
[ATL Simple Object (Einfaches ATL-Objekt)](../../atl/reference/adding-an-atl-simple-object.md)<br/>
[Threading Probleme im Prozess internen Server](/windows/win32/com/in-process-server-threading-issues)
