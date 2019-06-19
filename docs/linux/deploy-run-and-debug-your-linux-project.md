---
title: Bereitstellen, Ausführen und Debuggen Ihres C++-Projekts unter Linux in Visual Studio
description: Informationen zum Kompilieren, Ausführen und Debuggen von Code auf dem Remoteziel in einem C++-Projekt unter Linux in Visual Studio.
ms.date: 06/07/2019
ms.assetid: f7084cdb-17b1-4960-b522-f84981bea879
ms.openlocfilehash: 707915a502aafefee47af7e84b534e06ba678b3d
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821617"
---
# <a name="deploy-run-and-debug-your-linux-project"></a>Bereitstellen, Ausführen und Debuggen eines Linux-Projekts

::: moniker range="vs-2015"

Die Unterstützung für Linux ist in Visual Studio 2017 und höher verfügbar.

::: moniker-end

Nachdem Sie ein C++-Projekt in Visual Studio unter Linux erstellt haben und mit dem [Verbindungs-Manager von Linux](connect-to-your-remote-linux-computer.md) eine Verbindung mit dem Projekt hergestellt haben, können Sie das Projekt ausführen und debuggen. Die Kompilierung, die Ausführung und das Debuggen des Codes erfolgen auf dem Remoteziel.

::: moniker range="vs-2019"

**Visual Studio 2019 Version 16.1**: Sie können für verschiedene Linux-Systeme Debug- und Buildvorgänge durchführen. Geben Sie auf der Eigenschaftenseite **Allgemein** den Buildcomputer und auf der Eigenschaftenseite **Debuggen** den Debugcomputer an.

::: moniker-end

Es gibt mehrere Möglichkeiten für den Umgang mit dem Linux-Projekt sowie zum Debuggen des Projekts.

- Debuggen Sie mit herkömmlichen Features von Visual Studio wie Haltepunkten, Überwachungsfenstern und Positionieren des Mauszeigers über einer Variablen. Mit diesen Methoden können Sie wie bei anderen Projekttypen debuggen.

- Zeigen Sie die Ausgabe vom Zielcomputer im Linux-Konsolenfenster an. Sie können die Konsole auch verwenden, um Eingaben an den Zielcomputer zu senden.

## <a name="debug-your-linux-project"></a>Debuggen eines Linux-Projekts

1. Wählen Sie den Debugmodus auf der Eigenschaftenseite **Debuggen** aus.

   
   
   ::: moniker range="vs-2019"

   GDB wird zum Debuggen von Anwendungen verwendet, die unter Linux ausgeführt werden. Beim Debuggen auf einem Remotesystem (nicht WSL) stehen gdb für die Ausführung zwei verschiedene Modi zur Verfügung, die über die Option **Debugmodus** auf der Eigenschaftenseite **Debuggen** des Projekts ausgewählt werden können:

   ![GDB-Optionen](media/vs2019-debugger-settings.png)

   ::: moniker-end

   ::: moniker range="vs-2017"

   GDB wird zum Debuggen von Anwendungen verwendet, die unter Linux ausgeführt werden. Für die Ausführung stehen GDB zwei verschiedene Modi zur Verfügung, die über die Option **Debugging Mode** (Debugmodus) auf der Eigenschaftenseite **Debugging** (Debuggen) des Projekts ausgewählt werden können:

   ![GDB-Optionen](media/vs2017-debugger-settings.png)

   ::: moniker-end


   - Im **gdbserver**-Modus wird GDB lokal ausgeführt und stellt eine Verbindung mit gdbserver auf dem Remotesystem aus.  Dies ist der einzige Modus, der vom Linux-Konsolenfenster unterstützt wird.

   - Im **GDB**-Modus steuert der Visual Studio-Debugger GDB auf dem Remotesystem. Diese Option eignet sich besser, wenn die lokale Version von GDB nicht mit der Version kompatibel ist, die auf dem Zielcomputer installiert ist. |

   > [!NOTE]
   > Wenn Sie im gdbserver-Debugmodus keine Haltepunkte treffen können, versuchen Sie es im gdb-Modus. GDB muss zunächst auf dem Remoteziel [installiert](download-install-and-setup-the-linux-development-workload.md) werden.

1. Wählen Sie das Remoteziel mit der Standardsymbolleiste **Debuggen** in Visual Studio aus.

   Wenn das Remoteziel verfügbar ist, wird es anhand des Namens oder der IP-Adresse aufgelistet.

   ![Remoteziel](media/remote_target.png)

   Wenn Sie noch keine Verbindung mit dem Remoteziel hergestellt haben, wird eine Anweisung angezeigt, mit dem [Verbindungs-Manager von Linux](connect-to-your-remote-linux-computer.md) eine Verbindung mit dem Remoteziel herzustellen.

   ![Remotearchitektur](media/architecture.png)

1. Legen Sie einen Haltepunkt fest, indem Sie auf der linken Seite einer Codezeile klicken, von der Sie wissen, dass sie ausgeführt wird.

   In der Codezeile, in der Sie den Haltepunkt festlegen, wird ein roter Punkt angezeigt.

1. Drücken Sie **F5** (oder **Debuggen > Debuggen starten**), um das Debuggen zu starten.

   Wenn Sie das Debuggen starten, wird die Anwendung auf dem Remoteziel kompiliert, bevor sie gestartet wird. Fehler bei der Kompilierung werden im Fenster **Fehlerliste** angezeigt.

   Wenn keine Fehler vorliegen, wird die App gestartet, und der Debugger unterbricht die Ausführung am Haltepunkt.

   ![Treffen eines Haltepunkts](media/hit_breakpoint.png)

   Jetzt können Sie mit der Anwendung in ihrem aktuellen Zustand interagieren, Variablen anzeigen und Code schrittweise durchlaufen, indem Sie Befehlstasten wie **F10** oder **F11** drücken.

1. Wenn Sie die Linux-Konsole für die Interaktion mit Ihrer App verwenden möchten, wählen Sie **Debuggen > Linux-Konsole** aus.

   ![Menü mit Linux-Konsole](media/consolemenu.png)

   In dieser Konsole werden alle Konsolenausgaben vom Zielcomputer angezeigt. Zudem werden über die Konsole Eingaben an den Zielcomputer gesendet.

   ![Linux-Konsolenfenster](media/consolewindow.png)

## <a name="configure-other-debugging-options"></a>Konfigurieren anderer Debugoptionen

- Befehlszeilenargumente können mit dem Element **Programmargumente** auf der Eigenschaftenseite **Debugging** (Debuggen) des Projekts an die ausführbare Datei übergeben werden.

   ![Programmargumente](media/settings_programarguments.png)

- Bestimmte Debuggeroptionen können mit dem Eintrag **Weitere Debuggerbefehle** an GDB übergeben werden.  Beispiel: SIGILL-Signale (unzulässige Anweisung) sollen ignoriert werden.  Hierzu können Sie den **handle**-Befehl verwenden.  Fügen Sie wie oben dargestellt Folgendes zum Eintrag **Weitere Debuggerbefehle** hinzu:

   `handle SIGILL nostop noprint`

## <a name="debug-with-attach-to-process"></a>Debuggen mit „An den Prozess anhängen“

Die Eigenschaftenseite [Debuggen](prop-pages/debugging-linux.md) für Visual Studio-Projekte und die **launch.vs.json**-Einstellungen für CMake-Projekte enthalten Einstellungen, über die Sie Anfügungen an laufende Prozesse durchführen können. Wenn Sie zusätzliche Steuerungsoptionen benötigen, die nicht von diesen Einstellungen abgedeckt werden, können Sie eine Datei mit dem Namen `Microsoft.MIEngine.Options.xml` am Stamm Ihrer Projektmappe oder Ihres Arbeitsbereichs ablegen. Hier sehen Sie ein einfaches Beispiel:

```xml
<?xml version="1.0" encoding="utf-8"?>
<SupplementalLaunchOptions>
    <AttachOptions>
      <AttachOptionsForConnection AdditionalSOLibSearchPath="/home/user/solibs">
        <ServerOptions MIDebuggerPath="C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise\Common7\IDE\VC\Linux\bin\gdb\7.9\x86_64-linux-gnu-gdb.exe"
ExePath="C:\temp\ConsoleApplication17\ConsoleApplication17\bin\x64\Debug\ConsoleApplication17.out"/>
        <SetupCommands>
          <Command IgnoreFailures="true">-enable-pretty-printing</Command>
        </SetupCommands>
      </AttachOptionsForConnection>
    </AttachOptions>
</SupplementalLaunchOptions>
```

Das Objekt **AttachOptionsForConnection** verfügt über die meisten Attribute, die Sie möglicherweise brauchen. Das oben stehende Beispiel veranschaulicht, wie Sie einen Speicherort für die Suche nach zusätzlichen SO-Bibliotheken angeben. Durch das untergeordnete Element **ServerOptions** können Sie stattdessen Anfügungen an den Remoteprozess mit gdbserver durchführen. Dazu müssen Sie einen lokalen gdb-Client (der mit Visual Studio 2017 ausgelieferte wird oben gezeigt) und eine lokale Kopie der Binärdatei mit Symbolen angeben. Durch das Element **SetupCommands** können Sie Befehle direkt an gdb übergeben. Alle verfügbaren Optionen finden Sie im [LaunchOptions.xsd-Schema](https://github.com/Microsoft/MIEngine/blob/master/src/MICore/LaunchOptions.xsd) auf GitHub.

## <a name="next-steps"></a>Nächste Schritte

- Informationen zum Debuggen von ARM-Geräten unter Linux finden Sie im folgenden Blogbeitrag: [Debugging an embedded ARM device in Visual Studio (Debuggen eines eingebetteten ARM-Geräts in Visual Studio)](https://blogs.msdn.microsoft.com/vcblog/2018/01/10/debugging-an-embedded-arm-device-in-visual-studio/).

## <a name="see-also"></a>Siehe auch

[C++-Debugeigenschaften (Linux C++)](prop-pages/debugging-linux.md)
