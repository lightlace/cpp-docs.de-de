---
title: "OLE in MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungen [OLE], Informationen über OLE"
  - "MFC [C++], OLE und"
  - "OLE [C++]"
  - "OLE-Anwendungen [C++], Informationen über OLE"
  - "OLE-Komponentenobjektmodel (COM)"
  - "OLE-Container, Informationen über OLE"
  - "OLE-Elemente"
ms.assetid: 5193479d-1239-4697-aea4-e82f92c707ab
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# OLE in MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Artikel werden die Grundlagen von OLE\-Programmierung mit MFC.  MFC stellt die einfachste Methode, Programme schreiben, die OLE verwenden:  
  
-   Um visuelle Bearbeiten in OLE \(direkte Aktivierung\) verwenden.  
  
-   Um als OLE\-Container oder Server arbeiten.  
  
-   Um Drag & Drop\-Funktion implementieren.  
  
-   Um mit Datums\- und Uhrzeitdaten arbeiten.  
  
-   So die Zustandsdaten von MFC\-Modulen, einschließlich exportierte DLL\-Funktionseinstiegspunkt\-, OLE\/COM\-Schnittstelleneinstiegspunkte und Fensterprozedureinstiegspunkte verwalten.  
  
 Sie können [Automatisierung](../mfc/automation.md) oder [Remote\- Automatisierung](../mfc/remote-automation.md) verwenden, um ein anderes Programm vom Programm aus.  
  
> [!NOTE]
>  Der Begriff OLE bezeichnet die Technologien, die dem Verknüpfen und das Einbetten, einschließlich OLE\-Container, OLE\-Server, OLE\-Elemente zugeordnet sind, direkte Aktivierung \(oder visuelle Bearbeiten\), Protokollierer, Drag & Drop\-Datenbindung und Menüzusammenführung.  Der aktive Begriff gilt für das Component Object Model \(COM\) und den COM\-basierten Objekte wie ActiveX\-Steuerelemente zu.  OLE\-Automatisierung wird jetzt Automation aufgerufen.  
  
## In diesem Abschnitt  
 [OLE\-Hintergrund](../mfc/ole-background.md)  
 Erläutert OLE und stellt grundlegende Informationen darüber, wie sie funktioniert.  
  
 [Aktivierung](../mfc/activation-cpp.md)  
 Beschreibt die Rolle der Aktivierung in Bearbeitung OLE\-Elementen.  
  
 [Container](../mfc/containers.md)  
 Enthält Links zur Anwendung von Containern in OLE bereit.  
  
 [Datenobjekte und Datenquellen](../mfc/data-objects-and-data-sources-ole.md)  
 Enthält Links zu Themen, die die Verwendung von `COleDataObject` und `COleDataSource`\-Klassen erläutert.  
  
 [Drag & Drop](../mfc/drag-and-drop-ole.md)  
 Beschreibt die Verwendung das Kopieren und Einfügen mit OLE.  
  
 [OLE\-Menüs und Ressourcen](../mfc/menus-and-resources-ole.md)  
 Erläutert die Verwendung von Menüs und Ressourcen in den Dokument\-Anwendungen MFC\-OLE.  
  
 [Registrierung](../mfc/registration.md)  
 Erläutert Serverinstallation und \-initialisierung.  
  
 [Server](../mfc/servers.md)  
 Beschreibt, wie OLE\-Elemente \(oder Komponenten\) für Containeranwendungen erstellt.  
  
 [Protokollierer](../mfc/trackers.md)  
 Stellt Informationen zum `CRectTracker`\-Klasse bereit, die eine grafische Schnittstelle bereitstellt, um Benutzern zu ermöglichen, mit OLE\-Clientelementen zu interagieren.  
  
## Verwandte Abschnitte  
 [Verbindungspunkte](../mfc/connection-points.md)  
 Erläutert, wie die Verbindung \(früher bekannt als OLE\-Verbindungspunkte\) mithilfe der MFC\-Klassen `CCmdTarget` und `CConnectionPoint` implementiert.  
  
 [Container Server\-COM\-Komponenten\/](../mfc/containers-advanced-features.md)  
 Beschreibt die Schritte, die erforderlich sind, optionale erweiterte Funktionen in vorhandene Containeranwendungen zu enthalten.  
  
 [Mit dem Component Object Model](http://msdn.microsoft.com/library/windows/desktop/ms694363)  
 Beschreibt mit OLE ohne MFC.  
  
## Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)