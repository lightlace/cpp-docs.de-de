---
title: Konfigurieren eines Linux CMake-Projekts in Visual Studio | Microsoft Docs
ms.custom: 
ms.date: 10/25/2107
ms.reviewer: 
ms.suite: 
ms.technology: cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4e3baa9b6e362f93e7b2cda59d34cabf87324292
ms.sourcegitcommit: 1b480aa74886930b3bd0435d71cfcc3ccda36424
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="configure-a-linux-cmake-project"></a>Konfigurieren eines Linux CMake-Projekts
  
**Visual Studio 2017 Version 15.4** Wenn Sie die Linux C++-Workload installieren, ist standardmäßig CMake-Unterstützung für Linux ausgewählt. Sie können nun an Ihrer bestehenden Codebasis arbeiten, die CMake-verwendet, ohne sie in ein Visual Studio-Projekt konvertieren zu müssen. Wenn Ihre Codebasis plattformübergreifend ist, können Sie sowohl Windows als auch Linux in Visual Studio als Ziel verwenden. 

Dieses Thema setzt voraus, dass Sie über grundlegende Kenntnisse der CMake-Unterstützung in Visual Studio verfügen. Weitere Informationen finden Sie unter [CMake-Tools für Visual C++](../ide/cmake-tools-for-visual-cpp.md). Weitere Informationen zu CMake selbst finden Sie unter [Erstellen, Testen und Paketerstellung Ihrer Software mit CMake](https://cmake.org/).

> [!NOTE] 
> Die CMake-Unterstützung in Visual Studio erfordert die Servermodusunterstützung, die in CMake 3.8 eingeführt wurde. Wenn Ihr Paket-Manager eine ältere Version von CMake bereitstellt, können Sie diese umgehen, indem Sie CMake 3.8 aus der Quelle erstellen.



## <a name="open-a-folder"></a>Öffnen eines Ordners
Um zu beginnen, wählen Sie **Datei > Öffnen > Ordner** aus dem Hauptmenü aus, oder geben Sie `devenv.exe <foldername>` in der Befehlszeile ein. Der Ordner, den Sie öffnen, sollte eine Datei „CMakeLists.txt“ sowie Ihren Quellcode enthalten.
Das folgende Beispiel zeigt eine einfache Datei „CMakeLists.txt“ und CPP-Datei:

```cpp
// Hello.cpp

#include <iostream>;
 
int main(int argc, char* argv[])
{
    std::cout << "Hello" << std::endl;
}
```

„CMakeLists.txt“: 
```cmd
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="choose-a-linux-target"></a>Auswählen eines Linux-Ziels
Sobald Sie den Ordner öffnen, analysiert Visual Studio die Datei „CMakeLists.txt“ und gibt das Windows-Ziel „x86-Debug“ an. Um Linux als Zielen zu verwenden, ändern Sie die Projekteinstellungen in Linux-Debug oder Linux-Release.

Standardmäßig wählt Visual Studio das erste Remotesystem in der Liste aus (unter **Extras > Optionen > Plattformübergreifend > Verbindungs-Manager**). Wenn keine Remoteverbindungen gefunden werden, werden Sie aufgefordert, eine Remoteverbindung zu erstellen.

Nachdem Sie ein Linux-Ziel angegeben haben, wird Ihre Quelle auf den Linux-Computer kopiert. Dann wird CMake auf dem Linux-Computer ausgeführt, um den CMake-Cache für das Projekt zu generieren.  

![Generieren des CMake-Caches unter Linux](media/cmake-linux-1.png "Generieren des CMake-Caches unter Linux")  

## <a name="debug-the-project"></a>Debuggen des Projekts  
Um Ihren Code auf dem Remotesystem zu debuggen, legen Sie einen Haltepunkt fest, wählen Sie das CMake-Ziel als Startelement im Symbolleistenmenü neben der Projekteinstellung aus, und klicken Sie auf „Ausführen“ (oder drücken Sie F5).

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

## <a name="building-a-supported-cmake-release-from-source"></a>Erstellen eines unterstützten CMake-Release aus der Quelle
Die Mindestversion von CMake, die auf Ihrem Linux-Computer erforderlich ist, ist 3.8. Außerdem muss der Servermodus unterstützt werden. Um dies zu bestätigen, führen Sie diesen Befehl aus:

```cmd
cmake --version
```

Um zu bestätigen, dass der Servermodus aktiviert ist, führen Sie Folgendes aus:

```cmd
cmake -E capabilities
```

Suchen Sie in der Ausgabe nach "serverMode":true. Beachten Sie, dass selbst wenn Sie CMake wie unten beschrieben aus dem Quellcode kompilieren, die Funktionen überprüft werden sollten, wenn Sie fertig sind. Ihr Linux-System weist möglicherweise Einschränkungen auf, die verhindern, dass der Servermodus aktiviert wird.

Um mit dem Erstellen aus der Quelle in der Shell für Ihr Linux-System zu beginnen, stellen Sie sicher, dass Ihr Paket-Manager auf dem neuesten Stand ist und dass Git und Cmake verfügbar sind. Klonen Sie zunächst die CMake Quellen:

```cmd
sudo apt-get update
sudo apt-get install -y git cmake
git clone https://github.com/Kitware/CMake.git
cd CMake
```

Stellen Sie im nächsten Schritt sicher, dass Sie unter einem unterstützten Release von CMake für Visual Studio arbeiten. Wir verfolgen die Entwicklung von CMake aktiv nach, können aber nicht garantieren, dass wir das neueste Release unterstützen. Um z.B. CMake 3.9.0 zu erstellen, führen Sie zunächst Folgendes aus:

```cmd
git checkout tags/v3.9.0
```

Führen Sie dann die folgenden Befehle aus:

```cmd
mkdir out
cd out
cmake ../
make
sudo make install
```

Die oben aufgeführten Befehle erstellen und installieren das aktuelle Release von CMake in „/usr/local/bin“. Führen Sie diesen Befehl aus, um zu bestätigen, dass die Version >= 3.8 und der Servermodus aktiviert ist:

```cmd
/usr/local/bin/cmake –version
cmake -E capabilities
```

## <a name="see-also"></a>Siehe auch
[Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)  
[CMake-Tools für Visual C++](../ide/cmake-tools-for-visual-cpp.md)