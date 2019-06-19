---
title: Konfigurieren eines CMake-Projekts unter Linux in Visual Studio
description: Hier erfahren Sie, wie Sie ein Linux-CMake-Projekt in Visual Studio konfigurieren, bearbeiten und kompilieren.
ms.date: 06/07/2019
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: e0a4abb7fe62880af12277d5c5c474d6ec4e0202
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821672"
---
# <a name="configure-a-linux-cmake-project"></a>Konfigurieren eines Linux CMake-Projekts

::: moniker range="vs-2015"

Die Unterstützung für Linux ist in Visual Studio 2017 und höher verfügbar.

::: moniker-end

Wenn Sie einen Ordner öffnen, der ein CMake-Projekt enthält, verwendet Visual Studio die Metadaten, die CMake generiert, um IntelliSense und Builds automatisch zu konfigurieren. Lokale Konfigurations- und Debugeinstellungen werden in JSON-Dateien gespeichert, die optional für andere Benutzer von Visual Studio freigegeben werden können. 

Visual Studio nimmt keine Änderungen an den „CMakeLists.txt“-Dateien oder dem ursprünglichen CMake-Cache vor, sodass andere, die am selben Projekt arbeiten, weiterhin dieselben Tools benutzen können.

Allgemeine Informationen über die Unterstützung von CMake in Visual Studio finden Sie unter [CMake-Projekte in Visual Studio](../build/cmake-projects-in-visual-studio.md). Diesen Artikel sollten Sie lesen, bevor Sie hier fortfahren.

## <a name="before-you-begin"></a>Vorbereitungen

Stellen Sie zuerst sicher, dass die Workload **Linux-Entwicklung mit C++** mit CMake-Komponente installiert ist. Weitere Informationen finden Sie unter [Install the C++ Linux workload in Visual Studio (Installieren der C++-Workload unter Linux in Visual Studio)](download-install-and-setup-the-linux-development-workload.md). 

Stellen Sie sicher, dass Folgendes auf dem Linux-System installiert ist: 

- gcc
- gdb
- rsync
- zip 

::: moniker range="vs-2019"

Für die Unterstützung von CMake-Projekten unter Linux ist eine aktuelle Version von CMake auf dem Zielcomputer erforderlich. Die vom Standardpaket-Manager einer Distribution bereitgestellte Version ist häufig nicht ausreichend aktuell, um alle für Visual Studio erforderlichen Funktionen zu unterstützen. Visual Studio 2019 erkennt, ob eine aktuelle Version von CMake auf dem Linux-System installiert ist. Wenn keine aktuelle Version gefunden wird, zeigt Visual Studio im oberen Editor-Bereich eine Informationsleiste an und schlägt Ihnen vor, diese zu installieren.

::: moniker-end

::: moniker range="vs-2017"

Die CMake-Unterstützung in Visual Studio erfordert die Servermodusunterstützung, die in CMake 3.8 eingeführt wurde. Laden Sie für eine von Microsoft bereitgestellte CMake-Variante unter [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases) die aktuellsten vordefinierten Binärdateien herunter.

Die Binärdateien werden in `~/.vs/cmake` installiert. Nach dem Bereitstellen der Binärdateien wird Ihr Projekt automatisch neu generiert. Hinweis: Wenn die im Feld `cmakeExecutable` in `CMakeSettings.json` angegebene CMake-Version ungültig ist (Version nicht vorhanden oder ungültig) und die vorab erstellten Binärdateien vorhanden sind, ignoriert Visual Studio `cmakeExecutable` und verwendet die vorab erstellten Binärdateien.

:::moniker-end

## <a name="open-a-folder"></a>Öffnen eines Ordners

Um zu beginnen, wählen Sie **Datei** > **Öffnen** > **Ordner** aus dem Hauptmenü aus, oder geben Sie `devenv.exe <foldername>` in der Befehlszeile ein. Der Ordner, den Sie öffnen, sollte eine Datei „CMakeLists.txt“ sowie Ihren Quellcode enthalten.
Das folgende Beispiel zeigt eine einfache Datei „CMakeLists.txt“ und CPP-Datei:

```cpp
// hello.cpp

#include <iostream>

int main(int argc, char* argv[])
{
    std::cout << "Hello from Linux CMake" << std::endl;
}
```

„CMakeLists.txt“:

```cmd
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="choose-a-linux-target"></a>Auswählen eines Linux-Ziels

Sobald Sie den Ordner öffnen, analysiert Visual Studio die Datei „CMakeLists.txt“ und gibt das Windows-Ziel **x86-Debug** an. Ändern Sie die Projekteinstellungen auf **Linux-Debug** oder **Linux-Release**, um auf ein Linux-Remotesystem abzuzielen. 

::: moniker range="vs-2019"

Wählen Sie bei Verwendung von GCC **WSL-Debug** oder **WSL-Release** aus bzw. bei Verwendung der Clang-Varianten das Clang-/LLVM-Toolset, um auf das Windows-Subsystem für Linux abzuzielen. 

**Visual Studio 2019 Version 16.1** Wenn auf WSL abgezielt wird, ist das Kopieren von Quellen oder Headern nicht erforderlich, da der Compiler unter Linux Direktzugriff auf das Windows-Dateisystem hat, wo Ihre Quelldateien gespeichert sind. Visual Studio kann ebenso direkt auf die Linux-Headerdateien zugreifen.

::: moniker-end

Für Remoteziele wählt Visual Studio standardmäßig das erste Remotesystem in der Liste unter **Tools** > **Optionen** > **Plattformübergreifend** > **Verbindungs-Manager** aus. Wenn keine Remoteverbindungen gefunden werden, werden Sie aufgefordert, eine Remoteverbindung zu erstellen. Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit Ihrem Linux-Remotecomputer](connect-to-your-remote-linux-computer.md).

Wenn Sie ein Linux-Remoteziel angeben, wird Ihre Quelle in das Remotesystem kopiert.

Wenn Sie ein Ziel ausgewählt haben, wird CMake zum Generieren des CMake-Caches für Ihr Projekt automatisch auf dem Linux-System ausgeführt. 

![Generieren des CMake-Caches unter Linux](media/cmake-linux-1.png "Generieren des CMake-Caches unter Linux")

Visual Studio kopiert automatisch Header vom Linux-Computer in ein Verzeichnis auf Ihrem lokalen Windows-Computer, um IntelliSense-Unterstützung für Header auf Linux-Remotesystemen bereitzustellen. Weitere Informationen finden Sie unter [IntelliSense für Remoteheader (Visual Studio 2017-Version 15.7 und höher)](configure-a-linux-project.md#remote_intellisense).

## <a name="debug-the-project"></a>Debuggen des Projekts

Legen Sie zum Debuggen Ihres Codes auf dem angegebenen Debugzielsystem einen Breakpoint fest, wählen Sie im Symbolleistenmenü neben der Projekteinstellung das CMake-Ziel als Startelement aus, und klicken Sie in der Symbolleiste auf **&#x23f5; Start** bzw. F5.

Wenn Sie die Befehlszeilenargumente Ihres Programms anpassen möchten, klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die ausführbare Datei, und wählen Sie **Debug- und Starteinstellungen** aus. Hierdurch wird eine Konfigurationsdatei „launch.vs.json“ geöffnet oder erstellt, die Informationen zu Ihrem Programm enthält. Um zusätzliche Argumente anzugeben, fügen Sie sie dem JSON-Array `args` hinzu. Weitere Informationen finden Sie unter [Open Folder projects for C++ (Verwenden von „Ordner öffnen“ mit Projekten in Visual C++)](../build/open-folder-projects-cpp.md) und [Configure CMake debugging sessions (Konfigurieren von CMake-Debugsitzungen)](../build/configure-cmake-debugging-sessions.md).

## <a name="configure-cmake-settings-for-linux"></a>Konfigurieren von CMake-Einstellungen für Linux

Eine „CMakeSettings.json“-Datei in einem CMake-Projekt unter Linux kann alle unter [Anpassen von CMake-Buildeinstellungen](../build/customize-cmake-settings.md) aufgeführten Einstellungen angeben sowie weitere Eigenschaften, die die Buildeinstellungen auf dem Linux-Remotecomputer steuern. 

::: moniker range="vs-2019"

Öffnen Sie die Dropdownliste **Konfiguration**, und wählen Sie die Option **Konfigurationen verwalten** aus, um die Standardeinstellungen von CMake in Visual Studio 2019 zu ändern. 

![CMake-Konfigurationen verwalten](../build/media/vs2019-cmake-manage-configurations.png "Dropdownliste für CMake-Konfigurationen")

Dadurch wird der **Editor für CMake-Einstellungen** geöffnet, den Sie zum Bearbeiten der `CMakeSettings.json`-Datei im Stammprojektordner verwenden können. Sie können die Datei auch direkt öffnen, indem Sie im Editor auf **JSON bearbeiten** klicken. Weitere Informationen finden Sie unter [Anpassen von CMake-Einstellungen](../build/customize-cmake-settings.md).

::: moniker-end

::: moniker range="vs-2017"

Klicken Sie im Hauptmenü auf **CMake > CMake-Einstellungen ändern > CMakeLists.txt**, oder klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei „CMakeSettings.txt“, und wählen Sie dann **CMake-Einstellungen ändern** aus, um die CMake-Standardeinstellungen in Visual Studio 2017 zu ändern. Visual Studio erstellt dann eine neue `CMakeSettings.json`-Datei im Stammordner des Projekts. Sie können die Datei mit dem Editor für **CMake-Einstellungen** öffnen oder die Datei direkt ändern. Weitere Informationen finden Sie unter [Customize CMake settings (Anpassen von CMake-Einstellungen)](../build/customize-cmake-settings.md).

::: moniker-end

Das folgende Beispiel zeigt die Standardkonfiguration für Linux-Debug basierend auf dem vorherigen Codebeispiel:

```json
{
      "name": "Linux-Debug",
      "generator": "Unix Makefiles",
      "remoteMachineName": "${defaultRemoteMachineName}",
      "configurationType": "Debug",
      "remoteCMakeListsRoot": "/var/tmp/src/${workspaceHash}/${name}",
      "cmakeExecutable": "/usr/local/bin/cmake",
      "buildRoot": "${env.LOCALAPPDATA}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.LOCALAPPDATA}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "remoteBuildRoot": "/var/tmp/build/${workspaceHash}/build/${name}",
      "remoteInstallRoot": "/var/tmp/build/${workspaceHash}/install/${name}",
      "remoteCopySources": true,
      "remoteCopySourcesOutputVerbosity": "Normal",
      "remoteCopySourcesConcurrentCopies": "10",
      "remoteCopySourcesMethod": "rsync",
      "remoteCopySourcesExclusionList": [".vs", ".git"],
      "rsyncCommandArgs" : "-t --delete --delete-excluded",
      "remoteCopyBuildOutput" : "false",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "",
      "ctestCommandArgs": "",
      "inheritEnvironments": [ "linux-x64" ]
}
```
Die folgende Tabelle fasst diese Einstellungen zusammen:

|Einstellung|Beschreibung|
|-----------|-----------------|
|`name`|Dieser Wert kann beliebig sein.|
|`remoteMachineName`|Gibt an, welches Remotesystem als Ziel verwendet werden soll, wenn mehrere Remotesysteme vorhanden sind. IntelliSense ist für dieses Feld aktiviert, damit Sie das richtige System problemloser auswählen können.|
|`remoteCMakeListsRoot`|Gibt an, wohin Ihre Projektquellen auf dem Remotesystem kopiert werden.|
|`remoteBuildRoot`|Gibt an, wo die Buildausgabe auf Ihrem Remotesystem generiert wird. Diese Ausgabe wird auch lokal an den Speicherort kopiert, der durch `buildRoot` angegebenen wird.|
|`remoteInstallRoot` und `installRoot`| Ähnlich wie `remoteBuildRoot` und `buildRoot`, außer dass diese bei einer CMake-Installation gelten.|
|`remoteCopySources`|Gibt an, ob Ihre lokalen Quellen auf den Remotecomputer kopiert werden oder nicht. Sie können dies auf FALSE festlegen, wenn Sie viele Dateien haben und die Quellen selbst synchronisieren.|
|`remoteCopyOutputVerbosity`| Gibt die Ausführlichkeit des Kopiervorgangs an, falls Sie Fehler diagnostizieren müssen.|
|`remoteCopySourcesConcurrentCopies`| Gibt an, wie viele Prozesse erzeugt werden, um die Kopie auszuführen.|
|`remoteCopySourcesMethod`| Kann entweder `rsync` oder `sftp` sein.|
|`remoteCopySourcesExclusionList`| Gibt Dateien an, die nicht auf den Remotecomputer kopiert werden sollen.|
|`rsyncCommandArgs`|Steuert die rsync-Methode zum Kopieren.|
|`remoteCopyBuildOutput`| Steuert, ob die Remotebuildausgabe in Ihren lokalen Buildordner kopiert wird oder nicht.|

Sie können diese optionalen Einstellungen für mehr Kontrolle verwenden:

```json
{
      "remotePrebuildCommand": "",
      "remotePreGenerateCommand": "",
      "remotePostbuildCommand": "",
}
```

Mithilfe dieser Optionen können Sie Befehle vor und nach dem Erstellen und vor der CMake-Generierung auf dem Linux-System ausführen. Die Werte können ein beliebiger Befehl sein, der auf dem Remotesystem gültig ist. Die Ausgabe wird wieder zurück an Visual Studio geleitet.

::: moniker range="vs-2019"

In Visual Studio 2019 können Sie all diese Einstellungen über den **Editor für CMake-Einstellungen** bearbeiten.

::: moniker-end

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Projekteigenschaften](../build/working-with-project-properties.md)<br/>
[CMake Projects in Visual Studio (CMake-Projekte in Visual Studio)](../build/cmake-projects-in-visual-studio.md)<br/>
[Herstellen einer Verbindung mit Ihrem Linux-Remotecomputer](connect-to-your-remote-linux-computer.md)<br/>
[Anpassen von CMake-Buildeinstellungen](../build/customize-cmake-settings.md)<br/>
[Konfigurieren von CMake-Debugsitzungen](../build/configure-cmake-debugging-sessions.md)<br/>
[Bereitstellen, Ausführen und Debuggen Ihres Linux-Projekts](deploy-run-and-debug-your-linux-project.md)<br/>
[CMake predefined configuration reference (Referenz für vordefinierte CMake-Konfigurationen)](../build/cmake-predefined-configuration-reference.md)<br/>
