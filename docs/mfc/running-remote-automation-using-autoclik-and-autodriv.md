---
title: "Ausf&#252;hren von Remoteautomatisierung mithilfe von AUTOCLIK und AUTODRIV"
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
  - "AUTOCLIK-Beispiele [MFC]"
ms.assetid: 8900c0de-8dba-4f0a-8d9e-7db77a1f4f46
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Ausf&#252;hren von Remoteautomatisierung mithilfe von AUTOCLIK und AUTODRIV
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das AUTOCLIK\-Beispiel ist eine einfache Automatisierungsserverbeispielanwendung, die als Grundlage verwenden können, der mehr über die Automatisierung erfahren.  AUTODRIV ist eine einfache Automatisierungsclientanwendung diese Laufwerke AUTOCLIK.  Sie können sie verwenden, um von Automatisierung zu veranschaulichen.  
  
#### So AUTOCLIK.EXE auf beiden Computern installieren und sie mit den Automatisierung steuern  
  
1.  Installieren Sie die Beispielanwendung [Das AUTOCLIK\-Beispiel](../top/visual-cpp-samples.md) auf dem Entwicklungscomputer.  
  
2.  Erstellen Sie AUTOCLIK.EXE.  
  
3.  Führen Sie AUTOCLIK.EXE in der eigenständigen Weise aus und schließen Sie sie unten.  Dies registriert diesen als Automatisierungsserver.  
  
4.  Kopieren Sie AUTOCLIK.EXE auf einem Remotecomputer, führen Sie es dort, und schließen Sie sie unten.  
  
5.  Führen Sie AUTODRIV.EXE auf dem lokalen Computer aus und überprüfen Sie, dass, ihn ausführen, AUTOCLIK.EXE beginnt.  Um mehr über AUTODRIV.EXE erhalten, finden Sie unter [Das AUTOCLIK\-Beispiel](../top/visual-cpp-samples.md).  
  
6.  Auf dem Remotecomputer starten Sie AUTMGR32.EXE \(Automatisierungs\-Manager\).  
  
7.  Auf dem Remotecomputer starten Sie RACMGR32.EXE \(Verbindungs\-Manager für Remoteautomatisierung\).  
  
8.  Im Verbindungs\-Manager für Remoteautomatisierung ausgewähltes AutoClik.Document aus der Liste **OLE\-Klassen**.  
  
9. Wählen Sie eine Systemsicherheitsrichtlinie aus der Registerkarte **Clientzugriff**, um Clientzugriff zu AutoClik.Document zu gewähren.  
  
10. Auf dem lokalen Computer, dem Anfang RACMGR32.EXE und dem ausgewählten AutoClik.Document aus der Liste **OLE\-Klassen**.  
  
11. Von **Serververbindung** der Registerkarte wählen Sie die Netzwerkadresse des Remotecomputers und das entsprechende Netzwerkprotokoll aus.  
  
12. Wenn AutoClik.Document weiterhin im **OLE\-Klassen** Listenfeld markiert ist, wählen Sie den Befehl **Remoteelement** aus dem Menü `Register` aus.  
  
13. Auf dem lokalen Computer, führen AUTODRIV.EXE oder dem AUTOCLIK.MAK Entsprechung Visual Basic\-Projekt, wenn Sie Visual Basic verwenden möchten, statt als MFC, Client.  
  
 Auf dem Remotecomputer Sie sollten jetzt in der Lage sein, AUTOCLIK anzuzeigen die Befehle ausgeführt, die vom lokalen Client initiiert werden.  
  
## Siehe auch  
 [Remoteautomatisierung](../mfc/remote-automation.md)