---
title: OLE in MFC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, OLE and
- OLE items
- OLE applications [MFC], about OLE
- OLE [MFC]
- OLE containers [MFC], about OLE
- applications [OLE], about OLE
- OLE component object model (COM)
ms.assetid: 5193479d-1239-4697-aea4-e82f92c707ab
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c2a7fcd7db19d9dcc6e12c351a3fd55f0e67b118
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ole-in-mfc"></a>OLE in MFC
Dieser Artikel erläutert die Grundlagen der OLE-Programmierung mit MFC. MFC bietet die einfachste Möglichkeit, Programme zu schreiben, die OLE verwenden:  
  
-   Um OLE visuelle Bearbeitung (direkte Aktivierung) zu verwenden.  
  
-   Als OLE-Container oder Servern zu funktionieren.  
  
-   Drag & Drop-Funktionalität zu implementieren.  
  
-   Mit Datums-und Uhrzeitdaten arbeiten zu können.  
  
-   Zum Verwalten der Statusdaten von MFC exportiert Module, einschließlich Einstiegspunkte für DLL-Funktionen, OLE/COM-schnittstelleneingabepunkte und Einstiegspunkte für Fensterprozeduren.  
  
 Sie können auch [Automatisierung](../mfc/automation.md) oder [Remoteautomatisierung](../mfc/remote-automation.md) ein anderes Programm von Ihrem Programm ausgeführt werden.  
  
> [!NOTE]
>  Der Begriff OLE kennzeichnet die Technologien zugeordneten verlinken und einbetten, z. B. OLE-Container, OLE-Server, OLE-Elemente, direkte Aktivierung (oder die visuelle Bearbeitung), Rahmenstile, Drag & drop und Zusammenführen von Menüs. Der Begriff bezieht sich aktiv auf dem Component Object Model (COM) und COM-basierte Objekte wie ActiveX-Steuerelemente. OLE-Automatisierung heißt jetzt Automatisierung.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [OLE-Hintergrund](../mfc/ole-background.md)  
 Beschreibt OLE und enthält grundlegende Informationen dazu, wie er funktioniert.  
  
 [Activation (Aktivierung)](../mfc/activation-cpp.md)  
 Beschreibt die Rolle der Aktivierung bei der Bearbeitung von OLE-Elementen.  
  
 [Container](../mfc/containers.md)  
 Enthält Links zu mithilfe von in der OLE-Container.  
  
 [Datenobjekte und Datenquellen](../mfc/data-objects-and-data-sources-ole.md)  
 Enthält Links zu Themen, in denen die Verwendung der `COleDataObject` und `COleDataSource` Klassen.  
  
 [Drag & Drop](../mfc/drag-and-drop-ole.md)  
 Erläutert die Verwendung von kopieren und Einfügen mit OLE.  
  
 [OLE-Menüs und Ressourcen](../mfc/menus-and-resources-ole.md)  
 Erläutert die Verwendung von Menüs und Ressourcen in MFC-OLE-dokumentanwendungen.  
  
 [Registrierung](../mfc/registration.md)  
 Erläutert Serverinstallation und -Initialisierung.  
  
 [Server](../mfc/servers.md)  
 Beschreibt, wie OLE Elemente (oder Komponenten) für die Verwendung von containeranwendungen zu erstellen.  
  
 [Tracker](../mfc/trackers.md)  
 Enthält Informationen über die `CRectTracker` Klasse, die eine grafische Benutzeroberfläche zum Aktivieren von Benutzern für die Interaktion mit OLE-Clientelemente bereitstellt.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Verbindungspunkte](../mfc/connection-points.md)  
 Verbindungspunkte (früher als OLE-Verbindungspunkte bezeichnet) implementieren erläutert die MFC-Klassen mit `CCmdTarget` und `CConnectionPoint`.  
  
 [Container/Server-COM-Komponenten](../mfc/containers-advanced-features.md)  
 Beschreibt die erforderlichen Schritte zum optionale erweiterte Funktionen in vorhandenen Container-Anwendungen zu integrieren.  
  
 [Das Component Object Model](http://msdn.microsoft.com/library/windows/desktop/ms694363)  
 Beschreibt die Verwendung von OLE ohne MFC.  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)

