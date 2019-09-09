---
title: Optionen, ATL-Assistent für Active Server Page-Komponenten
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.asp.options
helpviewer_keywords:
- ATL Active Server Page Component Wizard, options
ms.assetid: 54f34e26-53c7-4456-9675-cb86e356bde0
ms.openlocfilehash: c76ab7730256b007b66d54ca6753409926f7ae89
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495298"
---
# <a name="options-atl-active-server-page-component-wizard"></a>Optionen, ATL-Assistent für Active Server Page-Komponenten

Auf dieser Seite des ATL-Active Server Seiten Komponenten-Assistenten können Sie eine größere Effizienz und Fehler Unterstützung für das Objekt entwerfen.

Weitere Informationen zu ATL-Projekten und ATL-COM-Klassen finden Sie unter [ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md).

- **Threadingmodell**

   Gibt die Methode zum Verwalten von Threads an. Standardmäßig verwendet das Projekt **Apartment** Threading.

   Weitere Informationen finden Sie unter [Angeben des Threadingmodells für ein Projekt](../../atl/specifying-the-threading-model-for-a-project-atl.md).

   |Option|Beschreibung|
   |------------|-----------------|
   |**Single**|Gibt an, dass das-Objekt das einzelne Threading Modell verwendet. Im einzelnen Threading Modell wird ein Objekt immer im primären com-Thread ausgeführt. Weitere Informationen finden Sie unter [Single Thread Apartments](/windows/win32/com/single-threaded-apartments) und [InProcServer32](/windows/win32/com/inprocserver32) .|
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

- **Unterstützung**

   Zusätzliche Supportoptionen:

   |Option|Beschreibung|
   |------------|-----------------|
   |**ISupportErrorInfo**|Erstellt Unterstützung für die [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md)-Schnittstelle, damit das Objekt Fehlerinformationen an den Client zurückgeben kann.|
   |**Verbindungspunkte**|Aktiviert Verbindungspunkte für Ihr Objekt, indem die Klasse des Objekts von [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)abgeleitet wird.|
   |**Frei Thread-Mars Haller**|Erstellt ein Freethread-Mars Haller-Objekt zum effizienten Mars Hallen von Schnittstellen Zeigern zwischen Threads im gleichen Prozess. Verfügbar für-Objekte, die entweder **sowohl** als **auch als** Threading Modell angeben.|

## <a name="see-also"></a>Siehe auch

[ATL-Assistent für Active Server Page-Komponenten](../../atl/reference/atl-active-server-page-component-wizard.md)<br/>
[ATL Active Server Page-Komponente](../../atl/reference/adding-an-atl-active-server-page-component.md)
