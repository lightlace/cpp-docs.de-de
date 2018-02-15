---
title: Remoteautomatisierungsinstallation | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Remote Automation [MFC], installation
- installing Remote Automation [MFC]
ms.assetid: 9a02c9f6-dfc6-4489-b240-a1afe25fa0c5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: acd8ee55261dfa03c68aef506dc90188d8d27d37
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="remote-automation-installation"></a>Remoteautomatisierungsinstallation
Remoteautomatisierung besteht nur relativ wenige Komponenten:  
  
-   Remoteautomatisierung-Clientproxy AUTPRX32. DLL.  
  
-   Die Remoteautomatisierung serverseitige Komponente, die Automatisierungs-Manager Sie AUTMGR32. EXE-DATEI.  
  
-   Der RAC-Manager RACMGR32. EXE-Datei, die zugehörige RacReg32. DLL.  
  
 Von diesen RAC-Manager in Visual Basic geschrieben ist und aus diesem Grund muss die Visual Basic-Laufzeit unterstützt. Diese und andere Remoteautomatisierung-Dateien werden bei der Installation von Visual C++ Enterprise Edition von Setup installiert werden.  
  
 Wenn Sie die Remoteautomatisierung-Komponenten auf einem Computer kopieren auf welche Version von Visual C++ Enterprise Edition nicht installiert ist, stellen Sie sicher, dass sich REGSRV32. EXE-Datei befindet sich auf dem Computer Pfad, und registrieren RACREG32. Die DLL über die folgende Befehlszeile:  
  
 REGSRVR32 RACREG32.DLL  
  
> [!NOTE]
>  Versionen der RAC-Manager vor Visual C++ 5.0 benötigten GUAGE32. OCX und TABCTL32. OCX. Beide Methoden ist für die Version des RAC-Manager, die geliefert wird mit Visual C++ Enterprise Edition, Version 5.0 oder höher erforderlich.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [The Automation Manager](../mfc/automation-manager-mfc.md)  
  
 [Der Manager für Remoteautomatisierungsverbindungen](../mfc/remote-automation-connection-manager.md)  
  
 [Benutzerkomponenten für Remoteautomatisierung](../mfc/remote-automation-user-components.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Remoteautomatisierung](../mfc/remote-automation.md)

