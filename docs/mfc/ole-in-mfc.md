---
title: OLE in MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, OLE and
- OLE items
- OLE applications [MFC], about OLE
- OLE [MFC]
- OLE containers [MFC], about OLE
- applications [OLE], about OLE
- OLE component object model (COM)
ms.assetid: 5193479d-1239-4697-aea4-e82f92c707ab
ms.openlocfilehash: 09d80e7c45875ad2e6ed8b599d4e01d2110d562f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378315"
---
# <a name="ole-in-mfc"></a>OLE in MFC

In diesen Artikeln wird erläutert, die Grundlagen der Verwendung von MFC OLE-Programmierung. MFC bietet die einfachste Möglichkeit zum Schreiben von Programmen, die OLE verwenden:

- Verwenden Sie OLE visuelle Bearbeitung (direkte Aktivierung).

- Als OLE-Container oder Server zu arbeiten.

- Um Drag & Drop-Funktionalität zu implementieren.

- Mit Datums-und Uhrzeitdaten zu arbeiten.

- Zum Verwalten der Statusdaten von MFC exportiert die Module, einschließlich Einstiegspunkte für DLL-Funktion, OLE/COM-schnittstelleneingabepunkte und Einstiegspunkte für Fensterprozeduren.

Sie können auch [Automation](../mfc/automation.md).

> [!NOTE]
>  Der Begriff, den OLE gibt an, die-Technologien im Zusammenhang mit verlinken und einbetten, einschließlich der OLE-Container, OLE-Server, OLE-Elemente, die direkte Aktivierung (oder visuelle Bearbeitung) Tracker, Drag & drop und Zusammenführen von Menüs. Der Begriff bezieht sich aktiv auf dem Component Object Model (COM) und COM-basierte Objekte wie z. B. ActiveX-Steuerelemente. OLE-Automatisierung ist jetzt als "Automatisierung" bezeichnet.

## <a name="in-this-section"></a>In diesem Abschnitt

[OLE-Hintergrund](../mfc/ole-background.md)<br/>
Beschreibt OLE und enthält grundlegende Informationen dazu, wie es funktioniert.

[Activation (Aktivierung)](../mfc/activation-cpp.md)<br/>
Beschreibt die Rolle der Aktivierung bei der Bearbeitung von OLE-Elementen.

[Container](../mfc/containers.md)<br/>
Enthält Links zur Verwendung von OLE Container.

[Datenobjekte und Datenquellen](../mfc/data-objects-and-data-sources-ole.md)<br/>
Enthält Links zu Themen, in denen die Verwendung der `COleDataObject` und `COleDataSource` Klassen.

[Drag & Drop](../mfc/drag-and-drop-ole.md)<br/>
Erläutert die Verwendung von kopieren und Einfügen mit OLE.

[OLE-Menüs und Ressourcen](../mfc/menus-and-resources-ole.md)<br/>
Erläutert die Verwendung von Menüs und Ressourcen in MFC-OLE-dokumentanwendungen.

[Registrierung](../mfc/registration.md)<br/>
Erläutert, Installation und Server-Initialisierung.

[Server](../mfc/servers.md)<br/>
Beschreibt, wie OLE Elemente (oder Komponenten) für die Verwendung von containeranwendungen zu erstellen.

[Tracker](../mfc/trackers.md)<br/>
Enthält Informationen über die `CRectTracker` Klasse, die eine grafische Benutzeroberfläche zum Aktivieren der Benutzerinteraktion mit OLE-Client-Elemente bereitstellt.

## <a name="related-sections"></a>Verwandte Abschnitte

[Verbindungspunkte](../mfc/connection-points.md)<br/>
Erläutert das Implementieren von Verbindungspunkten (früher als OLE-Verbindungspunkte) unter Verwendung der MFC-Klassen `CCmdTarget` und `CConnectionPoint`.

[Container/Server-COM-Komponenten](../mfc/containers-advanced-features.md)<br/>
Beschreibt die erforderlichen Schritte zum Optionaler erweiterter Features in vorhandenen containeranwendungen zu integrieren.

[Das Component Object Model](/windows/desktop/com/the-component-object-model)<br/>
Beschreibt die Verwendung von OLE ohne MFC.

## <a name="see-also"></a>Siehe auch

[Konzepte](../mfc/mfc-concepts.md)
