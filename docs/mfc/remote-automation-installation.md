---
title: "Remoteautomatisierungsinstallation | Microsoft Docs"
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
  - "Installieren von Remoteautomatisierung"
  - "Remoteautomatisierung, Installation"
ms.assetid: 9a02c9f6-dfc6-4489-b240-a1afe25fa0c5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Remoteautomatisierungsinstallation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Remote\- Automatisierung ist verhältnismäßig wenig Komponenten:  
  
-   Der von Automatisierungsclientproxy, AUTPRX32.DLL.  
  
-   Die serverseitige Komponente den Automatisierung, der Automatisierungs\-Manager, AUTMGR32.EXE.  
  
-   Der RAC\-Manager, RACMGR32.EXE, mit dem entsprechenden RACREG32.DLL.  
  
 Von diesen ist RAC\-Manager in Visual Basic geschrieben und daher die Visual Basic\-Laufzeit\-Unterstützung erfordert.  Diese und die anderen Remoteprozess Automatisierungsdateien werden vom Setup installiert, wenn Sie Visual C\+\+ Enterprise Edition installieren.  
  
 Wenn Sie die Automatisierungskomponenten Remote auf einen Computer kopieren, auf dem Visual C\+\+\-Version Enterprise Edition nicht installiert ist, stellen Sie sicher, dass REGSRV32.EXE auf den Pfad des Computers ist, und Register RACREG32.DLL mithilfe der folgenden Befehlszeile:  
  
 REGSRVR32 RACREG32.DLL  
  
> [!NOTE]
>  Versionen von RAC\-Manager vor Visual C\+\+ 5.0 erforderlichen GUAGE32.OCX und TABCTL32.OCX.  Keine dieser ist für die Version von RAC\-Manager erforderlich, der mit Visual C\+\+ Enterprise Edition, Version 5.0 oder höher bereitgestellte.  
  
## In diesem Abschnitt  
 [Der Automatisierungs\-Manager](../mfc/automation-manager-mfc.md)  
  
 [Der Verbindungs\-Manager für Remoteautomatisierung](../mfc/remote-automation-connection-manager.md)  
  
 [Remote\- Automatisierungs\-Benutzer\-Komponenten](../mfc/remote-automation-user-components.md)  
  
## Siehe auch  
 [Remoteautomatisierung](../mfc/remote-automation.md)