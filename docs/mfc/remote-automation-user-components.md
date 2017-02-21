---
title: "Benutzerkomponenten f&#252;r Remoteautomatisierung | Microsoft Docs"
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
  - "DLLs [C++], Automatisierung"
  - "Remoteautomatisierung [C++], Benutzerkomponenten"
ms.assetid: 601591cc-a442-440a-988e-baf3284b0d46
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Benutzerkomponenten f&#252;r Remoteautomatisierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie müssen sicherstellen, dass jeder Clientcomputer das Clientprogramm und alle Unterstützungs\-DLLs enthält, die es benötigt.  Sie müssen außerdem sicherstellen, dass die Anwendung und alle Unterstützungs\-DLLs, die erforderlich sind, auf dem Servercomputer vorhanden sind.  Abschließend müssen Sie sicherstellen, dass das Serverprogramm auf jedem Clientcomputer registriert wird, bevor RAC\-Manager ausgeführt werden kann, um die Verbindung zu konfigurieren.  Wenn das Programm \(als die meisten sind Sie\), SELF\-registriert, müssen Sie nur das Serverprogramm auf dem Clientcomputer ausgeführt werden, um ihn zu registrieren.  Schlägt dies fehl, müssen Sie möglicherweise eine Registrierungsdatei ausführen, die Sie bereitstellen, oder bearbeiten manuell die Registrierung.  
  
## Siehe auch  
 [Automatisierungs\-Manager \(MFC\)](../mfc/automation-manager-mfc.md)   
 [Manager für Remoteautomatisierungsverbindungen](../mfc/remote-automation-connection-manager.md)   
 [Remoteautomatisierungsinstallation](../mfc/remote-automation-installation.md)