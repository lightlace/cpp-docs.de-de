---
title: "Manager für Remoteautomatisierungsverbindungen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Automation clients [MFC], configuring for Remote Automation
- registry [MFC], remote Automation
- Automation servers [MFC], configuring for Remote Automation
- Remote Automation Connection Manager [MFC]
- Remote Automation [MFC], configuring client and server machines
- RAC Manager tool [MFC]
ms.assetid: 562eb7bc-f95c-46ad-ac97-f0dfa98362af
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cf316653b2f968fd5373c6265bb4f3f3ef3b0ba4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="remote-automation-connection-manager"></a>Manager für Remoteautomatisierungsverbindungen
Um Client- und Servercomputern konfigurieren zu können, müssen Sie registrierungsänderungen vornehmen. Anstatt auf diese Weise manuell ist es sehr viel einfacher, die Remote Automation-Verbindung (RAC)-Manager-Tool zu verwenden. Dieses Tool RACMGR32. EXE-Datei, zusammen mit RACREG32. DLL muss in einem beliebigen Verzeichnis gewählten kopiert werden. Verlegen sie den Pfad, kann er aus der Taskleiste mit der Ausführung ausgeführt werden. Sie können alternativ erstellen Sie eine Verknüpfung, oder platzieren einen Verweis darauf im Startmenü.  
  
 RACMGR32 in Visual Basic geschrieben ist und daher muss die DLLs für einige Visual Basic unterstützen. Diese Dateien befinden sich im gleichen Verzeichnis wie RACMGR32. EXE-Datei auf der CD-ROM. Die Versionen dieser Dateien, die vom Setup für Microsoft Visual C++ Enterprise Edition installiert sind, sind entsprechende oder jünger als solche, die mit den im Lieferumfang von Visual Basic Enterprise Edition 5.0. Visual C++ Setup kopiert die neuen Versionen von Visual Basic-Dateien in Ihrem Verzeichnis "System". Für Windows 9 x, dieses Verzeichnis ist in der Regel C:\Windows\System. Für Windows NT und Windows 2000 ist es in der Regel C:\WINNT\system32. Setup wird diese Dateien auch mit dem Betriebssystem registriert. Sie können sie aus der Visual Basic-Installation entfernen.  
  
## <a name="see-also"></a>Siehe auch  
 [Automatisierungs-Manager (MFC)](../mfc/automation-manager-mfc.md)   
 [Benutzerkomponenten für Remoteautomatisierung](../mfc/remote-automation-user-components.md)   
 [Remoteautomatisierungsinstallation](../mfc/remote-automation-installation.md)

