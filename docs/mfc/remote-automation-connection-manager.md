---
title: "Manager f&#252;r Remoteautomatisierungsverbindungen"
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
  - "Automatisierungsclients, Konfigurieren für Remoteautomatisierung"
  - "Automatisierungsserver, Konfigurieren für Remoteautomatisierung"
  - "RAC-Manager-Tool"
  - "Registrierung, Remoteautomatisierung"
  - "Manager für Remoteautomatisierungsverbindungen"
  - "Remoteautomatisierung, Konfigurieren von Client- und Servercomputern"
ms.assetid: 562eb7bc-f95c-46ad-ac97-f0dfa98362af
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Manager f&#252;r Remoteautomatisierungsverbindungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um Client\- und Servercomputer zu konfigurieren, müssen Sie Registrierungsänderungen vornehmen.  Anstatt, dies manuell transitive, ist es generell einfacher, das den Automatisierungs\-Verbindungs \(rac\)\- Managertool zu verwenden.  Dieses Tool, RACMGR32.EXE, zusammen mit RACREG32.DLL, muss in einem beliebigen Verzeichnis kopiert wurden, das Sie auswählen.  Indem es in PATH einfügen, kann es der Taskleiste mit der Ausführung ausgeführt werden.  Alternativ können Sie eine Verknüpfung zu der erstellen oder einen Verweis darauf im Startmenü platzieren.  
  
 RACMGR32 wird in Visual Basic geschrieben und daher mehrere Visual Basic\-Unterstützungs\-DLLs erfordert.  Diese Dateien werden in das gleiche Verzeichnis wie RACMGR32.EXE auf CD\-ROM eingefügt.  Die Versionen dieser Dateien, die durch die Einrichtung für Visual C\+\+ Enterprise Edition installiert sind, sind äquivalent oder neuer als die, die mit Visual Basic Enterprise Edition 5.0 sind.  Das Visual C\+\+ Setup erneut aus kopiert die neuen Versionen der Visual Basic\-Dateien im Systemverzeichnis.  Für Windows 9x, lautet dieses Verzeichnis in der Regel C:\\Windows\\System.  Für Windows NT und Windows 2000 ist es in der Regel C:\\WINNT\\system32.  Setup registriert diese Dateien auch im Betriebssystem.  Sie entfernen kann diese von der Visual Basic\-Installation.  
  
## Siehe auch  
 [Automatisierungs\-Manager \(MFC\)](../mfc/automation-manager-mfc.md)   
 [Benutzerkomponenten für Remoteautomatisierung](../mfc/remote-automation-user-components.md)   
 [Remoteautomatisierungsinstallation](../mfc/remote-automation-installation.md)