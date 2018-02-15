---
title: Erstellen von Programmen, die Remoteautomatisierung verwenden | Microsoft Docs
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
- Remote Automation, creating programs
ms.assetid: 8eb31320-1037-4029-b1f3-fdc9406dbaf1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 86a9b9f4dccaaa3a97366dffb11955d3b148aff5
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="creating-programs-that-use-remote-automation"></a>Erstellen von Programmen, die Remoteautomatisierung verwenden
Ein Automatisierungsobjekt und alle Automatisierungscontroller kann ohne Änderung auf den Quellcode, ohne die Notwendigkeit für die Neukompilierung und ohne erneute Remoteautomatisierung verwenden. Nachdem Sie eine eingerichtet haben, die lokal funktioniert (d. h. auf dem gleichen Computer), müssen nur wenige Schritte für die es Remoteausführung durchlaufen.  
  
#### <a name="to-execute-the-remote-automation-object"></a>Zum Ausführen des Objekts Remoteautomatisierung  
  
1.  Registrieren Sie die Anwendung auf dem Client oder mehreren Computern.  
  
2.  Konfigurieren Sie den Clientzugriff auf Remoteserver verwenden.  
  
3.  Installieren Sie und registrieren Sie die Anwendung auf dem Server oder mehreren Computern.  
  
4.  Konfigurieren Sie den Server aus, um die Remoteaktivierung.  
  
5.  Automatisierungs-Manager auf den Server/die Computer zu installieren.  
  
6.  Automatisierungs-Manager auf den Servern ausgeführt.  
  
7.  Führen Sie die Anwendung auf den Clients.  
  
 Schritt 1 wird am einfachsten durch Laden und Ausführen von Server-Anwendung auf dem Clientcomputer erreicht, wie die meisten Server Self-Service registriert sind. Wenn Sie das Setup lokal getestet vorher bereits diese Phase abgeschlossen ist. Die Server-Anwendung ist nicht selbst registrieren, kann es daher machen möchten. Andernfalls müssen Sie eine Registrierungsdatei bereitstellen, die der lokale Benutzer ausführen kann, um diesen Schritt auszuführen. Wenn Sie keines diese Dinge tun, Ihnen oder einem Administrator müssen manuell bearbeiten, die Registrierung einer Prozedur nicht für alle Spalten mit Ausnahme der am häufigsten fortgeschrittene Benutzer empfohlen.  
  
 Schritt 2 umfasst die Verwendung des Remote-Automation-Verbindung (RAC)-Managers. RAC-Manager ausführen, und stellen Sie sicher, dass die Registerkarte "Server-Verbindung" obersten ist. Suchen Sie anschließend den Eintrag für das Serverobjekt in der **OLE-Klassen** Bereich, und klicken Sie darauf. Verschieben Sie die **Netzwerkadresse** Kombinationsfeld Feld, und geben Sie den Namen des Servercomputers, auf dem die remote ausführbare Datei ausgeführt wird. Sie können z. B. eingeben \\\MyServer hier. Wählen Sie dann das entsprechende Netzwerk-Protokoll, aus der Liste aus. Sie müssen möglicherweise wenden Sie sich an Ihren Netzwerkadministrator, um zu bestimmen, welches Protokoll empfohlen wird. In vielen Fällen wird dies TCP/IP sein. Möglicherweise möchten schließlich eine Authentifizierungsebene auswählen. In den meisten Fällen wird dies Links "mit" (keine), oder Standardwert sein. Jetzt Maustaste die Server in der **OLE-Klassen** Bereich. Dadurch wird ein Kontextmenü erzeugen, in dem Sie lokal oder remote-Vorgang auswählen können. Wählen Sie Remote aus.  
  
 Schritt 3 umfasst ordnungsgemäß zu installieren und registrieren die Server-Anwendung auf dem ausgewählten Server oder mehreren Computern. Erneut, wenn die Anwendung selbst registrieren, werden einmal Ausführung auch registriert.  
  
 Schritt 4 umfasst die Konfiguration des Servers, um remote-Ausführung zu ermöglichen. RAC-Manager auf dem Servercomputer ausführen und sicherstellen, dass die **Clientzugriff** Registerkarte den Fokus besitzt. Wählen Sie das gewünschte Aktivierungsmodell (i. d. r. **zulassen Remote erstellt, indem Schlüssel**. Wenn Sie diese Option auswählen, müssen Sie auch auf die **Remoteaktivierung zulassen** Kontrollkästchen, um den Wert des Registrierungseintrags 'Y' festgelegt). Bei der Option ermöglichen Remote erstellt (ACL) haben Sie auch die Option zum Bearbeiten der ACL durch Betätigen der **ACL bearbeiten** Schaltfläche.  
  
 Damit um Remoteautomatisierung arbeiten zu können, müssen Sie Sie dann stellen Sie sicher, dass die Automatisierungs-Manager installiert ist und auf dem Server oder mehreren Computern ausgeführt wird. Wenn es nicht installiert ist, kopieren Sie AUTMGR32. EXE-Datei für das Windows-Systemverzeichnis. Informationen dazu finden Sie unter [Remoteinstallation Automation](../mfc/remote-automation-installation.md). Führen Sie zum Starten von Remoteautomatisierung Automatisierungs-Manager ein. Es wird eine kleine Statusfenster angezeigt, in dem eine Anzahl von Nachrichten angezeigt werden. Nachdem es gestartet wurde, wird es selbst minimieren. Wenn weiterhin Statusinformationen angezeigt werden sollen, können Sie klicken die **Automatisierungs-Manager** Registerkarte auf der Taskleiste, um das Fenster wiederherzustellen.  
  
 Der letzte Schritt ist die Clientanwendung auf dem Clientcomputer ausgeführt. Wenn Sie die oben beschriebenen Schritte ausgeführt haben, sollte Herstellen einer Verbindung mit dem Serverobjekt und genau wie zuvor lokal ausführen, obwohl ein wenig langsamer.  
  
 Beachten Sie, dass der RAC-Manager können auch die Wechseln zwischen Remoteautomatisierung und verteiltes COM (DCOM auf diesen Plattformen, die DCOM unterstützen), mit einem einzigen Mausklick ein Optionsfeld. Wenn Sie DCOM auswählen, können Sie verschiedene andere Konfigurationsoptionen festlegen. Finden Sie weitere Details der DCOM-Dokumentation.  
  
## <a name="see-also"></a>Siehe auch  
 [Remoteautomatisierung](../mfc/remote-automation.md)   
 [Ausführen von Remoteautomatisierung mithilfe von AUTOCLIK und AUTODRIV](../mfc/running-remote-automation-using-autoclik-and-autodriv.md)

