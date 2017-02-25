---
title: "OLE-Hintergrund: Container und Server | Microsoft Docs"
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
  - "Container, OLE-Containeranwendungen"
  - "Vollserver"
  - "OLE-Container, Containeranwendungen"
  - "OLE-Vollserveranwendungen"
  - "OLE-Serveranwendungen, Informationen über Serveranwendungen"
  - "OLE-Serveranwendungen, Miniserveranwendungen"
  - "Serveranwendungen"
  - "Serveranwendungen, Kommunikation mit Containern"
  - "Serveranwendungen, Definition"
  - "Serveranwendungen, Vollserver und Miniserver"
  - "Serveranwendungen, Anforderungen"
ms.assetid: dafbb31d-096c-4654-b774-12900d832919
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# OLE-Hintergrund: Container und Server
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Containeranwendung ist eine Anwendung, die die eingebetteten oder verknüpften Elemente in seine eigenen Dokumente enthalten kann.  Die Dokumente, die von einer Containeranwendung verwaltet werden, müssen in der Lage sein, OLE\-Dokumentkomponenten sowie die Daten zu speichern und anzuzeigen, die von der Anwendung selbst erstellt werden.  Eine Containeranwendung muss Benutzern zum Einfügen gelöschte auch zulassen oder bestehende Elemente durch aktivierende Serveranwendungen dann bearbeiten.  Die Benutzeroberflächeanforderungen einer Containeranwendung werden im Artikel [Container: Benutzeroberfläche\-Probleme](../mfc/containers-user-interface-issues.md).  
  
 Eine Serveranwendungs\- oder Komponenten\-Anwendung ist eine Anwendung, die OLE\-Dokumentkomponenten für Containeranwendungen erstellen kann.  Der Serveranwendungen Drag & Drop normalerweise Stützoder Kopieren der Daten in die Zwischenablage, sodass eine Containeranwendung mit Daten als verknüpftes oder eingebettetes Element einfügen kann.  Eine Anwendung kann ein Container und ein Server sein.  
  
 Die meisten Server sind eigenständige Anwendungen oder vollständige Server; Sie können entweder als eigenständige Anwendungen ausgeführt werden können oder durch eine Containeranwendung gestartet werden.  Ein miniserver ist ein spezieller Typ Serveranwendung, der nur durch einen Container gestartet werden kann.  Sie kann nicht als eigenständige Anwendung ausgeführt werden.  Microsoft zeichnen und Microsoft Graph\-Server sind Beispiele für miniservers.  
  
 Container und Server kommunizieren nicht direkt in Verbindung.  Stattdessen werden sie durch die OLE\-Systemdynamic Dynamic Link Libraries \(DLL\) in Verbindung.  Diese DLLs bieten Funktionen, dass Container und Serveraufruf und die Container und Server die Rückruffunktionen bereitstellen, die die DLLs aufrufen.  
  
 Verwenden dieses muss Kommunikationsmittel, Container nicht, um die Implementierungsdetails der Serveranwendung zu kennen.  Sie können einem Container, um die Elemente akzeptiert, die von jedem Server erstellt werden, ohne zu müssen, welche Typen von Servern zu definieren, mit dem sie arbeiten kann.  Folglich kann der Benutzer einer Containeranwendung zukünftige Anwendungen und Datenformaten nutzen.  Wenn diese neue Anwendungen OLE\-Komponenten sind, ist ein Verbunddokument in der Lage, die Elemente enthalten, die von diesen Anwendungen erstellt werden.  
  
## Siehe auch  
 [OLE\-Hintergrund](../mfc/ole-background.md)   
 [OLE\-Hintergrund: MFC\-Implementierung](../mfc/ole-background-mfc-implementation.md)   
 [Container](../mfc/containers.md)   
 [Server](../mfc/servers.md)   
 [Container: Clientelemente](../mfc/containers-client-items.md)   
 [Server: Serverelemente](../mfc/servers-server-items.md)