---
title: "OLE-Hintergrund"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE, Informationen über OLE"
ms.assetid: 5f654eb5-66b1-40c9-9215-bb85356a67f8
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# OLE-Hintergrund
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

OLE ist ein Mechanismus, der dem Benutzer ermöglicht, der Dokumente zu erstellen und zu bearbeiten, die die Elemente oder "Objekte" erstellt werden durch mehrere Anwendungen enthalten.  
  
> [!NOTE]
>  OLE war ursprünglich ein Akronym für Object Linking auf Embedding.  Allerdings wird darauf jetzt als OLE.  Die Teile OLE verknüpft nicht zum Verknüpfen und zum Einbetten sind nun Teil Active Technology.  
  
 OLE\-Dokumente Historically, aufgerufen Verbunddokumente, integrieren nahtlos verschiedene Datentypen oder Komponenten.  Soundclips, Arbeitsblätter und Bitmaps sind typische Beispiele aus Komponenten, die in OLE\-Dokumenten gefunden werden.  Das Unterstützen von OLE in der Anwendung ermöglicht den Benutzern, um OLE\-Dokumente zu verwenden, ohne die Umschaltung zwischen verschiedenen Anwendungen sich darum zu kümmern; OLE führt die Umschaltung für Sie.  
  
 Sie verwenden eine Containeranwendung, Verbunddokumente und eine Serveranwendungs\- oder Komponenten\-Anwendung zu erstellen, die Elemente innerhalb des Containerdokuments zu erstellen.  Jede Anwendung, die Sie schreiben, kann ein Container, ein Server oder beides sein.  
  
 OLE enthält viele verschiedene Konzepte diese alle Arbeiten in Hinblick auf das Ziel der nahtlosen Interaktion zwischen Anwendungen.  Diese Bereiche umfassen Folgendes:  
  
 Verknüpfen und Einbetten  
 Das Verknüpfen und das Einbetten sind zwei Methoden für das Speichern von Elementen, die in einem OLE\-Dokuments erstellt werden, die in einer anderen Anwendung erstellt wurden.  Allgemeine Informationen über die Unterschiede zwischen den zwei, finden Sie im Artikel [OLE\-Hintergrund: Verknüpfen und Einbetten](../mfc/ole-background-linking-and-embedding.md).  Ausführlichere Informationen finden Sie in Artikel [Container](../mfc/containers.md) und [Server](../mfc/servers.md).  
  
 Direkte Aktivierung \(visuelle Bearbeiten\)  
 Ein eingebettetes Element im Rahmen des Containerdokuments aktiviert, wird Bearbeiten der direkte Aktivierung oder visuellen Objekts aufgerufen.  Die Schnittstelle der Containeranwendung ändert, um die Funktionen der Teil\-Anwendung enthalten, die das eingebettete Element erstellt wurde.  Verknüpfte Elemente sind nicht an der Stelle da die tatsächlichen Daten für das Element in einer separaten Datei befinden, aus dem Kontext der Anwendung heraus können, die den Link enthält.  Weitere Informationen über direkte Aktivierung, finden Sie im Artikel [Aktivierung](../mfc/activation-cpp.md).  
  
> [!NOTE]
>  Das Verknüpfen und das Einbetten und direkte Aktivierung enthalten die Hauptmerkmale der visuellen Bearbeitung in OLE.  
  
 Automatisierung  
 Automatisierung können eine Anwendung, eine andere Anwendung zu erreichen.  Die Anwendung wird als antreibende Automatisierungsclient, und die Anwendung, die bestimmt wird, wird als Automatisierungskomponente Automatisierungsserver oder.  Weitere Informationen über die Automatisierung, finden Sie in Artikel [Automatisierungs\-Clients](../mfc/automation-clients.md) und [Automatisierungsserver](../mfc/automation-servers.md).  
  
> [!NOTE]
>  Automatisierung funktioniert in OLE und in den Active Technology\-Kontexten.  Sie können jedes Objekt COM\-basiert automatisieren.  
  
 Verbunddateien  
 Verbunddateien stellen ein Standarddateiformat, die strukturierte das Speichern von Verbunddokumenten für OLE\-Anwendungen vereinfacht.  Innerhalb einer Verbunddatei Speicher haben viele Funktionen von Verzeichnisse und Streams haben viele Funktionen von Dateien.  Diese Technologie wird auch strukturierten Speicher aufgerufen.  Weitere Informationen über Verbunddateien, finden Sie im Artikel [Container: Verbunddateien](../mfc/containers-compound-files.md).  
  
 Einheitliche Datenübertragung  
 Einheitliche Datenübertragung \(UDT\) ist ein Satz von Schnittstellen, die in einer Standardweise können gesendet und empfangen wurden die Daten, unabhängig von der tatsächlichen Methode, die ausgewählt wird, um die Daten zu übertragen.  UDT bildet die Grundlage für Datenübertragungen durch Drag & Drop.  UDT dient jetzt als Basis für vorhandene Windows\-Datenübertragung, wie die Zwischenablage und den dynamischen Datenaustausch \(DDE\).  Weitere Informationen über UDT, finden Sie im Artikel [Datenobjekte und Datenquellen \(OLE\)](../mfc/data-objects-and-data-sources-ole.md).  
  
 Drag & Drop  
 Drag & Drop ist eine benutzerfreundliche, Direktmanipulationstechnik für Datenübertragung mit Anwendungen, unter Fenstern in einer Anwendung oder sogar innerhalb eines einzelnen Fensters in einer Anwendung.  Die zu übertragenden Daten werden dem gewünschten Ziel ausgewählt und abgerufen.  Drag & Drop basiert auf einheitliche Datenübertragung.  Weitere Informationen über Drag & Drop, finden Sie im Artikel [Drag & Drop](../mfc/drag-and-drop-ole.md).  
  
 Component Object Model  
 Mit dem Component Object Model \(COM\) wird die verwendete Infrastruktur, wenn OLE\-Objekte miteinander.  Die Klassen MFC\-OLE vereinfachen COM für den Programmierer.  COM ist Teil Active Technology, da COM\-Objekte OLE und Active Technology zugrunde liegen.  Weitere Informationen zu COM, finden Sie die Themen [Active Template Library \(ATL\)](../atl/active-template-library-atl-concepts.md).  
  
 Einige der wichtigeren OLE\-Themen werden in den folgenden Artikeln behandelt:  
  
-   [OLE\-Hintergrund: Verknüpfen und Einbetten](../mfc/ole-background-linking-and-embedding.md)  
  
-   [OLE\-Hintergrund: Container und Server](../mfc/ole-background-containers-and-servers.md)  
  
-   [OLE\-Hintergrund: Durchführungsstrategien](../mfc/ole-background-implementation-strategies.md)  
  
-   [OLE\-Hintergrund: MFC\-Implementierung](../mfc/ole-background-mfc-implementation.md)  
  
 Für allgemeine OLE\-Information nicht gefunden in den oben genannten Artikeln, Suche für OLE in MSDN.  
  
## Siehe auch  
 [OLE](../mfc/ole-in-mfc.md)