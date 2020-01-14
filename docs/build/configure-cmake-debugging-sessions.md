---
title: Konfigurieren von CMake-Debugsitzungen in Visual Studio
description: Beschreibt die Verwendung von Visual Studio zum Konfigurieren der cmake-Debugger-Einstellungen.
ms.date: 01/13/2020
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: ff1de8241c2489e675f82f469f1cf697a72f5034
ms.sourcegitcommit: 275b71219d2a8bd5d78f87e21dd909e9968c2f44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75946813"
---
# <a name="configure-cmake-debugging-sessions"></a>Konfigurieren von CMake-Debugsitzungen

::: moniker range="vs-2015"

Native cmake-Unterstützung ist in Visual Studio 2017 und höher verfügbar.

::: moniker-end

::: moniker range=">=vs-2017"

Alle ausführbaren CMake-Ziele werden in der Dropdownliste **Startelement** auf der Symbolleiste **Allgemein** angezeigt. Wählen Sie eines aus, und starten Sie den Debugger, um eine Debugsitzung zu starten.

![Dropdown für cmake-Start Element](media/cmake-startup-item-dropdown.png "Dropdown für cmake-Start Element")

Sie können auch eine Debugsitzung aus Projektmappen-Explorer starten. Wechseln Sie zunächst in das Fenster **Projektmappen-Explorer** in die **Ansicht cmake-Ziele** .

![Cmake-Ziel Ansicht](media/cmake-targets-view.png  "Cmake-Ziel Ansicht (Menü Element)")

Klicken Sie dann mit der rechten Maustaste auf eine beliebige ausführbare Datei, und wählen Sie **Debuggen** , **Debug und Start** **Debuggen** beginnt automatisch mit dem Debuggen des ausgewählten Ziels, basierend auf Ihrer aktiven Konfiguration. Die **Einstellungen zum Debuggen und starten** öffnen die Datei " *Launch. vs. JSON* " und fügen eine neue Debugkonfiguration für das ausgewählte Ziel hinzu.

## <a name="customize-debugger-settings"></a>Anpassen von Debuggereinstellungen

Sie können die Debuggereinstellungen für ein beliebiges ausführbares cmake-Ziel in Ihrem Projekt in einer Datei namens " *Launch. vs. JSON*" anpassen. Es gibt drei Einstiegspunkte für diese Datei:

- Wählen Sie **Debuggen > debug-und Start Einstellungen für $ {activedebugtarget}** aus dem Hauptmenü aus, um die für das aktive Debugziel spezifische Debugkonfiguration zu bearbeiten. Wenn Sie kein aktives Ziel ausgewählt haben, wird diese Option ausgegraut angezeigt.

- Navigieren Sie in Projektmappen-Explorer zur **Ansicht Ziele** . Klicken Sie dann mit der rechten Maustaste auf ein Debugziel, und wählen Sie **Debug-und Start Einstellungen** , um die für das ausgewählte Ziel spezifische Debugkonfiguration zu bearbeiten.

- Klicken Sie mit der rechten Maustaste auf das Stammverzeichnis CMakeLists. txt, und wählen Sie **Debuggen und Start Einstellungen** aus, um das Dialogfeld **Debugger auswählen** zu öffnen. Im Dialogfeld können Sie eine beliebige Debugkonfiguration hinzufügen. Sie müssen jedoch das cmake-Ziel, das über die `projectTarget`-Eigenschaft aufgerufen werden soll, manuell angeben.

Um einen Verweis auf einen beliebigen Schlüssel in einer *cmakesettings. JSON* -Datei zu erhalten, weisen Sie ihm `cmake.` in " *Launch. vs. JSON*" zu. Das folgende Beispiel zeigt eine einfache Datei " *Launch. vs. JSON* ", die den Wert des `remoteCopySources` Schlüssels in der Datei " *cmakesettings. JSON* " für die aktuell ausgewählte Konfiguration abruft:

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "project": "CMakeLists.txt",
      "projectTarget": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "name": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "args": ["${cmake.remoteCopySources}"]
    }
  ]
}
```

Wenn Sie die Datei " *Launch. vs. JSON* " speichern, erstellt Visual Studio in der Dropdown Liste **Start Element** einen Eintrag für den neuen Namen. Sie können die Datei " *Launch. vs. JSON* " Bearbeiten, um mehrere Debugkonfigurationen für beliebig viele cmake-Ziele zu erstellen.

## <a name="launchvsjson-reference"></a>Verweis auf "Launch. vs. JSON"

Es gibt viele " *Launch. vs. JSON* "-Eigenschaften, die alle debuggingszenarien unterstützen. Die folgenden Eigenschaften gelten für alle Debugkonfigurationen, sowohl Remote als auch lokal:

- `projectTarget`: gibt das cmake-Ziel an, das beim Erstellen des Projekts aufgerufen werden soll. Visual Studio führt eine autopopulation dieser Eigenschaft aus, wenn Sie " *Launch. vs. JSON* " aus der **debug-> die Debug-und Start Einstellungen für "$ {activedebugtarget}** " oder " **Targets**"

- `program`: vollständiger Pfad zur ausführbaren Programmdatei auf dem Remote System. Sie können das Makro `${debugInfo.fullTargetPath}` hier verwenden.

- `args`: Befehlszeilenargumente, die an das zu debuggende Programm übermittelt werden.

## <a name="launchvsjson-reference-for-remote-linux-projects"></a>Launch. vs. JSON-Referenz für Linux-Remote Projekte

Die folgenden Eigenschaften sind spezifisch für **remotedebugkonfigurationen**. Sie können [Befehle auch direkt an gdb senden und die](https://github.com/microsoft/MIEngine/wiki/Executing-custom-gdb-lldb-commands) [miengine-Protokollierung aktivieren](https://github.com/microsoft/MIEngine/wiki/Logging). Mithilfe dieser Eigenschaften können Sie sehen, welche Befehle an gdb gesendet werden, welche Ausgabe-gdb zurückgibt und wie lange die einzelnen Befehle dauern.

- `cwd`: Aktuelles Arbeitsverzeichnis zum Suchen nach Abhängigkeiten und anderen Dateien auf dem Remote Computer. Das Makro `${debugInfo.defaultWorkingDirectory}` kann verwendet werden. Der Standardwert ist der Stamm arbeitsbereichroot, es sei denn, er wurde in *CMakeLists. txt*überschrieben. Diese Eigenschaft wird nur für Remote Konfigurationen verwendet. `currentDir` wird zum Festlegen des aktuellen Verzeichnisses der Start-App für ein lokales Projekt verwendet.

- `environment`: zusätzliche Umgebungsvariablen, die der Umgebung für das Programm mit der folgenden Syntax hinzugefügt werden sollen:

```json
  "environment": [
      {
        "name": "ENV1",
        "value": "envvalue1"
      },
      {
        "name": "ENV2",
        "value": "envvalue2"
      }
    ]
```

- `pipeArgs`: Befehlszeilenargumente, die an das pipeprogramm übergeben werden, um die Verbindung zu konfigurieren. Das Pipe-Programm wird verwendet, um Standard Eingaben/-Ausgaben zwischen Visual Studio und gdb zu übertragen. Der Befehl `${debuggerCommand}` starten von gdb auf dem Remote System und kann wie folgt geändert werden:

  - Exportieren Sie den Wert der Umgebungsvariablen Anzeige auf Ihrem Linux-System. Im folgenden Beispiel ist dieser Wert `:1`.

  ```json
  "pipeArgs": [
      "/s",
      "${debugInfo.remoteMachineId}",
      "/p",
      "${debugInfo.parentProcessId}",
      "/c",
      "export DISPLAY=:1;${debuggerCommand}",
      "--tty=${debugInfo.tty}"
    ],
  ```

  - Führen Sie vor der Ausführung von gdb ein Skript aus. Stellen Sie sicher, dass Ausführungs Berechtigungen für Ihr Skript festgelegt sind.

    ```json
    "pipeArgs": [
        "/s",
        "${debugInfo.remoteMachineId}",
        "/p",
        "${debugInfo.parentProcessId}",
        "/c",
        "/path/to/script.sh;${debuggerCommand}",
        "--tty=${debugInfo.tty}"
      ],
    ```

- `stopOnEntry`: ein boolescher Wert, der angibt, ob die Unterbrechung erfolgt, sobald der Prozess gestartet wird. Der Standardwert ist false.

- `visualizerFile`: eine [natvis-Datei](/visualstudio/debugger/create-custom-views-of-native-objects) , die beim Debuggen dieses Prozesses verwendet werden soll. Diese Option ist nicht kompatibel mit dem gdb-ganz Druckvorgang. Legen Sie auch `showDisplayString` fest, wenn Sie diese Eigenschaft festlegen.

- `showDisplayString`: ein boolescher Wert, der die Anzeige Zeichenfolge aktiviert, wenn ein `visualizerFile` angegeben wird. Wenn diese Option auf `true` festgelegt wird, kann die Leistung beim Debuggen verlangsamt werden

- `setupCommands`: ein oder mehrere gdb-Befehle, die ausgeführt werden sollen, um den zugrunde liegenden Debugger einzurichten.

- `externalConsole`: ein boolescher Wert, der angibt, ob eine Konsole für die zu debuggende Komponente gestartet wird.

- `miDebuggerPath`: der vollständige Pfad zu "gdb". Wenn nicht angegeben, sucht Visual Studio den Pfad zuerst nach dem Debugger.

::: moniker-end

::: moniker range="vs-2017"

- `remoteMachineName`: das Linux-Remote System, das gdb hostet, und das zu debuggende Programm.

::: moniker-end

::: moniker range="vs-2019"

Die folgenden Eigenschaften können zum Trennen des remotebuildsystems von Ihrem **remotedebugsystem**verwendet werden. Weitere Informationen finden Sie [unter Angeben von verschiedenen Computern zum entwickeln und Debuggen](../linux/deploy-run-and-debug-your-linux-project.md#cmake-projects).

- `remoteMachineName`: das Linux-Remote System, das gdb hostet, und das zu debuggende Programm. Dieser Eintrag muss nicht mit dem Linux-Remote System, das für den in " *cmakesettings. JSON*" angegebenen Build verwendet wird, identisch sein. Drücken Sie **STRG + LEERTASTE** , um eine Liste aller im [Verbindungs-Manager](../linux/connect-to-your-remote-linux-computer.md)gespeicherten Remote Verbindungen anzuzeigen.

- `disableDeploy`: gibt an, ob die Build-/debugtrennung deaktiviert ist. Wenn diese Funktion aktiviert ist, können Builds und Debuggen auf zwei separaten Computern erfolgen.

- `deployDirectory`: das Verzeichnis auf dem Remote Debuggerät (angegeben durch `remoteMachineName`), in das die ausführbare Datei kopiert wird.

- `deploy`: ein Array mit erweiterten Bereitstellungs Einstellungen. Sie müssen diese Einstellungen nur konfigurieren, wenn Sie eine präzisetere Kontrolle über den Bereitstellungs Prozess wünschen. Standardmäßig werden nur die Dateien, die für den zu debuggenden Prozess erforderlich sind, auf dem Remotedebugcomputer bereitgestellt.

  - `sourceMachine`: der Computer, von dem die Datei oder das Verzeichnis kopiert wird. Drücken Sie **STRG + LEERTASTE** , um eine Liste aller im Verbindungs-Manager gespeicherten Remote Verbindungen anzuzeigen.

  - `targetMachine`: der Computer, auf den die Datei oder das Verzeichnis kopiert wird. Drücken Sie **STRG + LEERTASTE** , um eine Liste aller im Verbindungs-Manager gespeicherten Remote Verbindungen anzuzeigen.

  - `sourcePath`: der Datei-oder Verzeichnis Speicherort auf `sourceMachine`.

  - `targetPath`: der Datei-oder Verzeichnis Speicherort auf `targetMachine`.

  - `deploymentType`: eine Beschreibung des Bereitstellungs Typs. `LocalRemote` und `RemoteRemote` werden unterstützt. `LocalRemote` bedeutet, dass aus dem lokalen Dateisystem in das Remote System kopiert wird, das durch `remoteMachineName` in " *Launch. vs. JSON*" angegeben wird. `RemoteRemote` bedeutet, dass das in " *cmakesettings. JSON* " angegebene remotebuildsystem in das unter " *Launch. vs. JSON*" angegebene Remote System kopiert werden soll.

  - `executable`: gibt an, ob die bereitgestellte Datei eine ausführbare Datei ist.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="attach-to-a-remote-process"></a>An einen Remote Prozess anhängen

Sie können an einen Prozess anhängen, der auf Ihrem Linux-System ausgeführt wird, indem Sie `processId` auf die Prozess-ID festlegen, an die der Debugger angefügt wird Weitere Informationen finden Sie unter Behandeln von [Problemen beim Anhängen an Prozesse mithilfe von gdb](https://github.com/Microsoft/MIEngine/wiki/Troubleshoot-attaching-to-processes-using-GDB).

::: moniker-end

::: moniker range="vs-2019"

## <a name="debug-on-linux-using-gdbserver"></a>Debuggen unter Linux mit gdbserver

Visual Studio 2019 Version 16,5 Preview 1 oder höher unterstützt das Remote Debuggen von cmake-Projekten mit gdbserver. Weitere Informationen finden Sie unter [Debuggen von Linux cmake-Projekten mit gdbserver](https://devblogs.microsoft.com/cppblog/debugging-linux-cmake-projects-with-gdbserver/).

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="see-also"></a>Siehe auch

[Cmake-Projekte in Visual Studio](cmake-projects-in-visual-studio.md)\
[Konfigurieren eines Linux CMake-Projekts](../linux/cmake-linux-project.md)\
Stellen [Sie eine Verbindung mit Ihrem Linux-Remote Computer](../linux/connect-to-your-remote-linux-computer.md) her\
[Anpassen der cmake-Buildeinstellungen](customize-cmake-settings.md)\
[Konfigurieren von cmake-Debugsitzungen](configure-cmake-debugging-sessions.md)\
[Bereitstellen, Ausführen und Debuggen Ihres Linux-Projekts](../linux/deploy-run-and-debug-your-linux-project.md)\
[CMake predefined configuration reference (Referenz für vordefinierte CMake-Konfigurationen)](cmake-predefined-configuration-reference.md)

::: moniker-end
