---
title: "Bereitstellen, Ausführen und Debuggen eines Linux-Projekts | Microsoft Docs"
ms.custom: 
ms.date: 11/06/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7084cdb-17b1-4960-b522-f84981bea879
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 237b6f3dbca8d529362a545f67ee0db4f9770d8d
ms.sourcegitcommit: 69632887f7a85f4841c49b4c1353d3144927a52c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2017
---
# <a name="deploy-run-and-debug-your-linux-project"></a>Bereitstellen, Ausführen und Debuggen eines Linux-Projekts

Nachdem Sie ein Linux-Projekt erstellt und mit dem [Verbindungs-Manager von Linux](../linux/connect-to-your-remote-linux-computer.md) eine Verbindung mit dem Projekt hergestellt haben, können Sie das Projekt ausführen und debuggen. Die Kompilierung, die Ausführung und das Debuggen des Codes erfolgen auf dem Remoteziel.

Es gibt mehrere Möglichkeiten für den Umgang mit dem Linux-Projekt sowie zum Debuggen des Projekts.

* Debuggen Sie mit herkömmlichen Features von Visual Studio wie Haltepunkten, Überwachungsfenstern und Positionieren des Mauszeigers über einer Variablen. Mit diesen Methoden können Sie wie bei anderen Projekttypen debuggen.
* Zeigen Sie die Ausgabe vom Zielcomputer in einem speziellen Fenster der Linux-Konsole an. Sie können die Konsole auch verwenden, um Eingaben an den Zielcomputer zu senden.

## <a name="debug-your-linux-project"></a>Debuggen eines Linux-Projekts

1. Wählen Sie den Debugmodus auf der Eigenschaftenseite **Debuggen** aus.

    GDB wird zum Debuggen von Anwendungen verwendet, die unter Linux ausgeführt werden.  Für die Ausführung stehen zwei Modi zur Verfügung, die über die Option **Debugmodus** auf der Eigenschaftenseite **Debugging** des Projekts ausgewählt werden können:

    ![GDB-Optionen](media/settings_debugger.png)

    - Im **gdbserver**-Modus wird GDB lokal ausgeführt und stellt eine Verbindung mit gdbserver her, der auf dem Remotesystem ausgeführt wird.  Dies ist der einzige Modus, der vom Linux-Konsolenfenster unterstützt wird.

    - Im **gdb**-Modus unterstützt der Visual Studio-Debugger GDB auf dem Remotesystem. Dies ist besser kompatibel, falls die lokale Version von GDB nicht mit der auf dem Zielcomputer installierten Version kompatibel ist. |

    > [!NOTE] 
    > Wenn Sie im gdbserver-Debugmodus keine Haltepunkte treffen können, versuchen Sie es im gdb-Modus. GDB muss zunächst auf dem Remoteziel [installiert](../linux/download-install-and-setup-the-linux-development-workload.md) werden.

2. Wählen Sie das Remoteziel mit der Standardsymbolleiste **Debuggen** in Visual Studio aus.

    Wenn das Remoteziel verfügbar ist, wird es anhand des Namens oder der IP-Adresse aufgelistet.

    ![Remoteziel](media/remote_target.png)

    Wenn Sie noch keine Verbindung mit dem Remoteziel hergestellt haben, wird eine Anweisung angezeigt, mit dem [Verbindungs-Manager von Linux](../linux/connect-to-your-remote-linux-computer.md) eine Verbindung mit dem Remoteziel herzustellen.

    ![Remotearchitektur](media/architecture.png)

3. Legen Sie einen Haltepunkt fest, indem Sie auf der linken Seite einer Codezeile klicken, von der Sie wissen, dass sie ausgeführt wird.

    In der Codezeile, in der Sie den Haltepunkt festlegen, wird ein roter Punkt angezeigt.

4. Drücken Sie **F5** (oder **Debuggen > Debuggen starten**), um das Debuggen zu starten.

    Wenn Sie das Debuggen starten, wird die Anwendung auf dem Remoteziel kompiliert, bevor sie gestartet wird. Fehler bei der Kompilierung werden im Fenster **Fehlerliste** angezeigt.

    Wenn keine Fehler vorliegen, wird die App gestartet, und der Debugger unterbricht die Ausführung am Haltepunkt.

    ![Treffen eines Haltepunkts](media/hit_breakpoint.png)  

    Jetzt können Sie mit der Anwendung in ihrem aktuellen Zustand interagieren, Variablen anzeigen und Code schrittweise durchlaufen, indem Sie Befehlstasten wie **F10** oder **F11** drücken.

4. Wenn Sie die Linux-Konsole für die Interaktion mit Ihrer App verwenden möchten, wählen Sie **Debuggen > Linux-Konsole** aus.

  ![Menü mit Linux-Konsole](media/consolemenu.png)

  In dieser Konsole werden alle Konsolenausgaben vom Zielcomputer angezeigt. Zudem werden über die Konsole Eingaben an den Zielcomputer gesendet.

  ![Linux-Konsolenfenster](media/consolewindow.png)

## <a name="configure-other-debugging-options"></a>Konfigurieren anderer Debugoptionen

* Befehlszeilenargumente können mit dem Element **Programmargumente** auf der Eigenschaftenseite **Debugging** des Projekts an die ausführbare Datei übergeben werden.
  
  ![Programmargumente](media/settings_programarguments.png)

* Bestimmte Debuggeroptionen können mit dem Eintrag **Weitere Debuggerbefehle** an GDB übergeben werden.  Beispiel: SIGILL-Signale (unzulässige Anweisung) sollen ignoriert werden.  Hierzu können Sie den **handle**-Befehl verwenden.  Fügen Sie wie oben dargestellt Folgendes zum Eintrag **Weitere Debuggerbefehle** hinzu:

  ```handle SIGILL nostop noprint```

## <a name="see-also"></a>Siehe auch
[C++-Debugeigenschaften (Linux C++)](../linux/prop-pages/debugging-linux.md).
