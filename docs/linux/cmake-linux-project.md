---
title: Konfigurieren eines CMake-Projekts unter Linux in Visual Studio
description: Hier erfahren Sie, wie Sie ein Linux-CMake-Projekt in Visual Studio konfigurieren, bearbeiten und kompilieren.
ms.date: 05/21/2019
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: e2cda5e9b942342cca035c48054aadb5425b69cf
ms.sourcegitcommit: bde3279f70432f819018df74923a8bb895636f81
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2019
ms.locfileid: "66182890"
---
# <a name="configure-a-linux-cmake-project"></a>Konfigurieren eines Linux CMake-Projekts

Wenn Sie einen Ordner öffnen, der ein CMake-Projekt enthält, verwendet Visual Studio die Metadaten, die CMake generiert, um IntelliSense und Builds automatisch zu konfigurieren. Lokale Konfigurations- und Debugeinstellungen werden in JSON-Dateien gespeichert, die optional für andere Benutzer von Visual Studio freigegeben werden können. 

Visual Studio nimmt keine Änderungen an den „CMakeLists.txt“-Dateien oder dem ursprünglichen CMake-Cache vor, sodass andere, die am selben Projekt arbeiten, weiterhin dieselben Tools benutzen können.

Allgemeine Informationen über die Unterstützung von CMake in Visual Studio finden Sie unter [CMake-Projekte in Visual Studio](../build/cmake-projects-in-visual-studio.md). Diesen Artikel sollten Sie lesen, bevor Sie hier fortfahren.

## <a name="before-you-begin"></a>Vorbereitungen

Stellen Sie zuerst sicher, dass die Workload **Linux-Entwicklung mit C++** mit CMake-Komponente installiert ist. Weitere Informationen finden Sie unter [Install the C++ Linux workload in Visual Studio (Installieren der C++-Workload unter Linux in Visual Studio)](download-install-and-setup-the-linux-development-workload.md). 

Stellen Sie sicher, dass Folgendes auf dem Linux-Computer installiert ist: 

- gcc
- gdb
- rsync
- zip 

::: moniker range="vs-2019"

Für die Unterstützung von CMake-Projekten unter Linux ist eine aktuelle Version von CMake auf dem Zielcomputer erforderlich. Die vom Standardpaket-Manager einer Distribution bereitgestellte Version ist häufig nicht ausreichend aktuell, um alle Features der IDE zu unterstützen. Visual Studio 2019 kann automatisch eine lokale Kopie von CMake für Benutzer auf Linux-Remotecomputern installieren, auf denen keine aktuelle Version von CMake installiert ist. Wenn keine kompatible Version von CMake beim ersten Erstellen Ihres Projekts erkannt wird, wird eine Informationsleiste angezeigt, die die automatische Installation von CMake anbietet.

Die Binärdateien werden in `~/.vs/cmake` installiert. Nach dem Bereitstellen der Binärdateien wird Ihr Projekt automatisch neu generiert. Hinweis: Wenn die im Feld `cmakeExecutable` in `CMakeSettings.json` angegebene CMake-Version ungültig ist (Version nicht vorhanden oder ungültig) und die vorab erstellten Binärdateien vorhanden sind, ignoriert Visual Studio `cmakeExecutable` und verwendet die vorab erstellten Binärdateien.

::: moniker-end

::: moniker range="vs-2017"

Die CMake-Unterstützung in Visual Studio erfordert die Servermodusunterstützung, die in CMake 3.8 eingeführt wurde. Laden Sie für eine von Microsoft bereitgestellte CMake-Variante unter [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases) die aktuellsten vordefinierten Binärdateien herunter.

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

Sobald Sie den Ordner öffnen, analysiert Visual Studio die Datei „CMakeLists.txt“ und gibt das Windows-Ziel **x86-Debug** an. Um Linux als Zielen zu verwenden, ändern Sie die Projekteinstellungen in **Linux-Debug** oder **Linux-Release**.

Standardmäßig wählt Visual Studio das erste Remotesystem in der Liste aus (unter **Extras** > **Optionen** > **Plattformübergreifend** > **Verbindungs-Manager**). Wenn keine Remoteverbindungen gefunden werden, werden Sie aufgefordert, eine Remoteverbindung zu erstellen. Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit Ihrem Linux-Remotecomputer](connect-to-your-remote-linux-computer.md).

Nachdem Sie ein Linux-Ziel angegeben haben, wird Ihre Quelle auf den Linux-Computer kopiert. Dann wird CMake auf dem Linux-Computer ausgeführt, um den CMake-Cache für das Projekt zu generieren.

![Generieren des CMake-Caches unter Linux](media/cmake-linux-1.png "Generieren des CMake-Caches unter Linux")

Um IntelliSense-Unterstützung für Remoteheader bereitzustellen, kopiert Visual Studio diese automatisch vom Linux-Computer in ein Verzeichnis auf dem lokalen Windows-Computer. Weitere Informationen finden Sie unter [IntelliSense für Remoteheader (Visual Studio 2017-Version 15.7 und höher)](configure-a-linux-project.md#remote_intellisense).

## <a name="debug-the-project"></a>Debuggen des Projekts

Um Ihren Code auf dem Remotesystem zu debuggen, legen Sie einen Haltepunkt fest, wählen Sie das CMake-Ziel als Startelement im Symbolleistenmenü neben der Projekteinstellung aus, und wählen Sie auf der Symbolleiste **&#x23f5; Starten** aus (oder drücken Sie F5).

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

Mithilfe dieser Optionen können Sie Befehle vor und nach dem Erstellen und vor der CMake-Generierung auf dem Remotesystem ausführen. Die Werte können ein beliebiger Befehl sein, der auf dem Remotesystem gültig ist. Die Ausgabe wird wieder zurück an Visual Studio geleitet.

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
