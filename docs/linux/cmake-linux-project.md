---
title: Konfigurieren eines CMake-Projekts unter Linux in Visual Studio
description: Konfigurieren eines Linux CMake-Projekts in Visual Studio
ms.date: 07/20/2018
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: 28902f0a2938fe653eb4dfbb6e512367b1052b8c
ms.sourcegitcommit: fe1e21df175cd004d21c6e4659082efceb649a8b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53978321"
---
# <a name="configure-a-linux-cmake-project"></a>Konfigurieren eines Linux CMake-Projekts

**Visual Studio 2017, Version 15.4 und höher**<br/>
Wenn Sie unter Linux die C++-Workload für Visual Studio installieren, ist standardmäßig CMake-Unterstützung für Linux aktiviert. Sie können nun an Ihrer bestehenden Codebasis arbeiten, die CMake-verwendet, ohne sie in ein Visual Studio-Projekt konvertieren zu müssen. Wenn Ihre Codebasis plattformübergreifend ist, können Sie sowohl Windows als auch Linux in Visual Studio als Ziel verwenden.

Dieses Thema setzt voraus, dass Sie über grundlegende Kenntnisse der CMake-Unterstützung in Visual Studio verfügen. Weitere Informationen finden Sie unter [CMake-Tools für Visual C++](../ide/cmake-tools-for-visual-cpp.md). Weitere Informationen zu CMake selbst finden Sie unter [Erstellen, Testen und Paketerstellung Ihrer Software mit CMake](https://cmake.org/).

> [!NOTE]
> Die CMake-Unterstützung in Visual Studio erfordert die Servermodusunterstützung, die in CMake 3.8 eingeführt wurde. Für eine von Microsoft bereitgestellte Variante von CMake laden Sie unter [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases) die aktuellsten vorab erstellten Binärdateien herunter. In Visual Studio 2019 können vorab erstellte Binärdateien automatisch bereitgestellt werden (siehe [Herunterladen von vorab erstellten CMake-Binärdateien](#download-prebuilt-cmake-binaries)).

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

Sobald Sie den Ordner öffnen, analysiert Visual Studio die Datei „CMakeLists.txt“ und gibt das Windows-Ziel **x86-Debug** an. Um Linux als Zielen zu verwenden, ändern Sie die Projekteinstellungen in **Linux-Debug** oder **Linux-Release**.

Standardmäßig wählt Visual Studio das erste Remotesystem in der Liste aus (unter **Extras** > **Optionen** > **Plattformübergreifend** > **Verbindungs-Manager**). Wenn keine Remoteverbindungen gefunden werden, werden Sie aufgefordert, eine Remoteverbindung zu erstellen.

Nachdem Sie ein Linux-Ziel angegeben haben, wird Ihre Quelle auf den Linux-Computer kopiert. Dann wird CMake auf dem Linux-Computer ausgeführt, um den CMake-Cache für das Projekt zu generieren.

![Generieren des CMake-Caches unter Linux](media/cmake-linux-1.png "Generieren des CMake-Caches unter Linux")

**Visual Studio 2017, Version 15.7 und höher**:<br/>
Um IntelliSense-Unterstützung für Remoteheader bereitzustellen, kopiert Visual Studio diese automatisch in ein Verzeichnis auf dem lokalen Windows-Computer. Weitere Informationen finden Sie unter [IntelliSense für Remoteheader (Visual Studio 2017-Version 15.7 und höher)](configure-a-linux-project.md#remote_intellisense).

## <a name="debug-the-project"></a>Debuggen des Projekts

Um Ihren Code auf dem Remotesystem zu debuggen, legen Sie einen Haltepunkt fest, wählen Sie das CMake-Ziel als Startelement im Symbolleistenmenü neben der Projekteinstellung aus, und wählen Sie auf der Symbolleiste **&#x23f5; Starten** aus (oder drücken Sie F5).

Wenn Sie die Befehlszeilenargumente Ihres Programms anpassen möchten, klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die ausführbare Datei, und wählen Sie **Debug- und Starteinstellungen** aus. Hierdurch wird eine Konfigurationsdatei „launch.vs.json“ geöffnet oder erstellt, die Informationen zu Ihrem Programm enthält. Um zusätzliche Argumente anzugeben, fügen Sie sie dem JSON-Array `args` hinzu. Weitere Informationen finden Sie unter [Ordner öffnen-Projekte in Visual C++](../ide/non-msbuild-projects.md).

## <a name="configure-cmake-settings-for-linux"></a>Konfigurieren von CMake-Einstellungen für Linux

Um die CMake-Standardeinstellungen zu ändern, wählen Sie **CMake > CMake-Einstellungen ändern > CMakeLists.txt** im Hauptmenü aus, oder klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf „CMakeSettings.txt“, und wählen Sie dann **CMake-Einstellungen ändern** aus. Visual Studio erstellt dann eine neue Datei in Ihrem Ordner namens `CMakeSettings.json`, die mit den Standardkonfigurationen aufgefüllt wird, die im Menüelement „Projekteinstellungen“ aufgelistet werden. Das folgende Beispiel zeigt die Standardkonfiguration für Linux-Debug basierend auf dem vorherigen Codebeispiel:

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

Der Wert `name` kann beliebig sein. Der Wert `remoteMachineName` gibt an, welches Remotesystem als Ziel verwendet werden soll, wenn mehrere Remotesysteme vorhanden sind. IntelliSense ist für dieses Feld aktiviert, damit Sie das richtige System problemloser auswählen können. Das Feld `remoteCMakeListsRoot` gibt an, wohin Ihre Projektquellen auf dem Remotesystem kopiert werden. Das Feld `remoteBuildRoot` ist der Speicherort, an dem die Buildausgabe auf Ihrem Remotesystem generiert wird. Diese Ausgabe wird auch lokal an den Speicherort kopiert, der durch `buildRoot` angegebenen wird. Die Felder `remoteInstallRoot` und `installRoot` ähneln den Feldern `remoteBuildRoot` und `buildRoot`, es sei denn diese gelten bei einer CMake-Installation. Der Eintrag `remoteCopySources` steuert, ob Ihre lokalen Quellen in den Remotecomputer kopiert werden oder nicht. Sie können dies auf „false“ festlegen, wenn Sie sehr viele Dateien haben und die Quellen selbst synchronisieren. Der Wert `remoteCopyOutputVerbosity` steuert die Ausführlichkeit des Kopiervorgangs, falls Sie Fehler diagnostizieren müssen. Der Eintrag `remoteCopySourcesConcurrentCopies` steuert, wie viele Prozesse erzeugt werden, um die Kopie auszuführen. Der Wert `remoteCopySourcesMethod` kann entweder von rsync oder von SFTP sein. Das Feld `remoteCopySourcesExclusionList` ermöglicht es Ihnen, zu steuern, was in den Remotecomputer kopiert wird. Der Wert `rsyncCommandArgs` ermöglicht es Ihnen, den rsync-Kopiervorgang zu steuern. Die Feld `remoteCopyBuildOutput` steuert, ob die Remotebuildausgabe in Ihren lokalen Buildordner kopiert wird oder nicht.

Es gibt auch optionale Einstellungen, die Sie für mehr Kontrolle verwenden können:

```json
{
      "remotePreBuildCommand": "",
      "remotePreGenerateCommand": "",
      "remotePostBuildCommand": "",
}
```

Mithilfe dieser Optionen können Sie Befehle vor und nach dem Erstellen und vor der CMake-Generierung auf dem Remotecomputer ausführen. Diese können alle gültigen Befehle auf dem Remotecomputer sein. Die Ausgabe wird wieder zurück an Visual Studio geleitet.

## <a name="download-prebuilt-cmake-binaries"></a>Herunterladen vorab erstellter Binärdateien für CMake

Ihre Linux-Distribution enthält möglicherweise eine ältere Version von CMake. Die CMake-Unterstützung in Visual Studio erfordert die Servermodusunterstützung, die in CMake 3.8 eingeführt wurde. Für eine von Microsoft bereitgestellte Variante von CMake laden Sie unter [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases) die aktuellsten vorab erstellten Binärdateien herunter.

**Visual Studio 2019**<br/>
Wenn keine gültige CMake-Version auf dem Remotecomputer gefunden wurde, wird eine Infoleiste mit der Option zum automatischen Erstellen der vorab erstellten CMake-Binärdateien angezeigt. Die Binärdateien werden in `~/.vs/cmake` installiert. Nach dem Bereitstellen der Binärdateien wird Ihr Projekt automatisch neu generiert. Hinweis: Wenn die im Feld `cmakeExecutable` in `CMakeSettings.json` angegebene CMake-Version ungültig ist (Version nicht vorhanden oder ungültig) und die vorab erstellten Binärdateien vorhanden sind, ignoriert Visual Studio `cmakeExecutable` und verwendet die vorab erstellten Binärdateien.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)<br/>
[CMake-Tools für Visual C++](../ide/cmake-tools-for-visual-cpp.md)
