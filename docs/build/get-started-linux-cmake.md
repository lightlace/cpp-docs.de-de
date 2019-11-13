---
title: Erstellen plattformübergreifender C++-Projekte in Visual Studio
description: Einrichten, kompilieren und Debuggen eines C++ Open Source-cmake-Projekts in Visual Studio, das auf Linux und Windows abzielt.
author: mikeblome
ms.topic: tutorial
ms.date: 11/08/2019
ms.openlocfilehash: 05f120335180d27e84a99819ee97c233dd1b39a7
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73965100"
---
# <a name="tutorial-create-c-cross-platform-projects-in-visual-studio"></a>Tutorial: Erstellen C++ von plattformübergreifenden Projekten in Visual Studio

Die Entwicklung mit C und C++ in Visual Studio eignet sich nicht nur für Windows-Anwendungen. In diesem Tutorial wird gezeigt, wie Sie Visual C++ Studio für die plattformübergreifende Entwicklung unter Windows und Linux verwenden. Sie basiert auf cmake, sodass Sie keine Visual Studio-Projekte erstellen oder generieren müssen. Wenn Sie einen Ordner öffnen, der die Datei "CMakeLists. txt" enthält, konfiguriert Visual Studio automatisch die IntelliSense-und Buildeinstellungen. Sie können schnell mit der Bearbeitung, dem Aufbau und dem Debuggen von Code in Windows beginnen. Wechseln Sie anschließend in Visual Studio zu Ihrer Konfiguration, um die gleiche unter Linux zu verwenden.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
> * Klonen eines Open Source-CMake-Projekts über GitHub
> * Öffnen des Projekts in Visual Studio
> * Erstellen und Debuggen eines ausführbaren Ziels unter Windows
> * Hinzufügen einer Verbindung zu einem Linux-Computer
> * Erstellen und Debuggen des gleichen Ziels unter Linux

## <a name="prerequisites"></a>Erforderliche Voraussetzungen

* Einrichten von Visual Studio für die plattformübergreifende C++-Entwicklung
  * Installieren Sie zunächst [Visual Studio](https://visualstudio.microsoft.com/vs/) , und wählen Sie die **Desktop C++ Entwicklung mit** und die **Linux-Entwicklung mit C++ Workloads**aus. Bei dieser minimalen Installation handelt es sich nur um 3 GB. Abhängig von ihrer Downloadgeschwindigkeit sollte die Installation nicht mehr als 10 Minuten dauern.

* Einrichten eines Linux-Computers für die plattformübergreifende C++-Entwicklung
  * Visual Studio erfordert keine bestimmte Linux-Distribution. Das Betriebssystem kann auf einem physischen Computer, einem virtuellen Computer oder in der Cloud ausgeführt werden. Sie können auch das Windows-Subsystem für Linux (WSL) verwenden. Für dieses Tutorial ist jedoch eine grafische Umgebung erforderlich. WSL wird hier nicht empfohlen, da es in erster Linie für Befehlszeilen Vorgänge vorgesehen ist.
  * Visual Studio erfordert diese Tools auf dem Linux-Computer C++ : Compiler, gdb, SSH, rsync und zip. In Debian-basierten Systemen können Sie diesen Befehl verwenden, um diese Abhängigkeiten zu installieren:

    ```cmd
    sudo apt install -y openssh-server build-essential gdb rsync zip
    ```

  * Visual Studio erfordert eine neuere Version von cmake auf dem Linux-Computer, auf dem der Server Modus aktiviert ist (mindestens 3,8). Microsoft gibt einen universellen CMake-Build heraus, den Sie auf allen Linux-Distributionen veröffentlichen können. Es wird empfohlen, diesen Build zu verwenden, um sicherzustellen, dass Sie über die neuesten Features verfügen. Sie können die CMake-Binärdateien aus dem [Microsoft-Fork des CMake-Repositorys](https://github.com/Microsoft/CMake/releases) auf GitHub herunterladen. Wechseln Sie zu dieser Seite, und laden Sie die Version herunter, die der Systemarchitektur auf Ihrem Linux-Computer entspricht, und markieren Sie Sie als ausführbare Datei:

    ```cmd
    wget <path to binary>
    chmod +x cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh
    ```

  * Sie sehen die Optionen zum Ausführen des Skripts mit `-–help`. Es wird empfohlen, dass Sie die `–prefix`-Option verwenden, um die Installation im Pfad **/usr/local** anzugeben, da dies der Standard Speicherort ist, an dem Visual Studio nach cmake sucht. Im folgenden Beispiel sehen Sie das Linux-x86_64-Skript. Ändern Sie ihn nach Bedarf, wenn Sie eine andere Zielplattform verwenden.

    ```cmd
    sudo ./cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh --skip-license --prefix=/usr/local
    ```

* Auf Ihrem Windows-Computer muss Git für Windows installiert sein.
* Ein GitHub-Konto.

## <a name="clone-an-open-source-cmake-project-from-github"></a>Klonen eines Open Source-CMake-Projekts über GitHub

In diesem Tutorial wird das Bullet-Physik-SDK auf GitHub verwendet. Es bietet eine Kollisionserkennung und physikalische Simulationen für viele Anwendungen. Das SDK enthält ausführbare Beispiel Programme, die kompiliert und ausgeführt werden, ohne dass zusätzlicher Code geschrieben werden muss. In diesem Tutorial werden keine der Quellcodes oder Buildskripts geändert. Klonen Sie zunächst das *bullet3* -Repository von GitHub auf dem Computer, auf dem Visual Studio installiert ist.

```cmd
git clone https://github.com/bulletphysics/bullet3.git
```

1. Wählen Sie im Hauptmenü von Visual Studio **Datei > > cmake öffnen**aus. Navigieren Sie zur Datei "CMakeLists. txt" im Stammverzeichnis des bullet3-Repository, das Sie soeben heruntergeladen haben.

    ![Visual Studio-Menü „Datei > Öffnen > CMake“](media/cmake-open-cmake.png)

    Sobald Sie den Ordner öffnen, wird die Ordnerstruktur im **Projektmappen-Explorer**sichtbar.

    ![Ordneransicht im Projektmappen-Explorer von Visual Studio](media/cmake-bullet3-solution-explorer.png)

    In dieser Ansicht sehen Sie genau, was sich auf dem Datenträger befindet. Die Ansicht ist nicht logisch oder gefiltert. Standardmäßig werden keine ausgeblendeten Dateien angezeigt.

1. Wählen Sie die Schaltfläche **alle Dateien anzeigen** aus, um alle Dateien im Ordner anzuzeigen.

    ![Schaltfläche zum Anzeigen aller Dateien im Projektmappen-Explorer von Visual Studio](media/cmake-bullet3-show-all-files.png)

## <a name="switch-to-targets-view"></a>Wechseln zur Zielansicht

Wenn Sie einen Ordner öffnen, der CMake verwendet, generiert Visual Studio automatisch einen CMake-Cache. Je nach Größe des Projekts kann dieser Vorgang etwas Zeit in Anspruch nehmen.

1. Wählen Sie im **Ausgabefenster** **Ausgabe anzeigen von:** aus, und wählen Sie dann **CMake**, um den Status der Cacheerstellung zu überwachen. Sobald der Vorgang abgeschlossen ist, wird „Extrahieren von Zielinformationen abgeschlossen.“ angezeigt.

   ![Visual Studio-Ausgabefenster mit Ausgabe aus CMake](media/cmake-bullet3-output-window.png)

   Nachdem dieser Vorgang abgeschlossen ist, wird IntelliSense konfiguriert. Sie können das Projekt erstellen und die Anwendung debuggen. Visual Studio zeigt nun eine logische Ansicht der Projekt Mappe an, die auf den in den CMakeLists-Dateien angegebenen Zielen basiert.

1. Über die Schaltfläche für **Projektmappen und Ordner** im **Projektmappen-Explorer** können Sie zur CMake-Zielansicht wechseln.

   ![Schaltfläche für Projektmappen und Ordner im Projektmappen-Explorer zum Wechseln zur CMake-Zielansicht](media/cmake-bullet3-show-targets.png)

   Die Ansicht für das Bullet Physics SDK sieht wie folgt aus:

   ![CMake-Zielansicht im Projektmappen-Explorer](media/cmake-bullet3-targets-view.png)

   Mit der Zielansicht erhalten Sie eine intuitivere Ansicht der Inhalte einer Quellbasis. Sie erkennen, dass einige Ziele Bibliotheken und andere ausführbare Dateien sind.

1. Erweitern Sie einen Knoten in der CMake-Zielansicht, um die Quellcodedateien anzuzeigen, egal wo sich diese auf dem Datenträger befinden.

## <a name="add-an-explicit-windows-x64-debug-configuration"></a>Hinzufügen einer expliziten Windows x64-Debug-Konfiguration

Visual Studio erstellt eine standardmäßige **x64-Debug-** Konfiguration für Windows. Durch Konfigurationen wird festgelegt, welche Plattformziele von Visual Studio für CMake verwendet werden sollen. Die Standardkonfiguration ist standardmäßig nicht auf dem Datenträger vorhanden. Wenn Sie eine Konfiguration explizit hinzufügen, erstellt Visual Studio eine Datei mit dem Namen " *cmakesettings. JSON*". Sie werden mit den Einstellungen für alle Konfigurationen aufgefüllt, die Sie angeben.

1. Fügen Sie eine neue Konfiguration hinzu. Öffnen Sie in der Symbolleiste die Dropdown- **Konfiguration** , und wählen Sie **Konfigurationen verwalten**aus.

   ![Dropdownmenü „Konfigurationen verwalten“](media/cmake-bullet3-manage-configurations.png)

   Der [Editor für die cmake-Einstellungen](customize-cmake-settings.md) wird geöffnet. Wählen Sie auf der linken Seite des Editors das grüne Pluszeichen aus, um eine neue Konfiguration hinzuzufügen. Das Dialogfeld **Konfiguration zu cmakesettings hinzufügen** wird angezeigt.

   ![Dialogfeld „Konfiguration zu CMakeSettings hinzufügen“](media/cmake-bullet3-add-configuration-x64-debug.png)

   In diesem Dialogfeld werden alle Konfigurationen, die in Visual Studio enthalten sind, sowie alle von Ihnen erstellten benutzerdefinierten Konfigurationen angezeigt. Wenn Sie weiterhin eine **x64-Debug-** Konfiguration verwenden möchten, sollten Sie diese zuerst hinzufügen. Wählen Sie **x64-Debug**aus, und wählen Sie dann die Schaltfläche **auswählen** aus. Visual Studio erstellt die Datei cmakesettings. JSON mit einer Konfiguration für **x64-Debug**und speichert Sie auf dem Datenträger. Sie können Ihre Konfigurationen beliebig benennen, indem Sie den Namensparameter direkt in „CMakeSettings.json“ ändern.

## <a name="set-a-breakpoint-build-and-run-on-windows"></a>Festlegen eines halte Punkts, erstellen und Ausführen unter Windows

In diesem Schritt debuggen wir ein Beispielprogramm, das die Bullet Physics-Bibliothek veranschaulicht.
  
1. Wählen Sie „AppBasicExampleGui“ im **Projektmappen-Explorer**, und erweitern Sie es.

1. Öffnen Sie die Datei `BasicExample.cpp`.

1. Legen Sie einen Haltepunkt fest, der erreicht wird, wenn Sie in die laufende Anwendung klicken. Das Klickereignis wird in einer Methode in einer Hilfsklasse behandelt. Führen Sie folgende Schritte aus, um schnell dorthin zu gelangen:

   1. Wählen Sie `CommonRigidBodyBase` aus, von dem die Struktur `BasicExample` abgeleitet ist. Sie befindet sich in Zeile 30.

   1. Klicken Sie mit der rechten Maustaste, und wählen Sie **Gehe zu Definition**. Nun sind Sie in der Kopfzeile commonrigidbodybase. h.

   1. In der Browseransicht oberhalb Ihrer Quelle sollten Sie sehen, dass Sie sich im `CommonRigidBodyBase`befinden. Rechts können Sie Member auswählen, die Sie sich genauer ansehen möchten. Öffnen Sie die Dropdown-Datei, und wählen Sie `mouseButtonCallback` aus, um zur Definition dieser Funktion in der Kopfzeile zu wechseln.

      ![Symbolleiste der Memberliste in Visual Studio](media/cmake-bullet3-member-list-toolbar.png)

1. Setzen Sie in der ersten Zeile dieser Funktion einen Breakpoint. Sie wird erreicht, wenn Sie im Fenster der Anwendung auf eine Maustaste klicken, wenn Sie unter dem Visual Studio-Debugger ausgeführt wird.

1. Wählen Sie zum Starten der Anwendung in der Symbolleiste die Dropdown-Dropdown-Option aus. Es ist das Symbol mit dem grünen Wiedergabe Symbol, das "Start Element auswählen" heißt. Wählen Sie in der Dropdown-Dropdown-Datei die Option appbasicexamplegui. exe aus. Der Name der ausführbaren Datei wird jetzt auf der Startschaltfläche angezeigt:

   ![Startdropdownmenü auf der Symbolleiste von Visual Studio für „Startelement auswählen“](media/cmake-bullet3-launch-button.png)

1. Wählen Sie die Schaltfläche starten, um die Anwendung und die erforderlichen Abhängigkeiten zu erstellen, und starten Sie Sie dann mit dem angefügten Visual Studio-Debugger. Nach kurzer Zeit wird die ausgeführte Anwendung angezeigt:

   ![Debugging einer Windows-Anwendung in Visual Studio](media/cmake-bullet3-launched.png)

1. Bewegen Sie den Mauszeiger in das Anwendungsfenster, und drücken Sie anschließend eine Taste, um den Breakpoint auszulösen. Der Breakpoint bringt Visual Studio wieder in den Vordergrund, und der Editor zeigt die Zeile an, in der die Ausführung angehalten wird. Sie können die Anwendungsvariablen, Objekte, Threads und den Arbeitsspeicher überprüfen oder den Code interaktiv durchlaufen. Wählen Sie weiter aus, um die Anwendung **fortzusetzen** , und beenden Sie Sie dann normal. Oder beenden Sie die Ausführung in Visual Studio mithilfe der Schaltfläche "beenden".

## <a name="add-a-linux-configuration-and-connect-to-the-remote-machine"></a>Hinzufügen einer Linux-Konfiguration und Verbinden mit dem Remotecomputer

1. Fügen Sie eine Linux-Konfiguration hinzu. Klicken Sie mit der rechten Maustaste im **Projektmappen-Explorer** auf die Datei „CMakeSettings.json“, und wählen Sie **Konfiguration hinzufügen** aus. Das Dialogfeld „Konfiguration zu CMakeSettings hinzufügen“ wird geöffnet, das Sie schon aus dem vorherigen Schritt kennen. Wählen Sie **Linux-Debuggen** Sie dieses Mal aus, und speichern Sie dann die Datei cmakesettings. JSON (Strg + s).

1. Wählen Sie in der Dropdown-Konfiguration die Option **Linux-Debug** aus.

   ![Konfigurationsdropdownmenü mit den Optionen x64-Debug und Linux-Debug](media/cmake-bullet3-linux-configuration-item.png)

   Wenn Sie zum ersten Mal eine Verbindung mit einem Linux-System herstellen, wird das Dialogfeld **Verbindung mit Remote System herstellen** angezeigt.

   ![Dialogfeld „Mit Remotesystem verbinden“ in Visual Studio](media/cmake-bullet3-connection-manager.png)

   Wenn Sie bereits eine Remote Verbindung hinzugefügt haben, können Sie dieses Fenster öffnen, indem Sie zu **Tools > Optionen > plattformübergreifende > Verbindungs-Manager**navigieren.

1. Geben Sie die [Verbindungsinformationen für Ihren Linux-Computer an,](/cpp/linux/connect-to-your-remote-linux-computer.md) und wählen Sie **verbinden**aus. Dieser Computer wird von Visual Studio als Standardverbindung für **Linux-Debug**als "cmakesettings. JSON" hinzugefügt. Außerdem werden die Header vom Remote Computer abgerufen, sodass Sie [IntelliSense speziell für diese Remote Verbindung](/cpp/linux/configure-a-linux-project?view=vs-2019#remote_intellisense)erhalten. Anschließend sendet Visual Studio Ihre Dateien an den Remote Computer und generiert den cmake-Cache auf dem Remote System. Diese Schritte können einige Zeit in Anspruch nehmen, abhängig von der Geschwindigkeit des Netzwerks und der Leistung des Remote Computers. Sie wissen, dass es abgeschlossen ist, wenn die Meldung "Ziel Informations Extraktion abgeschlossen" im cmake-Ausgabefenster angezeigt wird.

## <a name="set-a-breakpoint-build-and-run-on-linux"></a>Festlegen eines halte Punkts, erstellen und Ausführen unter Linux

Da es sich um eine Desktop Anwendung handelt, müssen Sie zusätzliche Konfigurationsinformationen für die Debugkonfiguration bereitstellen.

1. Klicken Sie in der Ansicht "cmake-Ziele" mit der rechten Maustaste auf appbasicexamplegui, und wählen Sie **Einstellungen Debuggen und starten** aus, um die Datei "Launch. vs. JSON" im Unterordner "Hidden **. vs** " zu öffnen Diese Datei befindet sich lokal in Ihrer Entwicklungsumgebung. Sie können sie zum Stamm Ihres Projekts verschieben, wenn Sie sie bei Ihrem Team einchecken und speichern möchten. In dieser Datei wurde eine Konfiguration für appbasicexamplegui hinzugefügt. Diese Standardeinstellungen funktionieren in den meisten Fällen, aber hier nicht. Da es sich um eine Desktop Anwendung handelt, müssen Sie einige zusätzliche Informationen bereitstellen, um das Programm zu starten, damit Sie es auf Ihrem Linux-Computer sehen können.

1. Um den Wert der Umgebungsvariablen `DISPLAY` auf Ihrem Linux-Computer zu finden, führen Sie den folgenden Befehl aus:

   ```cmd
   echo $DISPLAY
   ```

   In der Konfiguration für appbasicexamplegui gibt es ein Parameter Array, "pipeargs". Sie enthält eine Zeile: "$ {debug-Command}". Dabei handelt es sich um den Befehl, mit dem gdb auf dem Remote Computer gestartet wird. Visual Studio muss die Anzeige in diesen Kontext exportieren, bevor der Befehl ausgeführt wird. Wenn der Wert der Anzeige z. b. `:1`ist, ändern Sie die Zeile wie folgt:

   ```cmd
   "export DISPLAY=:1;${debuggerCommand}",
   ```

1. Starten und Debuggen Sie die Anwendung. Öffnen Sie in der Symbolleiste das Dropdown **Menü Start Element auswählen** , und wählen Sie **appbasicexamplegui**aus. Wählen Sie als nächstes das grüne Wiedergabe Symbol in der Symbolleiste aus, oder drücken Sie **F5**. Die Anwendung und ihre Abhängigkeiten werden auf dem Linux-Remote Computer erstellt und dann mit dem angefügten Visual Studio-Debugger gestartet. Auf Ihrem Linux-Remotecomputer sollte ein Anwendungsfenster geöffnet werden.

1. Bewegen Sie die Maus in das Anwendungsfenster, und klicken Sie auf eine Schaltfläche. Der Breakpoint wird getroffen. Die Programmausführung wird angehalten, Visual Studio kehrt wieder in den Vordergrund, und Sie sehen den Haltepunkt. Außerdem sollte ein Linux-Konsolenfenster in Visual Studio angezeigt werden. Das Fenster stellt die Ausgabe vom Linux-Remote Computer bereit und kann auch Eingaben für `stdin`akzeptieren. Wie jedes Visual Studio-Fenster können Sie es auch dort andocken, wo Sie es bevorzugen. Seine Position wird in zukünftigen Sitzungen beibehalten.

   ![Linux-Konsolenfenster in Visual Studio](media/cmake-bullet3-linux-console.png)

1. Sie können sich die Variablen, Objekte, Threads und den Arbeitsspeicher der Anwendung ansehen und Ihren Code in Visual Studio schrittweise und interaktiv ausführen. Aber dieses Mal machen Sie es auf einem Linux-Remote Computer anstatt in der lokalen Windows-Umgebung. Sie können fortfahren auswählen, damit die Anwendung **fortgesetzt** und ordnungsgemäß beendet wird, oder Sie können die Schaltfläche Beenden wie bei der lokalen Ausführung auswählen.

1. Sehen Sie sich das Aufruflistenfenster an, und zeigen Sie die Aufrufe von `x11OpenGLWindow` seit dem Start der Anwendung durch Visual Studio auf dem Linux-Computer an.

   ![Fenster „Aufrufliste“ mit der Linux-Aufrufliste](media/cmake-bullet3-linux-callstack.png)

## <a name="what-you-learned"></a>Zusammenfassung

In diesem Tutorial haben Sie eine Codebasis direkt von GitHub geklont. Sie haben es in Windows ohne Änderungen erstellt, ausgeführt und debuggten. Anschließend haben Sie dieselbe Codebasis mit geringfügigen Konfigurationsänderungen verwendet, um auf einem Linux-Remote Computer zu erstellen, auszuführen und zu debuggen.

## <a name="next-steps"></a>Nächste Schritte

In den folgenden Artikeln erhalten Sie weitere Informationen zum Konfigurieren und Debuggen von CMake-Projekten in Visual Studio:

> [!div class="nextstepaction"]
> [CMake Projects in Visual Studio (CMake-Projekte in Visual Studio)](cmake-projects-in-visual-studio.md)<br/><br/>
> [Konfigurieren eines Linux CMake-Projekts](../linux/cmake-linux-project.md)<br/><br/>
> [Herstellen einer Verbindung mit Ihrem Linux-Remotecomputer](../linux/connect-to-your-remote-linux-computer.md)<br/><br/>
> [Anpassen von CMake-Buildeinstellungen](customize-cmake-settings.md)<br/><br/>
> [Konfigurieren von CMake-Debugsitzungen](configure-cmake-debugging-sessions.md)<br/><br/>
> [Bereitstellen, Ausführen und Debuggen Ihres Linux-Projekts](../linux/deploy-run-and-debug-your-linux-project.md)<br/><br/>
> [CMake predefined configuration reference (Referenz für vordefinierte CMake-Konfigurationen)](cmake-predefined-configuration-reference.md)
>
