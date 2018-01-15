---
title: "Ausführen von Remoteautomatisierung mithilfe von AUTOCLIK und AUTODRIV | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: AUTOCLIK sample [MFC]
ms.assetid: 8900c0de-8dba-4f0a-8d9e-7db77a1f4f46
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 791655047eaf07732e1e006e8cc3ea8e7dec4727
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="running-remote-automation-using-autoclik-and-autodriv"></a>Ausführen von Remoteautomatisierung mithilfe von AUTOCLIK und AUTODRIV
AUTOCLIK ist ein einfaches Beispiel automatisierungsserveranwendung, die Sie als Basis dort erfahren Sie mehr über die Remoteautomatisierung verwenden können. AUTODRIV ist eine einfache-Clientanwendung, die AUTOCLIK gesteuert. Sie können diese um Remoteautomatisierung zu veranschaulichen.  
  
#### <a name="to-install-autoclikexe-on-two-machines-and-drive-it-using-remote-automation"></a>AUTOCLIK installieren zu können. EXE-Datei auf zwei Computern und führen mithilfe von Remoteautomatisierung  
  
1.  Installieren der [AUTOCLIK](../visual-cpp-samples.md) beispielanwendung auf dem Entwicklungscomputer.  
  
2.  AUTOCLIK zu erstellen. EXE-DATEI.  
  
3.  Führen Sie AUTOCLIK. EXE-Datei in der eigenständigen Weise und dann heruntergefahren. Dies wird als ein Automation-Server registriert.  
  
4.  Kopieren Sie AUTOCLIK. EXE-Datei auf einem Remotecomputer es dort auszuführen und dann beendet werden.  
  
5.  Führen Sie AUTODRIV. EXE-Datei auf dem lokalen Computer, und stellen Sie sicher, dass dadurch AUTOCLIK. EXE-DATEI. Weitere Informationen über AUTODRIV gefunden. EXE-Datei, finden Sie unter [AUTOCLIK](../visual-cpp-samples.md).  
  
6.  Starten Sie auf dem Remotecomputer Sie AUTMGR32. EXE-Datei (Automatisierungs-Manager).  
  
7.  Starten Sie auf dem Remotecomputer RACMGR32. EXE-Datei (Manager für Remoteautomatisierungsverbindungen).  
  
8.  Wählen Sie in der Manager für Remoteautomatisierungsverbindungen, AutoClik.Document aus der **OLE-Klassen** Liste.  
  
9. Wählen Sie eine Sicherheitsrichtlinie "System" aus der **Clientzugriff** Registerkarte AutoClik.Document Clientzugriff gewähren.  
  
10. Starten Sie auf dem lokalen Computer RACMGR32. EXE-Datei und wählen AutoClik.Document aus der **OLE-Klassen** Liste.  
  
11. Aus der **Serververbindung** Registerkarte, und wählen Sie sowohl die Netzwerk-Adresse des Remotecomputers und das entsprechende Netzwerkprotokoll.  
  
12. Mit AutoClik.Document noch im ausgewählten der **OLE-Klassen** Listenfeld, und wählen Sie die **Remote** Befehl die `Register` Menü.  
  
13. Führen Sie auf dem lokalen Computer AUTODRIV. EXE-Datei oder die entsprechende AUTOCLIK. MAK Visual Basic-Projekt ggf. haben eine Visual Basic, statt eines MFC-Client.  
  
 Auf dem Remotecomputer sollten Sie jetzt ausführen von Befehlen, die von einem lokalen Client initiiert AUTOCLIK anzeigen können.  
  
## <a name="see-also"></a>Siehe auch  
 [Remoteautomatisierung](../mfc/remote-automation.md)

