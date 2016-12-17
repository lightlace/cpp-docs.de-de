---
title: "Benutzerkomponenten f&#252;r Remoteautomatisierung"
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
  - "DLLs [C++], Automatisierung"
  - "Remoteautomatisierung [C++], Benutzerkomponenten"
ms.assetid: 601591cc-a442-440a-988e-baf3284b0d46
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Benutzerkomponenten f&#252;r Remoteautomatisierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie müssen sicherstellen, dass jeder Clientcomputer das Clientprogramm und alle Unterstützungs\-DLLs enthält, die es benötigt.  Sie müssen außerdem sicherstellen, dass die Anwendung und alle Unterstützungs\-DLLs, die erforderlich sind, auf dem Servercomputer vorhanden sind.  Abschließend müssen Sie sicherstellen, dass das Serverprogramm auf jedem Clientcomputer registriert wird, bevor RAC\-Manager ausgeführt werden kann, um die Verbindung zu konfigurieren.  Wenn das Programm \(als die meisten sind Sie\), SELF\-registriert, müssen Sie nur das Serverprogramm auf dem Clientcomputer ausgeführt werden, um ihn zu registrieren.  Schlägt dies fehl, müssen Sie möglicherweise eine Registrierungsdatei ausführen, die Sie bereitstellen, oder bearbeiten manuell die Registrierung.  
  
## Siehe auch  
 [Automatisierungs\-Manager \(MFC\)](../mfc/automation-manager-mfc.md)   
 [Manager für Remoteautomatisierungsverbindungen](../mfc/remote-automation-connection-manager.md)   
 [Remoteautomatisierungsinstallation](../mfc/remote-automation-installation.md)