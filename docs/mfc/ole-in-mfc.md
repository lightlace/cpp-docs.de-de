---
title: OLE in MFC | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, OLE and
- OLE items
- OLE applications [MFC], about OLE
- OLE [MFC]
- OLE containers [MFC], about OLE
- applications [OLE], about OLE
- OLE component object model (COM)
ms.assetid: 5193479d-1239-4697-aea4-e82f92c707ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c6c39c47762f4ac61e3192d5d3ecef997c3078bc
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204113"
---
# <a name="ole-in-mfc"></a>OLE in MFC
In diesen Artikeln wird erläutert, die Grundlagen der Verwendung von MFC OLE-Programmierung. MFC bietet die einfachste Möglichkeit zum Schreiben von Programmen, die OLE verwenden:  
  
-   Verwenden Sie OLE visuelle Bearbeitung (direkte Aktivierung).  
  
-   Als OLE-Container oder Server zu arbeiten.  
  
-   Um Drag & Drop-Funktionalität zu implementieren.  
  
-   Mit Datums-und Uhrzeitdaten zu arbeiten.  
  
-   Zum Verwalten der Statusdaten von MFC exportiert die Module, einschließlich Einstiegspunkte für DLL-Funktion, OLE/COM-schnittstelleneingabepunkte und Einstiegspunkte für Fensterprozeduren.  
  
 Sie können auch [Automation](../mfc/automation.md).  
  
> [!NOTE]
>  Der Begriff, den OLE gibt an, die-Technologien im Zusammenhang mit verlinken und einbetten, einschließlich der OLE-Container, OLE-Server, OLE-Elemente, die direkte Aktivierung (oder visuelle Bearbeitung) Tracker, Drag & drop und Zusammenführen von Menüs. Der Begriff bezieht sich aktiv auf dem Component Object Model (COM) und COM-basierte Objekte wie z. B. ActiveX-Steuerelemente. OLE-Automatisierung ist jetzt als "Automatisierung" bezeichnet.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [OLE-Hintergrund](../mfc/ole-background.md)  
 Beschreibt OLE und enthält grundlegende Informationen dazu, wie es funktioniert.  
  
 [Activation (Aktivierung)](../mfc/activation-cpp.md)  
 Beschreibt die Rolle der Aktivierung bei der Bearbeitung von OLE-Elementen.  
  
 [Container](../mfc/containers.md)  
 Enthält Links zur Verwendung von OLE Container.  
  
 [Datenobjekte und Datenquellen](../mfc/data-objects-and-data-sources-ole.md)  
 Enthält Links zu Themen, in denen die Verwendung der `COleDataObject` und `COleDataSource` Klassen.  
  
 [Drag & Drop](../mfc/drag-and-drop-ole.md)  
 Erläutert die Verwendung von kopieren und Einfügen mit OLE.  
  
 [OLE-Menüs und Ressourcen](../mfc/menus-and-resources-ole.md)  
 Erläutert die Verwendung von Menüs und Ressourcen in MFC-OLE-dokumentanwendungen.  
  
 [Registrierung](../mfc/registration.md)  
 Erläutert, Installation und Server-Initialisierung.  
  
 [Server](../mfc/servers.md)  
 Beschreibt, wie OLE Elemente (oder Komponenten) für die Verwendung von containeranwendungen zu erstellen.  
  
 [Tracker](../mfc/trackers.md)  
 Enthält Informationen über die `CRectTracker` Klasse, die eine grafische Benutzeroberfläche zum Aktivieren der Benutzerinteraktion mit OLE-Client-Elemente bereitstellt.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Verbindungspunkte](../mfc/connection-points.md)  
 Erläutert das Implementieren von Verbindungspunkten (früher als OLE-Verbindungspunkte) unter Verwendung der MFC-Klassen `CCmdTarget` und `CConnectionPoint`.  
  
 [Container/Server-COM-Komponenten](../mfc/containers-advanced-features.md)  
 Beschreibt die erforderlichen Schritte zum Optionaler erweiterter Features in vorhandenen containeranwendungen zu integrieren.  
  
 [Das Component Object Model](/windows/desktop/com/the-component-object-model)  
 Beschreibt die Verwendung von OLE ohne MFC.  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)

