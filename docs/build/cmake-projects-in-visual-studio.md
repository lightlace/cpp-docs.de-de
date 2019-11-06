---
title: CMake-Projekte in Visual Studio
ms.date: 10/31/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: 2efd228971f19ca525f245014f3046b1b62995dc
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624593"
---
# <a name="cmake-projects-in-visual-studio"></a>CMake-Projekte in Visual Studio

CMake ist ein plattformübergreifendes Open Source-Tool, das zum Definieren von Buildprozessen verwendet wird, die auf mehreren Plattformen ausgeführt werden. In diesem Artikel wird davon ausgegangen, dass Sie mit CMake vertraut sind. Weitere Informationen finden Sie unter [Build, Test and Package Your Software With CMake (Erstellen, Testen und Packen Ihrer Software mit CMake)](https://cmake.org/).

> [!NOTE]
> CMake wurde in den letzten Versionen immer mehr und mehr in Visual Studio integriert. Um die korrekten Informationen für die Version anzuzeigen, die Sie verwenden, stellen Sie sicher, dass die Versions Auswahl in der linken oberen Ecke dieser Seite ordnungsgemäß festgelegt ist.

::: moniker range="vs-2019"

Die  **C++ Komponente "cmake-Tools für Windows** " verwendet die Funktion " [Ordner öffnen](open-folder-projects-cpp.md) ", um cmake-Projektdateien (z. b. "CMakeLists. txt") direkt für IntelliSense und Browsen zu verarbeiten. Es werden sowohl Ninja- als auch Visual Studio-Generatoren unterstützt. Wenn Sie einen Visual Studio-Generator verwenden, wird eine temporäre Projektdatei generiert und an „msbuild.exe“ übergeben. Diese wird jedoch nie für IntelliSense oder das Durchsuchen geladen. Sie können auch einen vorhandenen cmake-Cache importieren.

## <a name="installation"></a>Installation

**Cmake-Tools für Windows werden standardmäßig als Teil der Desktop Entwicklung mit Arbeitsauslastung und als Teil der Linux-Entwicklung mit Arbeitsauslastung installiert. C++**  **C++** **C++** Weitere Informationen finden Sie unter [plattformübergreifende cmake-Projekte](../linux/cmake-linux-project.md) .

![CMake-Komponente in der Workload „Desktopentwicklung mit C++“](media/cmake-install-2019.png)

Weitere Informationen finden Sie unter [Install the C++ Linux workload in Visual Studio (Installieren der C++-Workload unter Linux in Visual Studio)](../linux/download-install-and-setup-the-linux-development-workload.md).

## <a name="ide-integration"></a>IDE-Integration

Wenn Sie **Datei > Öffnen Sie > Ordner** , um einen Ordner zu öffnen, der die Datei "CMakeLists. txt" enthält, geschieht Folgendes:

- Visual Studio fügt dem Menü " **Projekt** " **cmake** -Elemente mit Befehlen zum Anzeigen und Bearbeiten von cmake-Skripts hinzu.

- Der **Projektmappen-Explorer** zeigt die Ordnerstruktur und die Dateien an.

- Visual Studio führt cmake. exe aus und generiert die cmake-Cachedatei (*cmakecache. txt*) für die Standard *Konfiguration*, bei der es sich um x64 Debug handelt. Die CMake-Befehlszeile wird im **Ausgabefenster** zusammen mit zusätzlichen Ausgaben von CMake angezeigt.

- Im Hintergrund beginnt Visual Studio damit, die Quelldateien zu indizieren, um IntelliSense, das Durchsuchen von Informationen, das Refactoring und vieles mehr zu ermöglichen. Während Sie arbeiten, überwacht Visual Studio die Änderungen im Editor und auf dem Datenträger, damit der Index mit den Quellen synchron ist.

Sie können Ordner öffnen, die eine beliebige Anzahl von CMake-Projekten enthalten. Visual Studio erkennt und konfiguriert alle CMakeLists.txt-Stammdateien in Ihrem Arbeitsbereich. CMake-Vorgänge (Konfigurieren, Erstellen, Debuggen) sowie C++ IntelliSense und das Durchsuchen sind für alle CMake-Projekte in Ihrem Arbeitsbereich verfügbar.

![CMake-Projekte mit mehreren Stammdateien](media/cmake-multiple-roots.png)

Sie können die Projekte auch logisch strukturiert nach Zielen anzeigen. Wählen Sie in der Dropdownliste der Symbolleiste des **Projektmappen-Explorers** die Option **Zielansicht** aus:

![Schaltfläche für CMake-Zielansicht](media/cmake-targets-view.png)

Klicken Sie oben in der **Projektmappen-Explorer** auf die Schaltfläche **alle Dateien anzeigen** , um alle vom cmake generierten Ausgaben in den Ordnern *out/Build/<config>* anzuzeigen.

Visual Studio verwendet eine Datei namens " **cmakesettings. JSON** ", die es Ihnen ermöglicht, mehrere Buildkonfigurationen zu definieren und zu speichern und bequem zwischen Ihnen in der IDE zu wechseln. Eine *Konfiguration* ist ein Visual Studio-Konstrukt, das Einstellungen kapselt, die für einen bestimmten Buildtyp spezifisch sind. Die Einstellungen werden verwendet, um die Standard Befehlszeilenoptionen zu konfigurieren, die Visual Studio an cmake. exe übergibt. Sie können hier auch weitere cmake-Optionen angeben und alle weiteren Variablen definieren, die Sie wünschen. Alle Optionen werden entweder als interne oder externe Variablen in den cmake-Cache geschrieben. In Visual Studio 2019 bietet der **cmake Settings Editor** eine bequeme Möglichkeit zum Bearbeiten der Einstellungen. Weitere Informationen finden Sie unter [Anpassen der cmake-Einstellungen](customize-cmake-settings.md) .

Eine Einstellung, `intelliSenseMode` wird nicht an cmake übergeben, sondern nur von Visual Studio verwendet.

Verwenden Sie die Datei " **CMakeLists. txt** " in jedem Projektordner genauso wie in einem beliebigen cmake-Projekt, um Quelldateien anzugeben, Bibliotheken zu suchen, Compileroptionen und Linkeroptionen festzulegen und andere buildsystembezogene Informationen anzugeben.

Wenn Sie der Debugzeit Argumente an eine ausführbare Datei übergeben müssen, können Sie eine andere Datei mit dem Namen **Launch. vs. JSON**verwenden. In einigen Szenarios generiert Visual Studio automatisch diese Dateien, und Sie können diese manuell bearbeiten. Sie können die Datei auch selbst erstellen.

> [!NOTE]
> Für andere Arten von geöffneten Ordner Projekten werden zwei zusätzliche JSON-Dateien verwendet: **cppproperties. JSON** und **Tasks. vs. JSON**. Diese sind für CMake-Projekte jedoch nicht relevant.

## <a name="open-an-existing-cache"></a>Öffnen eines vorhandenen Caches

Wenn Sie eine vorhandene cmake-Cachedatei (*cmakecache. txt*) öffnen, versucht Visual Studio nicht, Ihren Cache und ihre Buildstruktur für Sie zu verwalten. Dadurch erhalten Ihre benutzerdefinierten oder bevorzugten Tools die komplette Kontrolle darüber, wie cmake das Projekt konfiguriert. Sie können einen vorhandenen Cache in Visual Studio über **Datei öffnen > > cmake öffnen** und zu einer vorhandenen Datei " *cmakecache. txt*" navigieren. Wenn Sie das Projekt bereits in Visual Studio geöffnet haben, können Sie auch einen vorhandenen Cache auf die gleiche Weise hinzufügen, wie Sie eine neue Konfiguration hinzufügen würden. Weitere Informationen finden Sie in unserem Blogbeitrag zum [Öffnen eines vorhandenen Caches in Visual Studio](https://devblogs.microsoft.com/cppblog/open-existing-cmake-caches-in-visual-studio/).

## <a name="building-cmake-projects"></a>Erstellen von CMake-Projekten

Folgende Optionen stehen Ihnen zum Erstellen eines CMake-Projekts zur Verfügung:

1. Suchen Sie auf der Symbolleiste Allgemein nach der Dropdown Liste **Konfigurationen** . Es wird wahrscheinlich standardmäßig "x64-Debug" angezeigt. Wählen Sie die gewünschte Konfiguration aus, und drücken Sie **F5**, oder klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** (grünes Dreieck). Das Projekt wird genau wie eine Visual Studio-Projektmappe zunächst erstellt.

1. Klicken Sie mit der rechten Maustaste auf CMakeLists.txt, und wählen Sie im Kontextmenü **Erstellen** aus. Wenn mehrere Ziele in Ihrer Ordnerstruktur vorhanden sind, können Sie auswählen, den Build für alle oder nur für ein bestimmtes Ziel durchzuführen.

1. Wählen Sie im Hauptmenü **Build > Build all** (**F7** oder **STRG + UMSCHALT + B**) aus. Stellen Sie sicher, dass ein CMake-Ziel bereits in der Dropdownliste **Startelement** auf der Symbolleiste **Allgemein** ausgewählt ist.

![Cmake Build (Menübefehl)](media/cmake-build-menu.png "Cmake-Build (Befehlsmenü)")

Erwartungsgemäß werden die Buildergebnisse im **Ausgabefenster** und in der **Fehlerliste** angezeigt.

![Cmake-Buildfehler](media/cmake-build-errors.png "Cmake-Buildfehler")

In einem Ordner mit mehreren Buildzielen können Sie das Element **Erstellen** im Menü **CMake** oder das Kontextmenü *CMakeLists.txt* auswählen, um das CMake-Ziel für den Build anzugeben. Wenn Sie **STRG+UMSCHALT+B** in einem CMake-Projekt drücken, wird das derzeit aktive Dokument erstellt.

## <a name="debugging-cmake-projects"></a>Debuggen von CMake-Projekten

Wenn Sie ein CMake-Projekt debuggen möchten, wählen Sie die gewünschte Konfiguration aus, und drücken Sie **F5**. Klicken Sie alternativ auf die Schaltfläche **Ausführen** auf der Symbolleiste. Wenn die Schaltfläche **Ausführen** „Startelement auswählen“ anzeigt, klicken Sie auf den Dropdownpfeil, und wählen Sie das Ziel aus, das ausgeführt werden soll. (In einem CMake-Projekt ist die Option „Aktuelles Dokument“ nur für CPP-Dateien gültig.)

![Schaltfläche "cmake Run"](media/cmake-run-button.png "Schaltfläche "cmake Run"")

Durch **Ausführen** oder **F5** wird das Projekt zunächst erstellt, wenn seit dem vorherigen Build Änderungen vorgenommen wurden. Änderungen an *cmakesettings. JSON* bewirken, dass der cmake-Cache erneut generiert wird.

Sie können eine cmake-Debugsitzung anpassen, indem Sie die Eigenschaften in der Datei " **Launch. vs. JSON** " festlegen. Weitere Informationen finden Sie unter [Configure CMake debugging sessions (Konfigurieren von CMake-Debugsitzungen)](configure-cmake-debugging-sessions.md).

## <a name="just-my-code-for-cmake-projects"></a>Nur eigenen Code für cmake-Projekte

Wenn Sie für Windows mit dem MSVC-Compiler erstellen, haben die cmake-Projekte Unterstützung für das Debuggen von nur eigenen Code im Compiler und Linker, wenn die Option in Visual Studio aktiviert ist. Um die **Einstellung zu ändern** , wechseln Sie zu Extras > **Optionen** > **Debuggen** > **Allgemein**.

## <a name="vcpkg-integration"></a>Vcpkg-Integration

Wenn Sie [vcpkg](vcpkg.md)installiert haben, integrieren cmake-Projekte, die in Visual Studio geöffnet werden, die vcpkg-Toolkette-Datei automatisch. Dies bedeutet, dass für die Verwendung von vcpkg mit ihren cmake-Projekten keine zusätzliche Konfiguration erforderlich ist. Diese Unterstützung funktioniert sowohl für lokale vcpkg-Installationen als auch für vcpkg-Installationen auf Remote Systemen, die Sie als Ziel haben. Dieses Verhalten wird automatisch deaktiviert, wenn Sie eine andere Toolkette in der Konfiguration der cmake-Einstellungen angeben.

## <a name="customize-configuration-feedback"></a>Anpassen des Konfigurations Feedbacks

Standardmäßig werden die meisten Konfigurations Nachrichten unterdrückt, es sei denn, es ist ein Fehler aufgetreten. Alle Nachrichten können angezeigt werden, indem Sie dieses **Feature in Extras** > **Optionen** > **cmake**aktivieren.

   ![Konfigurieren von cmake-Diagnose Optionen](media/vs2019-cmake-configure-options.png "Cmake-Diagnose Optionen")

## <a name="editing-cmakeliststxt-files"></a>Bearbeiten von CMakeLists.txt-Dateien

Wenn Sie eine CMakeLists.txt-Datei bearbeiten möchten, klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei, und wählen Sie **Öffnen** aus. Wenn Sie Änderungen an der Datei vornehmen, wird eine gelbe Statusleiste angezeigt, die Sie darüber informiert, dass IntelliSense ein Update durchführen möchte und die Möglichkeit bietet, den Updatevorgang abzubrechen. Weitere Informationen zu „CMakeLists.txt“ finden Sie unter [CMake documentation (CMake-Dokumentation)](https://cmake.org/documentation/).

   ![Datei "CMakeLists. txt" Bearbeiten](media/cmake-cmakelists.png "Datei "CMakeLists. txt" Bearbeiten")

Sobald Sie die Datei speichern, wird der Konfigurationsschritt automatisch erneut ausgeführt. Dieser zeigt Informationen im **Ausgabefenster** an. Fehler und Warnungen werden in der **Fehlerliste** oder im **Ausgabefenster** angezeigt. Doppelklicken Sie auf einen Fehler in der **Fehlerliste**, um zur problematischen Zeile in CMakeLists.txt zu navigieren.

   ![CMakeLists. txt-Datei Fehler](media/cmake-cmakelists-error.png "CMakeLists. txt-Datei Fehler")

## <a name="cmake-configure-step"></a>CMake-Konfigurationsschritt

Wenn wichtige Änderungen an den Dateien *cmakesettings. JSON* oder *CMakeLists. txt* vorgenommen werden, führt Visual Studio automatisch den cmake-Konfigurationsschritt erneut aus. Wenn der Konfigurationsschritt ohne Fehler abgeschlossen wird, sind die gesammelten Informationen in C++ IntelliSense, in den C++-Sprachdiensten sowie in Build- und Debugvorgängen verfügbar.

## <a name="troubleshooting-cmake-cache-errors"></a>Behandlung von CMake-Cachefehlern

Wenn Sie weitere Informationen zum Status des cmake-Caches benötigen, um ein Problem zu diagnostizieren, öffnen Sie das **Projekt** -Hauptmenü oder das Kontextmenü *CMakeLists. txt* in **Projektmappen-Explorer** , um einen der folgenden Befehle auszuführen:

- Der **Ansichts Cache** öffnet die Datei " *cmakecache. txt* " aus dem Build Root-Ordner im Editor. (Alle Änderungen, die Sie an dieser Stelle in " *cmakecache. txt* " vornehmen, werden zurückgesetzt, wenn Sie den Cache bereinigen. Informationen zum vornehmen von Änderungen, die nach dem Bereinigen des Caches beibehalten werden, finden Sie unter [Anpassen der cmake-Einstellungen](customize-cmake-settings.md)

- **Cacheordner öffnen** öffnet ein Explorer-Fenster zum Stammordner des Builds.

- **Cache bereinigen** löscht den Stammordner des Builds, sodass der nächste CMake-Konfigurationsschritt mit einem leeren Cache beginnt.

- **Cache generieren** erzwingt die Ausführung des Schritts „Generieren“, auch wenn Visual Studio die Umgebung für aktuell hält.

Die automatische Cache Generierung kann im Dialog **> Optionen > cmake >** Dialogfeld "Allgemein" deaktiviert werden.

## <a name="run-cmake-from-the-command-line"></a>Ausführen von CMake über die Befehlszeile

Wenn Sie CMake über den Visual Studio-Installer installiert haben, können Sie CMake über die Befehlszeile ausführen, indem Sie die folgenden Schritte ausführen:

1. Führen Sie die entsprechende Datei „vsdevcmd.bat“ (x86/x64) aus. Weitere Informationen finden Sie unter [Erstellen über die Befehlszeile](building-on-the-command-line.md).

1. Wechseln Sie zu Ihrem Ausgabeordner.

1. Führen Sie CMake zum Erstellen/Konfigurieren Ihrer App aus.

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 2017 bietet umfassende Unterstützung für cmake, einschließlich [plattformübergreifender cmake-Projekte](../linux/cmake-linux-project.md). Die Komponente **Visual C++-Tools für CMake** verwendet die Funktion **Ordner öffnen**, um zu ermöglichen, dass die IDE CMake-Projektdateien (z.B. „CMakeLists.txt“) direkt für IntelliSense und das Durchsuchen nutzt. Es werden sowohl Ninja- als auch Visual Studio-Generatoren unterstützt. Wenn Sie einen Visual Studio-Generator verwenden, wird eine temporäre Projektdatei generiert und an „msbuild.exe“ übergeben. Diese wird jedoch nie für IntelliSense oder das Durchsuchen geladen. Sie können auch einen vorhandenen cmake-Cache importieren. 

## <a name="installation"></a>Installation

**Visual C++-Tools für CMake** wird standardmäßig als Teil der Workloads **Desktopentwicklung mit C++** und **Linux-Entwicklung mit C++** installiert.

![CMake-Komponente in der Workload „Desktopentwicklung mit C++“](media/cmake-install.png)

Weitere Informationen finden Sie unter [Install the C++ Linux workload in Visual Studio (Installieren der C++-Workload unter Linux in Visual Studio)](../linux/download-install-and-setup-the-linux-development-workload.md).

## <a name="ide-integration"></a>IDE-Integration

Wenn Sie **Datei > Öffnen Sie > Ordner** , um einen Ordner zu öffnen, der die Datei "CMakeLists. txt" enthält, geschieht Folgendes:

- Visual Studio fügt ein **CMake**-Menüelement zum Hauptmenü hinzu, das Befehle für das Anzeigen und Bearbeiten von CMake-Skripts enthält.

- Der **Projektmappen-Explorer** zeigt die Ordnerstruktur und die Dateien an.

- Visual Studio führt „CMake.exe“ aus und generiert optional den CMake-Cache für die *Standardkonfiguration* (x86 Debug). Die CMake-Befehlszeile wird im **Ausgabefenster** zusammen mit zusätzlichen Ausgaben von CMake angezeigt.

- Im Hintergrund beginnt Visual Studio damit, die Quelldateien zu indizieren, um IntelliSense, das Durchsuchen von Informationen, das Refactoring und vieles mehr zu ermöglichen. Während Sie arbeiten, überwacht Visual Studio die Änderungen im Editor und auf dem Datenträger, damit der Index mit den Quellen synchron ist.

Sie können Ordner öffnen, die eine beliebige Anzahl von CMake-Projekten enthalten. Visual Studio erkennt und konfiguriert alle CMakeLists.txt-Stammdateien in Ihrem Arbeitsbereich. CMake-Vorgänge (Konfigurieren, Erstellen, Debuggen) sowie C++ IntelliSense und das Durchsuchen sind für alle CMake-Projekte in Ihrem Arbeitsbereich verfügbar.

![CMake-Projekte mit mehreren Stammdateien](media/cmake-multiple-roots.png)

Sie können die Projekte auch logisch strukturiert nach Zielen anzeigen. Wählen Sie in der Dropdownliste der Symbolleiste des **Projektmappen-Explorers** die Option **Zielansicht** aus:

![Schaltfläche für CMake-Zielansicht](media/cmake-targets-view.png)

Visual Studio verwendet eine Datei namens " *cmakesettings. JSON* " zum Speichern von Umgebungsvariablen oder Befehlszeilenoptionen für "cmake. exe". Mit *cmakesettings. JSON* können Sie auch mehrere cmake-Buildkonfigurationen definieren und speichern und bequem zwischen Ihnen in der IDE wechseln.

Verwenden Sie andernfalls die Datei " *CMakeLists. txt* " genauso wie in einem beliebigen cmake-Projekt, um Quelldateien anzugeben, Bibliotheken zu suchen, Compileroptionen und Linkeroptionen festzulegen und andere buildsystembezogene Informationen anzugeben.

Wenn Sie der Debugzeit Argumente an eine ausführbare Datei übergeben müssen, können Sie eine andere Datei mit dem Namen **Launch. vs. JSON**verwenden. In einigen Szenarios generiert Visual Studio automatisch diese Dateien, und Sie können diese manuell bearbeiten. Sie können die Datei auch selbst erstellen.

> [!NOTE]
> Für andere Arten von geöffneten Ordner Projekten werden zwei zusätzliche JSON-Dateien verwendet: **cppproperties. JSON** und **Tasks. vs. JSON**. Diese sind für CMake-Projekte jedoch nicht relevant.

## <a name="import-an-existing-cache"></a>Importieren eines vorhandenen Caches

Wenn Sie eine vorhandene Datei " *cmakecache. txt* " importieren, extrahiert Visual Studio automatisch angepasste Variablen und erstellt eine vorab aufgefüllte *cmakesettings. JSON* -Datei, die darauf basiert. Der ursprüngliche Cache wird nicht geändert und kann weiterhin über die Befehlszeile oder über das Tool bzw. die IDE verwendet werden, mit dem bzw. der er generiert wurde. Die neue Datei " *cmakesettings. JSON* " wird zusammen mit dem Stammverzeichnis des Projekts "CMakeLists. txt" platziert. Visual Studio generiert einen neuen Cache, der auf der Einstellungsdatei basiert. Sie können die automatische Cache Generierung im Dialog **> Optionen > cmake >** Dialogfeld "Allgemein" überschreiben.

Nicht der gesamte Inhalt des Caches wird importiert.  Eigenschaften wie der Generator und der Speicherort des Compilers werden durch die Standardwerte ersetzt, die in der IDE bekanntermaßen funktionieren.

### <a name="to-import-an-existing-cache"></a>Importieren eines vorhandenen Caches

1. Wählen Sie im Hauptmenü Datei aus, **> > cmake öffnen**:

   ![Cmake öffnen](media/cmake-file-open.png "Datei, öffnen, cmake")

   Dadurch wird der Assistent **CMake-Projekt aus Cache importieren** gestartet.

2. Navigieren Sie zur Datei " *cmakecache. txt* ", die Sie importieren möchten, und klicken Sie dann auf **OK**. Der Assistent **CMake-Projekt aus Cache importieren** wird angezeigt:

   ![Importieren eines cmake-Caches](media/cmake-import-wizard.png "Öffnen des Assistenten zum Importieren von cmake-Caches")

   Wenn der Assistent abgeschlossen ist, können Sie die neue Datei " *cmakecache. txt* " in **Projektmappen-Explorer** neben der Stammdatei " *CMakeLists. txt* " in Ihrem Projekt sehen.

## <a name="building-cmake-projects"></a>Erstellen von CMake-Projekten

Folgende Optionen stehen Ihnen zum Erstellen eines CMake-Projekts zur Verfügung:

1. Suchen Sie auf der Symbolleiste Allgemein nach der Dropdown Liste **Konfigurationen** . Es wird wahrscheinlich standardmäßig "Linux-Debug" oder "x64-Debug" angezeigt. Wählen Sie die gewünschte Konfiguration aus, und drücken Sie **F5**, oder klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** (grünes Dreieck). Das Projekt wird genau wie eine Visual Studio-Projektmappe zunächst erstellt.

1. Klicken Sie mit der rechten Maustaste auf die Datei " *CMakeLists. txt* ", und wählen Sie im Kontextmenü **Erstellen** Wenn mehrere Ziele in Ihrer Ordnerstruktur vorhanden sind, können Sie auswählen, den Build für alle oder nur für ein bestimmtes Ziel durchzuführen.

1. Wählen Sie im Hauptmenü die Option **Build >** Projekt Mappe erstellen (**F7** oder **STRG + UMSCHALT + B**) aus. Stellen Sie sicher, dass ein CMake-Ziel bereits in der Dropdownliste **Startelement** auf der Symbolleiste **Allgemein** ausgewählt ist.

![Cmake Build (Menübefehl)](media/cmake-build-menu.png "Cmake-Build (Befehlsmenü)")

Sie können Buildkonfigurationen, Umgebungsvariablen, Befehlszeilenargumente und andere Einstellungen anpassen, ohne die Datei "CMakeLists. txt" mit der Datei " *cmakesettings. JSON* " zu ändern. Weitere Informationen finden Sie unter [Customize CMake settings (Anpassen von CMake-Einstellungen)](customize-cmake-settings.md).

Erwartungsgemäß werden die Buildergebnisse im **Ausgabefenster** und in der **Fehlerliste** angezeigt.

![Cmake-Buildfehler](media/cmake-build-errors.png "Cmake-Buildfehler")

In einem Ordner mit mehreren Buildzielen können Sie das Element **Erstellen** im Menü **CMake** oder das Kontextmenü *CMakeLists.txt* auswählen, um das CMake-Ziel für den Build anzugeben. Wenn Sie **STRG+UMSCHALT+B** in einem CMake-Projekt drücken, wird das derzeit aktive Dokument erstellt.

## <a name="debugging-cmake-projects"></a>Debuggen von CMake-Projekten

Wenn Sie ein CMake-Projekt debuggen möchten, wählen Sie die gewünschte Konfiguration aus, und drücken Sie **F5**. Klicken Sie alternativ auf die Schaltfläche **Ausführen** auf der Symbolleiste. Wenn die Schaltfläche **Ausführen** „Startelement auswählen“ anzeigt, klicken Sie auf den Dropdownpfeil, und wählen Sie das Ziel aus, das ausgeführt werden soll. (In einem CMake-Projekt ist die Option „Aktuelles Dokument“ nur für CPP-Dateien gültig.)

![Schaltfläche "cmake Run"](media/cmake-run-button.png "Schaltfläche "cmake Run"")

Durch **Ausführen** oder **F5** wird das Projekt zunächst erstellt, wenn seit dem vorherigen Build Änderungen vorgenommen wurden.

Sie können eine cmake-Debugsitzung anpassen, indem Sie die Eigenschaften in der Datei " **Launch. vs. JSON** " festlegen. Weitere Informationen finden Sie unter [Configure CMake debugging sessions (Konfigurieren von CMake-Debugsitzungen)](configure-cmake-debugging-sessions.md).

## <a name="editing-cmakeliststxt-files"></a>Bearbeiten von CMakeLists.txt-Dateien

Wenn Sie eine CMakeLists.txt-Datei bearbeiten möchten, klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei, und wählen Sie **Öffnen** aus. Wenn Sie Änderungen an der Datei vornehmen, wird eine gelbe Statusleiste angezeigt, die Sie darüber informiert, dass IntelliSense ein Update durchführen möchte und die Möglichkeit bietet, den Updatevorgang abzubrechen. Weitere Informationen zu „CMakeLists.txt“ finden Sie unter [CMake documentation (CMake-Dokumentation)](https://cmake.org/documentation/).

   ![Datei "CMakeLists. txt" Bearbeiten](media/cmake-cmakelists.png "Datei "CMakeLists. txt" Bearbeiten")

Sobald Sie die Datei speichern, wird der Konfigurationsschritt automatisch erneut ausgeführt. Dieser zeigt Informationen im **Ausgabefenster** an. Fehler und Warnungen werden in der **Fehlerliste** oder im **Ausgabefenster** angezeigt. Doppelklicken Sie auf einen Fehler in der **Fehlerliste**, um zur problematischen Zeile in CMakeLists.txt zu navigieren.

   ![CMakeLists. txt-Datei Fehler](media/cmake-cmakelists-error.png "CMakeLists. txt-Datei Fehler")

## <a name="cmake-configure-step"></a>CMake-Konfigurationsschritt

Wenn wichtige Änderungen an den Dateien *cmakesettings. JSON* oder CMakeLists. txt vorgenommen werden, führt Visual Studio automatisch den cmake-Konfigurationsschritt erneut aus. Wenn der Konfigurationsschritt ohne Fehler abgeschlossen wird, sind die gesammelten Informationen in C++ IntelliSense, in den C++-Sprachdiensten sowie in Build- und Debugvorgängen verfügbar.

Wenn mehrere CMake-Projekte den gleichen CMake-Konfigurationsnamen (z.B. „x86-Debug“) verwenden, werden alle konfiguriert und erstellt (in einem eigenen Stammordner für den Build), wenn diese Konfiguration ausgewählt ist. Sie können die Ziele aller CMake-Projekte debuggen, die in dieser CMake-Konfiguration enthalten sind.

   ![Cmake-Menü Element nur Build](media/cmake-build-only.png "Cmake-Menü Element nur Build")

Erstellen Sie eine neue Konfiguration mit einem eindeutigen Namen in der Datei " *cmakesettings. JSON* ", um Builds und Debugsitzungen auf eine Teilmenge der Projekte im Arbeitsbereich zu beschränken, und wenden Sie Sie nur auf diese Projekte an. Wenn diese Konfiguration ausgewählt ist, werden die IntelliSense-, Build- und Debugbefehle nur für die angegebenen Projekte aktiviert.

## <a name="troubleshooting-cmake-cache-errors"></a>Behandlung von CMake-Cachefehlern

Wenn Sie weitere Informationen zum Status des CMake-Caches benötigen, um ein Problem zu diagnostizieren, öffnen Sie das Hauptmenü **CMake** oder das Kontextmenü *CMakeLists.txt* im **Projektmappen-Explorer**, um einen der folgenden Befehle auszuführen:

- **Cache anzeigen** öffnet die Datei „CMakeCache.txt“ aus dem Stammordner des Builds im Editor. (Alle Änderungen, die Sie hier an „CMakeCache.txt“ vornehmen, werden verworfen, wenn Sie den Cache bereinigen. Informationen zum vornehmen von Änderungen, die nach dem Bereinigen des Caches beibehalten werden, finden Sie unter [Anpassen der cmake-Einstellungen](customize-cmake-settings.md)

- **Cacheordner öffnen** öffnet ein Explorer-Fenster zum Stammordner des Builds.

- **Cache bereinigen** löscht den Stammordner des Builds, sodass der nächste CMake-Konfigurationsschritt mit einem leeren Cache beginnt.

- **Cache generieren** erzwingt die Ausführung des Schritts „Generieren“, auch wenn Visual Studio die Umgebung für aktuell hält.

Die automatische Cache Generierung kann im Dialog **> Optionen > cmake >** Dialogfeld "Allgemein" deaktiviert werden.

## <a name="single-file-compilation"></a>Kompilierung einzelner Dateien

Klicken Sie zum Erstellen einer einzelnen Datei in einem CMake-Projekt im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei, und klicken Sie auf **Kompilieren**. Sie können die derzeit im Editor geöffnete Datei auch über das CMake-Hauptmenü erstellen:

![Kompilierung einzelner Dateien in CMake](media/cmake-single-file-compile.png)

## <a name="run-cmake-from-the-command-line"></a>Ausführen von CMake über die Befehlszeile

Wenn Sie CMake über den Visual Studio-Installer installiert haben, können Sie CMake über die Befehlszeile ausführen, indem Sie die folgenden Schritte ausführen:

1. Führen Sie die entsprechende Datei „vsdevcmd.bat“ (x86/x64) aus. Weitere Informationen finden Sie unter [Erstellen über die Befehlszeile](building-on-the-command-line.md).

1. Wechseln Sie zu Ihrem Ausgabeordner.

1. Führen Sie CMake zum Erstellen/Konfigurieren Ihrer App aus.

::: moniker-end

::: moniker range="vs-2015"

In Visual Studio 2015 können Visual Studio-Benutzer einen [CMake-Generator](https://cmake.org/cmake/help/latest/manual/cmake-generators.7.html) verwenden, um MSBuild-Projektdateien zu generieren, die anschließend von der IDE für IntelliSense sowie für das Durchsuchen und die Kompilierung verwendet werden.

::: moniker-end


## <a name="see-also"></a>Siehe auch

[Tutorial: Erstellen C++ von plattformübergreifenden Projekten in Visual Studio](get-started-linux-cmake.md)<br/>
[Konfigurieren eines Linux CMake-Projekts](../linux/cmake-linux-project.md)<br/>
[Herstellen einer Verbindung mit Ihrem Linux-Remotecomputer](../linux/connect-to-your-remote-linux-computer.md)<br/>
[Anpassen von CMake-Buildeinstellungen](customize-cmake-settings.md)<br/>
[CMakeSettings.json-Referenz](o regenerate the root-reference.md)<br/>
[Konfigurieren von CMake-Debugsitzungen](configure-cmake-debugging-sessions.md)<br/>
[Bereitstellen, Ausführen und Debuggen Ihres Linux-Projekts](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake predefined configuration reference (Referenz für vordefinierte CMake-Konfigurationen)](cmake-predefined-configuration-reference.md)<br/>
