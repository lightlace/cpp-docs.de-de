---
title: "Benutzerkomponenten für Remoteautomatisierung | Microsoft Docs"
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
- DLLs [MFC], Automation
- Remote Automation [MFC], user components
ms.assetid: 601591cc-a442-440a-988e-baf3284b0d46
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2f82fe529586579109434da447e26b15dcb9503a
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="remote-automation-user-components"></a>Benutzerkomponenten für Remoteautomatisierung
Sie müssen sicherstellen, dass jeder Clientcomputer, enthält Ihr Clientprogramm und keine Unterstützung dafür DLLs. Sie müssen auch sicherstellen, dass die Server-Anwendung und keine Unterstützung dafür DLLs auf dem Servercomputer vorhanden sind. Schließlich müssen Sie sicherstellen, dass Ihre Serverprogramm auf jedem Clientcomputer registriert ist, bevor RAC-Manager zum Konfigurieren der Verbindung ausgeführt werden kann. Wenn das Programm selbst registrieren wird (wie die meisten werden), müssen Sie nur des Programms auf dem Clientcomputer zu registrieren ausführen. Andernfalls müssen Sie möglicherweise führen Sie eine Registrierungsdatei, die Sie bereitstellen oder die Registrierung manuell bearbeiten.  
  
## <a name="see-also"></a>Siehe auch  
 [Automatisierungs-Manager (MFC)](../mfc/automation-manager-mfc.md)   
 [Manager für Remoteautomatisierungsverbindungen](../mfc/remote-automation-connection-manager.md)   
 [Remoteautomatisierungsinstallation](../mfc/remote-automation-installation.md)

