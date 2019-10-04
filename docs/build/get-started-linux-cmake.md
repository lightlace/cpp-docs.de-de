---
title: Erstellen plattformübergreifender C++-Projekte in Visual Studio
description: In diesem Tutorial lernen Sie, wie Sie ein Open Source-CMake-Projekt in C++ in Visual Studio für Linux und Windows erstellen, kompilieren und debuggen können.
author: mikeblome
ms.topic: tutorial
ms.date: 03/05/2019
ms.openlocfilehash: cd01d5e389bda46fbb05d297ece8e68ef2265725
ms.sourcegitcommit: c53a3efcc5d51fc55fa57ac83cca796b33ae888f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2019
ms.locfileid: "71960725"
---
# <a name="tutorial-create-c-cross-platform-projects-in-visual-studio"></a>Tutorial: Erstellen plattformübergreifender C++-Projekte in Visual Studio 

Die Entwicklung mit C und C++ in Visual Studio eignet sich nicht nur für Windows-Anwendungen. In diesem Tutorial erfahren Sie, wie Sie in Visual Studio mit C++ basierend auf CMake plattformübergreifend entwickeln können, ohne Visual Studio-Projekte erstellen oder generieren zu müssen. Wenn Sie einen Ordner öffnen, der die Datei „CMakeLists.txt“ enthält, konfiguriert Visual Studio automatisch IntelliSense und die Buildeinstellungen. Sie können Ihren Code in Visual Studio lokal unter Windows erstellen, bearbeiten und debuggen und dann Ihre Konfiguration so anpassen, dass das gleiche für Linux geschieht.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
> * Klonen eines Open Source-CMake-Projekts über GitHub
> * Öffnen des Projekts in Visual Studio 
> * Erstellen und Debuggen eines ausführbaren Ziels unter Windows
> * Hinzufügen einer Verbindung zu einem Linux-Computer
> * Erstellen und Debuggen des gleichen Ziels unter Linux

## <a name="prerequisites"></a>Erforderliche Komponenten

- Einrichten von Visual Studio für die plattformübergreifende C++-Entwicklung
    - Zunächst müssen Sie [Visual Studio installieren](https://visualstudio.microsoft.com/vs/). Überprüfen Sie als Nächstes, dass die Workloads **Desktopentwicklung mit C++** und **Linux Entwicklung mit C++** installiert sind. Diese Installation mit den wichtigsten Komponenten ist nur 3 GB groß. Je nach Downloadgeschwindigkeit Ihres Internetanschlusses sollte die Installation also nicht länger als zehn Minuten dauern.
- Einrichten eines Linux-Computers für die plattformübergreifende C++-Entwicklung
    - Visual Studio erfordert keine bestimmte Linux-Distribution. Das Betriebssystem kann auf einem physischen Computer, einer VM und auf dem Windows-Subsystem für Linux (WSL) ausgeführt werden. Für dieses Tutorial benötigen Sie eine grafische Umgebung. Aus diesem Grund wird von der Verwendung des WSL abgeraten, da dieses hauptsächlich für Befehlszeilenvorgänge ausgelegt ist.
    - Visual Studio erfordert die folgenden Tools auf dem Linux-Computer: C++Compiler, gdb, SSH, rsync und zip. Unter auf Debian basierten Systemen können Sie diese Abhängigkeiten folgendermaßen installieren.
    
    ```cmd
        sudo apt install -y openssh-server build-essential gdb rsync zip
    ```
    - Visual Studio erfordert eine aktuelle Version von CMake auf dem Linux-Computer, in der der Servermodus aktiviert ist (mindestens 3.8). Microsoft gibt einen universellen CMake-Build heraus, den Sie auf allen Linux-Distributionen veröffentlichen können. Es wird empfohlen, dass Sie diesen Build verwenden, damit Sie die neuesten Funktionen verwenden können. Sie können die CMake-Binärdateien aus dem [Microsoft-Fork des CMake-Repositorys](https://github.com/Microsoft/CMake/releases) auf GitHub herunterladen. Navigieren Sie dorthin, und laden Sie die Version herunter, die der Systemarchitektur Ihres Linux-Computers entspricht. Markieren Sie sie anschließend als ausführbare Datei:
    
    ```cmd
        wget <path to binary>
        chmod +x cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh
    ```
    - Sie sehen die Optionen zum Ausführen des Skripts mit `-–help`. Es wird empfohlen, dass Sie die Option `–prefix` verwenden, um die Installation unter **/usr/local** durchzuführen. Dies ist der Standardspeicherort, an dem Visual Studio nach CMake sucht. Im folgenden Beispiel sehen Sie das Linux-x86_64-Skript. Sie können dieses nach Bedarf anpassen. 
    
    ```cmd
        sudo ./cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh --skip-license --prefix=/usr/local
    ```
- Auf Ihrem Windows-Computer muss Git für Windows installiert sein.
- Ein GitHub-Konto.

## <a name="clone-an-open-source-cmake-project-from-github"></a>Klonen eines Open Source-CMake-Projekts über GitHub

In diesem Tutorial verwenden wir das Bullet Physics SDK von GitHub, das Konflikte erkennt und physikalische Simulationen für unterschiedliche Anwendungen durchführen kann. Das SDK enthält ausführbare Beispielprogramme, die kompiliert und ausgeführt werden können, ohne zusätzlichen Code schreiben zu müssen. In diesem Tutorial wird der Quellcode nicht angepasst und wir erstellen keine Skripts. Klonen Sie zunächst das Repository bullet3 von GitHub auf dem Computer, auf dem Visual Studio installiert ist. 

```cmd

git clone https://github.com/bulletphysics/bullet3.git

```

1. Wählen Sie im Hauptmenü von Visual Studio **Datei > Öffnen > CMake** aus, und navigieren Sie zur Datei „CMakeLists.txt“ am Stamm des Repositorys bullet3, das Sie gerade heruntergeladen haben.

    ![Visual Studio-Menü „Datei > Öffnen > CMake“](media/cmake-open-cmake.png)

    Wenn Sie den Ordner öffnen, wir Ihre Ordnerstruktur im **Projektmappen-Explorer** angezeigt.

    ![Ordneransicht im Projektmappen-Explorer von Visual Studio](media/cmake-bullet3-solution-explorer.png)

    In dieser Ansicht sehen Sie genau, was sich auf dem Datenträger befindet. Die Ansicht ist nicht logisch oder gefiltert. Standardmäßig werden keine ausgeblendeten Dateien angezeigt. 

2. Klicken Sie auf die Schaltfläche zum **Anzeigen aller Dateien**, um alle Dateien im Ordner anzuzeigen.

    ![Schaltfläche zum Anzeigen aller Dateien im Projektmappen-Explorer von Visual Studio](media/cmake-bullet3-show-all-files.png)

## <a name="switch-to-targets-view"></a>Wechseln zur Zielansicht

Wenn Sie einen Ordner öffnen, der CMake verwendet, generiert Visual Studio automatisch einen CMake-Cache. Je nach Größe des Projekts kann dieser Vorgang etwas Zeit in Anspruch nehmen. 

1. Wählen Sie im **Ausgabefenster** **Ausgabe anzeigen von:** aus, und wählen Sie dann **CMake**, um den Status der Cacheerstellung zu überwachen. Sobald der Vorgang abgeschlossen ist, wird „Extrahieren von Zielinformationen abgeschlossen.“ angezeigt.

    ![Visual Studio-Ausgabefenster mit Ausgabe aus CMake](media/cmake-bullet3-output-window.png)

    Nachdem dieser Vorgang abgeschlossen wurde, wird IntelliSense konfiguriert, das Projekt kann erstellt werden, und Sie können die Anwendung debuggen. Visual Studio kann jetzt eine logische Ansicht der Projektmappe basierend auf den Zielen anzeigen, die in den CMakeLists-Dateien angegeben werden. 

2. Über die Schaltfläche für **Projektmappen und Ordner** im **Projektmappen-Explorer** können Sie zur CMake-Zielansicht wechseln.

    ![Schaltfläche für Projektmappen und Ordner im Projektmappen-Explorer zum Wechseln zur CMake-Zielansicht](media/cmake-bullet3-show-targets.png)

    Die Ansicht für das Bullet Physics SDK sieht wie folgt aus:

    ![CMake-Zielansicht im Projektmappen-Explorer](media/cmake-bullet3-targets-view.png)

    Mit der Zielansicht erhalten Sie eine intuitivere Ansicht der Inhalte einer Quellbasis. Sie erkennen, dass einige Ziele Bibliotheken und andere ausführbare Dateien sind. 

3. Erweitern Sie einen Knoten in der CMake-Zielansicht, um die Quellcodedateien anzuzeigen, egal wo sich diese auf dem Datenträger befinden.

## <a name="add-an-explicit-windows-x64-debug-configuration"></a>Hinzufügen einer expliziten Windows x64-Debug-Konfiguration

Visual Studio erstellt eine standardmäßige **x64-Debug-** Konfiguration für Windows. Durch Konfigurationen wird festgelegt, welche Plattformziele von Visual Studio für CMake verwendet werden sollen. Die Standardkonfiguration ist standardmäßig nicht auf dem Datenträger vorhanden. Wenn Sie eine Konfiguration explizit hinzufügen, erstellt Visual Studio eine Datei mit dem Namen „CMakeSettings.json“, die mit Einstellungen für alle angegebenen Konfigurationen aufgefüllt wird. 

1. Klicken Sie zum Hinzufügen einer neuen Konfiguration in der Symbolleiste auf die Konfigurationsdropdownmenü, und wählen Sie **Konfigurationen verwalten...** aus.

    ![Dropdownmenü „Konfigurationen verwalten“](media/cmake-bullet3-manage-configurations.png)

    Dadurch wird der Editor für die [cmake-Einstellungen](customize-cmake-settings.md)geöffnet. Wählen Sie auf der linken Seite des Editors das grüne Pluszeichen aus, um eine neue Konfiguration hinzuzufügen. Das Dialogfeld **Konfiguration zu CMakeSettings hinzufügen** wird angezeigt.

    ![Dialogfeld „Konfiguration zu CMakeSettings hinzufügen“](media/cmake-bullet3-add-configuration-x64-debug.png)

    In diesem Dialogfeld werden alle Konfigurationen angezeigt, die in Visual Studio enthalten sind, sowie alle benutzerdefinierten Konfigurationen, die Sie erstellt haben. Wenn Sie weiterhin eine **x64-Debug-** Konfiguration verwenden möchten, sollten Sie diese zuerst hinzufügen. Klicken Sie auf **x64-Debug** und dann auch **Auswählen**. Dadurch wird die Datei "cmakesettings. JSON" mit einer Konfiguration für **x64-Debug** erstellt und auf dem Datenträger gespeichert. Sie können Ihre Konfigurationen beliebig benennen, indem Sie den Namensparameter direkt in „CMakeSettings.json“ ändern.

## <a name="set-a-breakpoint-build-and-run-on-windows"></a>Festlegen eines halte Punkts, erstellen und Ausführen unter Windows 

In diesem Schritt debuggen wir ein Beispielprogramm, das die Bullet Physics-Bibliothek veranschaulicht.
  
1. Wählen Sie „AppBasicExampleGui“ im **Projektmappen-Explorer**, und erweitern Sie es. 
1. Öffnen Sie die Datei `BasicExample.cpp`. 
1. Legen Sie einen Breakpoint fest, der erreicht werden soll, wenn Sie in der ausgeführten Anwendung klicken. Das Klickereignis wird in einer Methode in einer Hilfsklasse behandelt. Führen Sie folgende Schritte aus, um schnell dorthin zu gelangen:

    1. Wählen Sie das `CommonRigidBodyBase`-Objekt, von dem die Struktur `BasicExample` abgeleitet wird. Dieses befindet sich etwa in Zeile 30.
    1. Klicken Sie mit der rechten Maustaste, und wählen Sie **Gehe zu Definition**. Sie befinden sich jetzt in „CommonRigidBodyBase.h“. 
    1. In der Browseransicht über Ihrer Quelle sollten Sie sehen, dass Sie sich in `CommonRigidBodyBase` befinden. Rechts können Sie Member auswählen, die Sie sich genauer ansehen möchten. Öffnen Sie das Dropdownmenü, und wählen Sie `mouseButtonCallback`, um zur Definition dieser Funktion im Header zu wechseln.

        ![Symbolleiste der Memberliste in Visual Studio](media/cmake-bullet3-member-list-toolbar.png)

1. Setzen Sie in der ersten Zeile dieser Funktion einen Breakpoint. An diesem Breakpoint wird die Ausführung angehalten, wenn Sie eine Maustaste im Fenster der Anwendung drücken, wenn diese im Visual Studio-Debugger gestartet wird.

1. Sie können die Anwendung starten, indem Sie auf das Dropdownmenü „Startelement auswählen“ mit dem Wiedergabesymbol in der Symbolleiste klicken. Klicken Sie im Dropdownmenü auf „AppBasicExampleGui.exe“. Der Name der ausführbaren Datei wird jetzt auf der Startschaltfläche angezeigt:

    ![Startdropdownmenü auf der Symbolleiste von Visual Studio für „Startelement auswählen“](media/cmake-bullet3-launch-button.png)

5.  Klicken Sie auf die Startschaltfläche, um die Anwendung und erforderliche Abhängigkeiten zu erstellen. Starten Sie sie anschließend mit angefügtem Visual Studio-Debugger. Nach kurzer Zeit wird die ausgeführte Anwendung angezeigt:

    ![Debugging einer Windows-Anwendung in Visual Studio](media/cmake-bullet3-launched.png)

6. Bewegen Sie den Mauszeiger in das Anwendungsfenster, und drücken Sie anschließend eine Taste, um den Breakpoint auszulösen. Dadurch wird Visual Studio wieder im Vordergrund angezeigt, und der Editor zeigt die Zeile an, bei der die Ausführung angehalten wurde. Sie können sich die Variablen, Objekte und Threads der Anwendung ansehen. Sie können den Code zudem schrittweise interaktiv ausführen. Sie können auf **Weiter** klicken, um die Ausführung der Anwendung normal fortzusetzen und zu beenden, oder Sie können die Ausführung mit der Stoppschaltfläche abbrechen.

##  <a name="add-a-linux-configuration-and-connect-to-the-remote-machine"></a>Hinzufügen einer Linux-Konfiguration und Verbinden mit dem Remotecomputer

1. Fügen Sie als Nächstes eine Linux-Konfiguration hinzu. Klicken Sie mit der rechten Maustaste im **Projektmappen-Explorer** auf die Datei „CMakeSettings.json“, und wählen Sie **Konfiguration hinzufügen** aus. Das Dialogfeld „Konfiguration zu CMakeSettings hinzufügen“ wird geöffnet, das Sie schon aus dem vorherigen Schritt kennen. Wählen Sie **Linux-Debuggen** Sie dieses Mal aus, und speichern Sie dann die Datei cmakesettings. JSON (Strg + s). 
2. Wählen Sie anschließend **Linux-Debug** aus dem Dropdownmenü aus.

    ![Konfigurationsdropdownmenü mit den Optionen x64-Debug und Linux-Debug](media/cmake-bullet3-linux-configuration-item.png)

    Wenn Sie zum ersten Mal eine Verbindung mit einem Linux-System herstellen, wird das Dialogfeld **Mit Remotesystem verbinden** angezeigt.

    ![Dialogfeld „Mit Remotesystem verbinden“ in Visual Studio](media/cmake-bullet3-connection-manager.png)

    Wenn Sie bereits eine Remoteverbindung hinzugefügt haben, können Sie das Fenster über **Extras > Optionen > Plattformübergreifend > Verbindungs-Manager > Hinzufügen** öffnen.
 
3. Geben Sie die [Verbindungsinformationen für Ihren Linux-Computer] (Connect-to-your-Remote-Linux-Computer.MD] an, und klicken Sie auf **verbinden**. Dieser Computer wird von Visual Studio als Standardverbindung für **Linux-Debug**als "cmakesettings. JSON" hinzugefügt. Außerdem werden die Header vom Remote Computer abgerufen, sodass Sie [IntelliSense speziell für diese Remote Verbindung](https://docs.microsoft.com/en-us/cpp/linux/configure-a-linux-project?view=vs-2019#remote_intellisense)erhalten. Nun werden Ihre Dateien von Visual Studio an den Remote Computer gesendet, und der cmake-Cache wird auf dem Remote System generiert. Diese Schritte können abhängig von der Netzwerkgeschwindigkeit und der Leistung Ihres Remotecomputers einige Zeit in Anspruch nehmen. Der Vorgang ist abgeschlossen, wenn im CMake-Ausgabefenster „Target info extraction done“ (Extrahieren der Zielinformationen abgeschlossen) angezeigt wird.

## <a name="set-a-breakpoint-build-and-run-on-linux"></a>Festlegen eines Breakpoints, Erstellen und Ausführen unter Linux

Da es sich um eine Desktopanwendung handelt, müssen Sie weitere Konfigurationsinformationen für die Debugkonfiguration angeben. 

1. Klicken Sie in der CMake-Zielansicht mit der rechten Maustaste auf „AppBasicExampleGui“, und wählen Sie **Einstellungen für Debuggen und Starten** aus, um die Datei „launch.vs.json“ zu öffnen, die sich im versteckten **.vs**-Unterordner befindet. Diese Datei befindet sich lokal in Ihrer Entwicklungsumgebung. Sie können sie zum Stamm Ihres Projekts verschieben, wenn Sie sie bei Ihrem Team einchecken und speichern möchten. In dieser Datei wurde eine Konfiguration für „AppBasicExampleGui“ hinzugefügt. Diese Standardeinstellungen funktionieren in den meisten Fällen. Da es sich bei unserer Anwendung jedoch um eine Desktopanwendung handelt, müssen Sie weitere Informationen angeben, um das Programm starten und dieses auch auf Ihrem Linux-PC sehen zu können. 
2. Dazu benötigen Sie den Wert der Umgebungsvariablen `DISPLAY` auf Ihrem Linux-Computer. Führen Sie den folgenden Befehl aus, um diesen zu erhalten.

    ```cmd
    echo $DISPLAY
    ```

    In der Konfiguration für „AppBasicExampleGui“ gibt es das Parameterarray „pipeArgs“. Darin gibt es die Zeile "${debuggerCommand}". Mit diesem Befehl wird gdb auf dem Remotecomputer gestartet. Visual Studio muss die Anzeige in diesem Kontext exportieren, bevor dieser Befehl ausgeführt wird. Wenn der Wert Ihrer Anzeige z.B. „:1“ ist, passen Sie die Zeile wie folgt an:

    ```cmd
    "export DISPLAY=:1;${debuggerCommand}",
    ```
3. Sie können Ihre Anwendung starten und debuggen, indem Sie das Dropdownmenü **Startelement auswählen** auf der Symbolleiste öffnen und „AppBasicExampleGui“ auswählen. Klicken Sie auf die Wiedergabeschaltfläche, oder drücken Sie **F5**. Dadurch wird die Anwendung und ihre Abhängigkeiten auf dem Linux-Remotecomputer erstellt. Starten Sie sie anschließend mit angefügtem Visual Studio-Debugger. Auf Ihrem Linux-Remotecomputer sollte ein Anwendungsfenster geöffnet werden.

4. Bewegen Sie den Mauszeiger in das Anwendungsfenster, und drücken Sie anschließend eine Taste, um den Breakpoint auszulösen. Die Ausführung des Programms wird am Breakpoint angehalten, und Visual Studio wird wieder im Vordergrund angezeigt. Außerdem sollte ein Linux-Konsolenfenster in Visual Studio angezeigt werden. In diesem Fenster wird die Ausgabe des Linux-Computers angezeigt, und es kann auch Eingaben für `stdin` akzeptieren. Wie jedes andere Visual Studio-Fenster können Sie es an einer gewünschten Stelle andocken. Diese Position wird auch in zukünftigen Sitzung beibehalten.

    ![Linux-Konsolenfenster in Visual Studio](media/cmake-bullet3-linux-console.png)

5. Sie können sich die Variablen, Objekte, Threads und den Arbeitsspeicher der Anwendung ansehen und Ihren Code in Visual Studio schrittweise und interaktiv ausführen. Dieses Mal führen Sie diese Schritt jedoch auf einem Linux-Remotecomputer statt auf einem lokalen Windows-Computer aus. Sie können auf **Weiter** klicken, um die Ausführung der Anwendung normal fortzusetzen und zu beenden, oder Sie können die Ausführung mit der Stoppschaltfläche abbrechen, wie Sie es auch bei der lokalen Ausführung tun würden.

6. Sehen Sie sich das Aufruflistenfenster an, und zeigen Sie die Aufrufe von `x11OpenGLWindow` seit dem Start der Anwendung durch Visual Studio auf dem Linux-Computer an.

    ![Fenster „Aufrufliste“ mit der Linux-Aufrufliste](media/cmake-bullet3-linux-callstack.png)

## <a name="what-you-learned"></a>Zusammenfassung 

In diesem Tutorial haben Sie gelernt, wie Sie eine Codebasis direkt über GitHub klonen können, und Sie haben erfahren, wie Sie eine Anwendung unter Windows ohne zusätzliche Modifizierungen erstellen, ausführen und debuggen können. Dieselbe Codebasis haben Sie dann mit geringfügigen Änderungen der Konfiguration auf einem Linux-Remotecomputer erstellt, ausgeführt und gedebuggt. 

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
