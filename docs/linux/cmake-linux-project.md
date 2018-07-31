---
title: Konfigurieren eines Linux CMake-Projekts in Visual Studio | Microsoft Docs
description: Konfigurieren eines Linux CMake-Projekts in Visual Studio
ms.custom: ''
ms.date: 07/20/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 743f15cdb9fe8b0233f5b59ca399c0f47704d441
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269539"
---
# <a name="configure-a-linux-cmake-project"></a>Konfigurieren eines Linux CMake-Projekts

**Visual Studio 2017, Version 15.4 und höher**  
Wenn Sie unter Linux die C++-Workload für Visual Studio installieren, ist standardmäßig CMake-Unterstützung für Linux aktiviert. Sie können nun an Ihrer bestehenden Codebasis arbeiten, die CMake-verwendet, ohne sie in ein Visual Studio-Projekt konvertieren zu müssen. Wenn Ihre Codebasis plattformübergreifend ist, können Sie sowohl Windows als auch Linux in Visual Studio als Ziel verwenden.

Dieses Thema setzt voraus, dass Sie über grundlegende Kenntnisse der CMake-Unterstützung in Visual Studio verfügen. Weitere Informationen finden Sie unter [CMake-Tools für Visual C++](../ide/cmake-tools-for-visual-cpp.md). Weitere Informationen zu CMake selbst finden Sie unter [Erstellen, Testen und Paketerstellung Ihrer Software mit CMake](https://cmake.org/).

> [!NOTE]  
> Die CMake-Unterstützung in Visual Studio erfordert die Servermodusunterstützung, die in CMake 3.8 eingeführt wurde. Wenn Ihr Paket-Manager eine ältere Version von CMake bereitstellt, können Sie als Umgehung [CMake aus der Quelle erstellen](#build-a-supported-cmake release-from-source) oder CMake über die offizielle [Seite für den CMake-Download](https://cmake.org/download/) herunterladen. Laden Sie unter [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases) die aktuellsten vorab erstellten Binärdateien herunter, wenn Sie mit einer von Microsoft bereitgestellten CMake-Variante arbeiten möchten, die den Bereich [CMake-Zielansicht](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/cmake-support-in-visual-studio-targets-view-single-file-compilation-and-cache-generation-settings/) in Visual Studio unterstützt.

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

**Visual Studio 2017, Version 15.7 und höher**:  
Um IntelliSense-Unterstützung für Remoteheader bereitzustellen, kopiert Visual Studio diese automatisch in ein Verzeichnis auf dem lokalen Windows-Computer. Weitere Informationen finden Sie unter [IntelliSense für Remoteheader (Visual Studio 2017-Version 15.7 und höher)](configure-a-linux-project.md#remote_intellisense).

## <a name="debug-the-project"></a>Debuggen des Projekts

Um Ihren Code auf dem Remotesystem zu debuggen, legen Sie einen Haltepunkt fest, wählen Sie das CMake-Ziel als Startelement im Symbolleistenmenü neben der Projekteinstellung aus, und wählen Sie auf der Symbolleiste **&#x23f5; Starten** aus (oder drücken Sie F5).

Wenn Sie die Befehlszeilenargumente Ihres Programms anpassen möchten, klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die ausführbare Datei, und wählen Sie **Debug- und Starteinstellungen** aus. Hierdurch wird eine Konfigurationsdatei „launch.vs.json“ geöffnet oder erstellt, die Informationen zu Ihrem Programm enthält. Um zusätzliche Argumente anzugeben, fügen Sie sie dem JSON-Array `args` hinzu. Weitere Informationen finden Sie unter [Ordner öffnen-Projekte in Visual C++](https://docs.microsoft.com/en-us/cpp/ide/non-msbuild-projects).

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
      "remoteBuildRoot": "/var/tmp/build/${workspaceHash}/build/${name}",
      "remoteCopySources": true,
      "remoteCopySourcesOutputVerbosity": "Normal",
      "remoteCopySourcesConcurrentCopies": "10",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "",
      "ctestCommandArgs": "",
      "inheritEnvironments": [ "linux-x64" ]
}
```

Der Wert `name` kann beliebig sein. Der Wert `remoteMachineName` gibt an, welches Remotesystem als Ziel verwendet werden soll, wenn mehrere Remotesysteme vorhanden sind. IntelliSense ist für dieses Feld aktiviert, damit Sie das richtige System problemloser auswählen können. Das Feld `remoteCMakeListsRoot` gibt an, wohin Ihre Projektquellen auf dem Remotesystem kopiert werden. Das Feld `remoteBuildRoot` ist der Speicherort, an dem die Buildausgabe auf Ihrem Remotesystem generiert wird. Diese Ausgabe wird auch lokal an den Speicherort kopiert, der durch `buildRoot` angegebenen wird.

## <a name="build-a-supported-cmake-release-from-source"></a>Erstellen eines unterstützten CMake-Release aus der Quelle

Die Mindestversion von CMake, die auf Ihrem Linux-Computer erforderlich ist, ist 3.8. Außerdem muss der Servermodus unterstützt werden. Um dies zu bestätigen, führen Sie diesen Befehl aus:

```cmd
cmake --version
```

Um zu bestätigen, dass der Servermodus aktiviert ist, führen Sie Folgendes aus:

```cmd
cmake -E capabilities
```

Suchen Sie in der Ausgabe nach **"serverMode":true**. Beachten Sie, dass selbst wenn Sie CMake wie unten beschrieben aus dem Quellcode kompilieren, die Funktionen überprüft werden sollten, wenn Sie fertig sind. Ihr Linux-System weist möglicherweise Einschränkungen auf, die verhindern, dass der Servermodus aktiviert wird.

Um mit dem Erstellen von CMake aus der Quelle in der Shell für Ihr Linux-System zu beginnen, stellen Sie sicher, dass Ihr Paket-Manager auf dem neuesten Stand ist und dass Git und CMake verfügbar sind.

Klonen Sie zunächst die CMake-Quellen aus dem [Microsoft CMake-Repository](https://github.com/Microsoft/CMake), in dem wir einen Fork für die CMake-Unterstützung für Visual Studio verwalten:

```cmd
sudo apt-get update
sudo apt-get install -y git cmake
git clone https://github.com/Microsoft/CMake.git
cd CMake
```

Erstellen und installieren Sie im nächsten Schritt das aktuelle Release von CMake in „/usr/local/bin“, indem Sie diese Befehle ausführen:

```cmd
mkdir out
cd out
cmake ../
make
sudo make install
```

Führen Sie dann diesen Befehl aus, um zu bestätigen, dass die Version >= 3.8 und der Servermodus aktiviert ist:

```cmd
/usr/local/bin/cmake –version
cmake -E capabilities
```

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)  
[CMake-Tools für Visual C++](../ide/cmake-tools-for-visual-cpp.md)  
