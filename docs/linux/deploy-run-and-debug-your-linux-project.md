---
title: Bereitstellen, Ausführen und Debuggen Ihres C++-Projekts unter Linux in Visual Studio | Microsoft-Dokumentation
description: Informationen zum Kompilieren, Ausführen und Debuggen von Code auf dem Remoteziel in einem C++-Projekt unter Linux in Visual Studio.
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: f7084cdb-17b1-4960-b522-f84981bea879
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 964da719da8d6f48131fc60f7e7fdfb247637fbf
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50069946"
---
# <a name="deploy-run-and-debug-your-linux-project"></a>Bereitstellen, Ausführen und Debuggen eines Linux-Projekts

Nachdem Sie ein C++-Projekt in Visual Studio unter Linux erstellt haben und mit dem [Verbindungs-Manager von Linux](../linux/connect-to-your-remote-linux-computer.md) eine Verbindung mit dem Projekt hergestellt haben, können Sie das Projekt ausführen und debuggen. Die Kompilierung, die Ausführung und das Debuggen des Codes erfolgen auf dem Remoteziel.

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

## <a name="next-steps"></a>Nächste Schritte

* Informationen zum Debuggen von ARM-Geräten unter Linux finden Sie in folgendem Blogbeitrag: [Debugging an embedded ARM device in Visual Studio (Debuggen eines eingebetteten ARM-Geräts in Visual Studio)](https://blogs.msdn.microsoft.com/vcblog/2018/01/10/debugging-an-embedded-arm-device-in-visual-studio/).

* Wenn Sie mithilfe des Befehls **An den Prozess anhängen** einen Debugvorgang ausführen möchten, lesen Sie diesen Blogbeitrag: [Linux C++ Workload improvements to the Project System, Linux Console Window, rsync and Attach to Process (Verbesserungen der Linux C++-Workload für das Projektsystem, die Linux-Konsole, Windows, rsync und „An den Prozess anhängen“)](https://blogs.msdn.microsoft.com/vcblog/2018/03/13/linux-c-workload-improvements-to-the-project-system-linux-console-window-rsync-and-attach-to-process/)

## <a name="see-also"></a>Siehe auch
[C++-Debugeigenschaften (Linux C++)](../linux/prop-pages/debugging-linux.md).
