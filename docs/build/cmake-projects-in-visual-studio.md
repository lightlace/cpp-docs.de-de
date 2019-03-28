---
title: CMake-Projekte in Visual Studio
ms.date: 03/27/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: 479179d94a0534f5f0c790fea18e281053b686e2
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565294"
---
# <a name="cmake-projects-in-visual-studio"></a>CMake-Projekte in Visual Studio

CMake ist ein plattformübergreifendes Open Source-Tool, das zum Definieren von Buildprozessen verwendet wird, die auf mehreren Plattformen ausgeführt werden. In diesem Artikel wird davon ausgegangen, dass Sie mit CMake vertraut sind. Weitere Informationen finden Sie unter [Build, Test and Package Your Software With CMake (Erstellen, Testen und Packen Ihrer Software mit CMake)](https://cmake.org/).

In Visual Studio 2015 können Visual Studio-Benutzer einen [CMake-Generator](https://cmake.org/cmake/help/latest/manual/cmake-generators.7.html) verwenden, um MSBuild-Projektdateien zu generieren, die anschließend von der IDE für IntelliSense sowie für das Durchsuchen und die Kompilierung verwendet werden.

In Visual Studio 2017 wird umfangreiche Unterstützung für CMake eingeführt, darunter [plattformübergreifende CMake-Projekte](../linux/cmake-linux-project.md). Die Komponente **Visual C++-Tools für CMake** verwendet die Funktion **Ordner öffnen**, um zu ermöglichen, dass die IDE CMake-Projektdateien (z.B. „CMakeLists.txt“) direkt für IntelliSense und das Durchsuchen nutzt. Es werden sowohl Ninja- als auch Visual Studio-Generatoren unterstützt. Wenn Sie einen Visual Studio-Generator verwenden, wird eine temporäre Projektdatei generiert und an „msbuild.exe“ übergeben. Diese wird jedoch nie für IntelliSense oder das Durchsuchen geladen. Sie können einen vorhandenen CMake-Cache importieren. Visual Studio automatisch die benutzerdefinierte Variablen extrahiert und erstellt eine vorab aufgefüllte **"cmakesettings.JSON"** Datei. 

## <a name="installation"></a>Installation

**Visual C++-Tools für CMake** wird standardmäßig als Teil der Workloads **Desktopentwicklung mit C++** und **Linux-Entwicklung mit C++** installiert.

![CMake-Komponente in der Workload „Desktopentwicklung mit C++“](media/cmake-install.png)

Weitere Informationen finden Sie unter [Install the C++ Linux workload in Visual Studio (Installieren der C++-Workload unter Linux in Visual Studio)](../linux/download-install-and-setup-the-linux-development-workload.md).

## <a name="ide-integration"></a>IDE-Integration

Wenn Sie auf **Datei > Öffnen > Ordner** klicken, um einen Ordner zu öffnen, der eine CMakeLists.txt-Datei enthält, geschieht Folgendes:

- Visual Studio fügt ein **CMake**-Menüelement zum Hauptmenü hinzu, das Befehle für das Anzeigen und Bearbeiten von CMake-Skripts enthält.

- Der **Projektmappen-Explorer** zeigt die Ordnerstruktur und die Dateien an.

- Visual Studio führt „CMake.exe“ aus und generiert optional den CMake-Cache für die *Standardkonfiguration* (x86 Debug). Die CMake-Befehlszeile wird im **Ausgabefenster** zusammen mit zusätzlichen Ausgaben von CMake angezeigt.

- Im Hintergrund beginnt Visual Studio damit, die Quelldateien zu indizieren, um IntelliSense, das Durchsuchen von Informationen, das Refactoring und vieles mehr zu ermöglichen. Während Sie arbeiten, überwacht Visual Studio die Änderungen im Editor und auf dem Datenträger, damit der Index mit den Quellen synchron ist.

Sie können Ordner öffnen, die eine beliebige Anzahl von CMake-Projekten enthalten. Visual Studio erkennt und konfiguriert alle CMakeLists.txt-Stammdateien in Ihrem Arbeitsbereich. CMake-Vorgänge (Konfigurieren, Erstellen, Debuggen) sowie C++ IntelliSense und das Durchsuchen sind für alle CMake-Projekte in Ihrem Arbeitsbereich verfügbar.

![CMake-Projekte mit mehreren Stammdateien](media/cmake-multiple-roots.png)

Sie können die Projekte auch logisch strukturiert nach Zielen anzeigen. Wählen Sie in der Dropdownliste der Symbolleiste des **Projektmappen-Explorers** die Option **Zielansicht** aus:

![Schaltfläche für CMake-Zielansicht](media/cmake-targets-view.png)

Visual Studio verwendet eine Datei namens **"cmakesettings.JSON"** , Umgebungsvariablen oder Befehlszeilenoptionen für Cmake.exe zu speichern. **"Cmakesettings.JSON"** können Sie definieren, und Speichern von mehreren CMake Buildkonfigurationen und problemlos zwischen ihnen in der IDE wechseln. 

Verwenden Sie andernfalls die **Datei "cmakelists.txt"** genauso wie Sie würde in jedem Projekt CMake Quelldateien angeben, suchen Bibliotheken, Compiler- und Linkeroptionen Optionen festlegen und Angeben von anderen Buildsystem Informationen in Bezug auf.

Wenn Sie Argumente beim Debuggen einer ausführbaren Datei übergeben müssen, können Sie eine andere Datei mit dem Namen **"Launch.VS.JSON"**. In einigen Szenarios generiert Visual Studio automatisch diese Dateien, und Sie können diese manuell bearbeiten. Sie können die Datei auch selbst erstellen.

> [!NOTE]
> Für andere Arten von Open Folder-Projekte werden zwei zusätzliche JSON-Dateien verwendet: **"Cppproperties.JSON"** und **"Tasks.VS.JSON"**. Diese sind für CMake-Projekte jedoch nicht relevant.

## <a name="import-an-existing-cache"></a>Importieren eines vorhandenen Caches

Wenn Sie eine vorhandene Datei „CMakeLists.txt“ importieren, extrahiert Visual Studio benutzerdefinierte Variablen automatisch und erstellt eine vorab mit Daten aufgefüllte Datei **CMakeSettings.json**, die auf diesen basiert. Der ursprüngliche Cache wird nicht geändert und kann weiterhin über die Befehlszeile oder über das Tool bzw. die IDE verwendet werden, mit dem bzw. der er generiert wurde. Die neue **"cmakesettings.JSON"** -Datei wird zusammen mit der im Stamm des Projekts "cmakelists.txt" gespeichert. Visual Studio generiert einen neuen Cache, der auf der Einstellungsdatei basiert. Sie können die automatische Cachegenerierung im Dialogfeld **Extras > Optionen > CMake > Allgemein** außer Kraft setzen.

Nicht der gesamte Inhalt des Caches wird importiert.  Eigenschaften wie der Generator und der Speicherort des Compilers werden durch die Standardwerte ersetzt, die in der IDE bekanntermaßen funktionieren.

### <a name="to-import-an-existing-cache"></a>Importieren eines vorhandenen Caches

1. Klicken Sie im Hauptmenü auf **Datei > Öffnen > CMake**:

   ![Öffnen von CMake](media/cmake-file-open.png "Datei > Öffnen > CMake")

   Dadurch wird der Assistent **CMake-Projekt aus Cache importieren** gestartet.

2. Navigieren Sie zur CMakeCache.txt-Datei, die Sie importieren möchten, und klicken Sie dann auf **OK**. Der Assistent **CMake-Projekt aus Cache importieren** wird angezeigt:

   ![Importieren eines CMake-Caches](media/cmake-import-wizard.png "Öffnen des Assistenten zum Importieren von CMake-Caches")

   Wenn der Assistent abgeschlossen ist, wird die neue Datei „CMakeCache.txt“ im **Projektmappen-Explorer** neben der Stammdatei „CMakeLists.txt“ in Ihrem Projekt geöffnet.

## <a name="building-cmake-projects"></a>Erstellen von CMake-Projekten

Folgende Optionen stehen Ihnen zum Erstellen eines CMake-Projekts zur Verfügung:

1. Suchen Sie in der Symbolleiste des Allgemeinen der **Konfigurationen** Dropdownliste; es ist wahrscheinlich "Linux-Debug" oder "X64-Debug" standardmäßig anzeigt wird. Wählen Sie die gewünschte Konfiguration, und drücken Sie **F5**, oder klicken Sie auf die **ausführen** auf der Symbolleiste die Schaltfläche (grüne Dreieck). Das Projekt wird genau wie eine Visual Studio-Projektmappe zunächst erstellt.

1. Klicken Sie mit der rechten Maustaste auf CMakeLists.txt, und wählen Sie im Kontextmenü **Erstellen** aus. Wenn mehrere Ziele in Ihrer Ordnerstruktur vorhanden sind, können Sie auswählen, den Build für alle oder nur für ein bestimmtes Ziel durchzuführen.

1. Alternativ können Sie im Hauptmenü auf **Erstellen > Projektmappe erstellen** klicken bzw. **F7** oder **STRG+UMSCHALT+B** drücken. Stellen Sie sicher, dass ein CMake-Ziel bereits in der Dropdownliste **Startelement** auf der Symbolleiste **Allgemein** ausgewählt ist.

![CMake-Menübefehl „Erstellen“](media/cmake-build-menu.png "CMake build menu command")

Sie können die Buildkonfigurationen, Umgebungsvariablen, Befehlszeilenargumente und andere Einstellungen anpassen, ohne Ändern der Datei "CMakeLists.txt" mithilfe der **"cmakesettings.JSON"** Datei. Weitere Informationen finden Sie unter [Customize CMake settings (Anpassen von CMake-Einstellungen)](customize-cmake-settings.md).

Erwartungsgemäß werden die Buildergebnisse im **Ausgabefenster** und in der **Fehlerliste** angezeigt.

![CMake-Buildfehler](media/cmake-build-errors.png "CMake build errors")

In einem Ordner mit mehreren Buildzielen können Sie das Element **Erstellen** im Menü **CMake** oder das Kontextmenü **CMakeLists.txt** auswählen, um das CMake-Ziel für den Build anzugeben. Wenn Sie **STRG+UMSCHALT+B** in einem CMake-Projekt drücken, wird das derzeit aktive Dokument erstellt.

## <a name="debugging-cmake-projects"></a>Debuggen von CMake-Projekten

Wenn Sie ein CMake-Projekt debuggen möchten, wählen Sie die gewünschte Konfiguration aus, und drücken Sie **F5**. Klicken Sie alternativ auf die Schaltfläche **Ausführen** auf der Symbolleiste. Wenn die Schaltfläche **Ausführen** „Startelement auswählen“ anzeigt, klicken Sie auf den Dropdownpfeil, und wählen Sie das Ziel aus, das ausgeführt werden soll. (In einem CMake-Projekt ist die Option „Aktuelles Dokument“ nur für CPP-Dateien gültig.)

![CMake-Schaltfläche „Ausführen“](media/cmake-run-button.png "Cmake run button")

Durch **Ausführen** oder **F5** wird das Projekt zunächst erstellt, wenn seit dem vorherigen Build Änderungen vorgenommen wurden.

Sie können eine Debugsitzung durch Festlegen von Eigenschaften CMake Anpassen der **"Launch.VS.JSON"** Datei. Weitere Informationen finden Sie unter [Configure CMake debugging sessions (Konfigurieren von CMake-Debugsitzungen)](configure-cmake-debugging-sessions.md).


## <a name="editing-cmakeliststxt-files"></a>Bearbeiten von CMakeLists.txt-Dateien

Wenn Sie eine CMakeLists.txt-Datei bearbeiten möchten, klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei, und wählen Sie **Öffnen** aus. Wenn Sie Änderungen an der Datei vornehmen, wird eine gelbe Statusleiste angezeigt, die Sie darüber informiert, dass IntelliSense ein Update durchführen möchte und die Möglichkeit bietet, den Updatevorgang abzubrechen. Weitere Informationen zu „CMakeLists.txt“ finden Sie unter [CMake documentation (CMake-Dokumentation)](https://cmake.org/documentation/).

   ![Bearbeiten der Datei „CMakeLists.txt“](media/cmake-cmakelists.png "CMakeLists.txt file editing")

Sobald Sie die Datei speichern, wird der Konfigurationsschritt automatisch erneut ausgeführt. Dieser zeigt Informationen im **Ausgabefenster** an. Fehler und Warnungen werden in der **Fehlerliste** oder im **Ausgabefenster** angezeigt. Doppelklicken Sie auf einen Fehler in der **Fehlerliste**, um zur problematischen Zeile in CMakeLists.txt zu navigieren.

   ![Fehler in der Datei „CMakeLists.txt“](media/cmake-cmakelists-error.png "CMakeLists.txt file errors")


## <a name="cmake-configure-step"></a>CMake-Konfigurationsschritt

Wenn wesentliche Änderungen vorgenommen werden, um die **"cmakesettings.JSON"** oder die Datei "cmakelists.txt"-Dateien, führt Visual Studio automatisch erneut im CMake Konfigurationsschritt. Wenn der Konfigurationsschritt ohne Fehler abgeschlossen wird, sind die gesammelten Informationen in C++ IntelliSense, in den C++-Sprachdiensten sowie in Build- und Debugvorgängen verfügbar.

Wenn mehrere CMake-Projekte den gleichen CMake-Konfigurationsnamen (z.B. „x86-Debug“) verwenden, werden alle konfiguriert und erstellt (in einem eigenen Stammordner für den Build), wenn diese Konfiguration ausgewählt ist. Sie können die Ziele aller CMake-Projekte debuggen, die in dieser CMake-Konfiguration enthalten sind.

   ![CMake-Menüelement „Nur erstellen“](media/cmake-build-only.png "CMake Build Only menu item")

Um beschränken von Builds und Debuggen Sitzungen für eine Teilmenge der Projekte in den Arbeitsbereich, erstellen Sie eine neue Konfiguration mit einem eindeutigen Namen in der **"cmakesettings.JSON"** Datei, und klicken Sie auf diese Projekte nur anzuwenden. Wenn diese Konfiguration ausgewählt ist, werden die IntelliSense-, Build- und Debugbefehle nur für die angegebenen Projekte aktiviert.

## <a name="troubleshooting-cmake-cache-errors"></a>Behandlung von CMake-Cachefehlern

Wenn Sie weitere Informationen zum Status des CMake-Caches benötigen, um ein Problem zu diagnostizieren, öffnen Sie das Hauptmenü **CMake** oder das Kontextmenü **CMakeLists.txt** im **Projektmappen-Explorer**, um einen der folgenden Befehle auszuführen:

- **Cache anzeigen** öffnet die Datei „CMakeCache.txt“ aus dem Stammordner des Builds im Editor. (Alle Änderungen, die Sie hier an „CMakeCache.txt“ vornehmen, werden verworfen, wenn Sie den Cache bereinigen. Um Änderungen vorzunehmen, die beibehalten werden, nachdem der Cache bereinigt wird, finden Sie unter [Anpassen von CMake-Einstellungen](customize-cmake-settings.md).)

- **Cacheordner öffnen** öffnet ein Explorer-Fenster zum Stammordner des Builds.

- **Cache bereinigen** löscht den Stammordner des Builds, sodass der nächste CMake-Konfigurationsschritt mit einem leeren Cache beginnt.

- **Cache generieren** erzwingt die Ausführung des Schritts „Generieren“, auch wenn Visual Studio die Umgebung für aktuell hält.

Die automatische Cachegenerierung kann im Dialogfeld **Extras > Optionen > CMake > Allgemein** deaktiviert werden.

## <a name="single-file-compilation"></a>Kompilierung einzelner Dateien

Klicken Sie zum Erstellen einer einzelnen Datei in einem CMake-Projekt im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei, und klicken Sie auf **Kompilieren**. Sie können die derzeit im Editor geöffnete Datei auch über das CMake-Hauptmenü erstellen:

![Kompilierung einzelner Dateien in CMake](media/cmake-single-file-compile.png)

## <a name="run-cmake-from-the-command-line"></a>Ausführen von CMake über die Befehlszeile

Wenn Sie CMake über den Visual Studio-Installer installiert haben, können Sie CMake über die Befehlszeile ausführen, indem Sie die folgenden Schritte ausführen:

1. Führen Sie die entsprechende Datei „vsdevcmd.bat“ (x86/x64) aus. Weitere Informationen finden Sie unter [Erstellen über die Befehlszeile](building-on-the-command-line.md).

1. Wechseln Sie zu Ihrem Ausgabeordner.

1. Führen Sie CMake zum Erstellen/Konfigurieren Ihrer App aus.
  
## <a name="see-also"></a>Siehe auch

[Tutorial: Erstellen von plattformübergreifenden C++-Projekten in Visual Studio](get-started-linux-cmake.md)<br/>
[Konfigurieren eines Linux CMake-Projekts](../linux/cmake-linux-project.md)<br/>
[Herstellen einer Verbindung mit Ihrem Linux-Remotecomputer](../linux/connect-to-your-remote-linux-computer.md)<br/>
[Anpassen von CMake-Buildeinstellungen](customize-cmake-settings.md)<br/>
[CMakeSettings.json-Referenz](cmakesettings-reference.md)<br/>
[Konfigurieren von CMake-Debugsitzungen](configure-cmake-debugging-sessions.md)<br/>
[Bereitstellen, Ausführen und Debuggen Ihres Linux-Projekts](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake predefined configuration reference (Referenz für vordefinierte CMake-Konfigurationen)](cmake-predefined-configuration-reference.md)<br/>
