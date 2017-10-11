---
title: "Bereitstellen, Ausführen und Debuggen eines Linux-Projekts | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7084cdb-17b1-4960-b522-f84981bea879
author: BrianPeek
ms.author: brpeek
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 1f36435bbb8238fb6068e7b58f9142eda62bc28c
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---

# <a name="deploy-run-and-debug-your-project"></a>Bereitstellen, Ausführen und Debuggen eines Linux-Projekts

Nachdem Sie das Projekt erstellt haben, stellen Sie eine Verbindung mit dem Linux-Computer her. Dabei wird der Code kompiliert, ausgeführt und gedebuggt.

1. Legen Sie die Remotezielarchitektur mit der üblichen Dropdownliste in Visual Studio wie dargestellt fest: ![Remotearchitektur](media/architecture.png)

Es gibt mehrere Möglichkeiten für den Umgang mit dem Linux-Projekt sowie zum Debuggen des Projekts.

* Die herkömmlichen Visual Studio-Funktionen Haltepunkte, Überwachungsfenster und Draufzeigen auf eine Variable funktionieren erwartungsgemäß, sodass Sie wie gewohnt debuggen können.
* Über das Menüelement **Debug > Linux Console** (Debuggen > Linux-Konsole) kann ein spezielles Linux-Konsolenfenster geöffnet werden.

  ![Menü mit Linux-Konsole](media/consolemenu.png)

  In dieser Konsole werden alle Konsolenausgaben vom Zielcomputer angezeigt. Zudem werden über die Konsole Eingaben an den Zielcomputer gesendet.

  ![Linux-Konsolenfenster](media/consolewindow.png)

* Befehlszeilenargumente können mit dem Element **Programmargumente** auf der Eigenschaftenseite **Debugging** des Projekts an die ausführbare Datei übergeben werden.
  
  ![Programmargumente](media/settings_programarguments.png)

* GDB wird zum Debuggen von Anwendungen verwendet, die unter Linux ausgeführt werden.  Für die Ausführung stehen zwei Modi zur Verfügung, die über die Option **Debugmodus** auf der Eigenschaftenseite **Debugging** des Projekts ausgewählt werden können:

  ![GDB-Optionen](media/settings_debugger.png)

  | Auswahl | Beschreibung
  | --------- | ---
  | gdbserver | GDB wird lokal ausgeführt und stellt eine Verbindung mit gdbserver her, das auf dem Remotesystem ausgeführt wird.  Dies ist der einzige Modus, der vom Linux-Konsolenfenster unterstützt wird. 
  | gdb       | Der Visual Studio-Debugger unterstützt GDB auf dem Remotesystem, das besser kompatibel ist, falls die lokale Version von GDB nicht mit der auf dem Zielcomputer installierten Version kompatibel ist.

* Bestimmte Debuggeroptionen können mit dem Eintrag **Weitere Debuggerbefehle** an GDB übergeben werden.  Beispiel: SIGILL-Signale (unzulässige Anweisung) sollen ignoriert werden.  Hierzu können Sie den **handle**-Befehl verwenden.  Fügen Sie wie oben dargestellt Folgendes zum Eintrag **Weitere Debuggerbefehle** hinzu:

  ```handle SIGILL nostop noprint```

