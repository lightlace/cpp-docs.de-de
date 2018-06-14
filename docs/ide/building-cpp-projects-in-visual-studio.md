---
title: Erstellen von C++-Projekten in Visual Studio | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++ projects, building
- projects [C++], building
- builds [C++], about building in Visual Studio
ms.assetid: 9e8bc1a2-bb17-4951-937a-c757ed88d2d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a7008e7fe670471301968482fbd4c6c758f0ff5e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340501"
---
# <a name="building-c-projects-in-visual-studio"></a>Erstellen von C++-Projekten in Visual Studio
In der integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) vom Visual Studio gibt es verschiedene Möglichkeiten für das Erstellen einer kompletten Lösung oder nur eines Projekts. Sie können außerdem Buildeinstellungen ändern und benutzerdefiniere Buildschritte angeben, um Ihren Entwicklungsprozess effizienter zu gestalten.  
  
 Sie können wie folgt vorgehen, um eine Projektmappe zu erstellen, die in Visual Studio geöffnet und im **Projektmappen-Explorer** ausgewählt ist:  
  
-   Wählen Sie in der Menüleiste **Erstellen**, **Projektmappe erstellen**.  
  
-   Oder öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für die Projektmappe, und wählen Sie dann **Projektmappe erstellen** aus.  
  
-   Oder drücken Sie F7. (Das ist das Standardtastenkürzel für die C-/C++-Entwicklungseinstellungen.)  
  
-   Oder geben Sie `Build.BuildSolution` im [Befehlsfenster](/visualstudio/ide/reference/command-window) ein (klicken Sie in der Menüleiste auf **Ansicht** > **Andere Fenster** > **Befehlsfenster**).  
  
-   Oder geben Sie `build build solution` im Feld [Schnellstart](/visualstudio/ide/reference/quick-launch-environment-options-dialog-box) ein.  
  
 Sie können wie folgt vorgehen, um ein Projekt zu erstellen, das im **Projektmappen-Explorer** ausgewählt ist:  
  
-   Klicken Sie auf der Menüleiste auf**Erstellen** > **\<Projektname> erstellen**.  
  
-   Oder öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das Projekt, und wählen Sie dann **Erstellen** aus.  
  
-   Oder geben Sie `Build.BuildOnlyProject` im Befehlsfenster ein (klicken Sie in der Menüleiste auf **Ansicht** > **Andere Fenster** > **Befehlsfenster**).  
  
-   Oder geben Sie `build project only build only <project name>` im Feld „Schnellstart“ ein.  
  
 Wenn Sie eine Visual C++-Anwendung in Visual Studio erstellen, können Sie viele der Buildeinstellungen im Dialogfeld für die Eigenschaftenseiten des Projekts ändern. Informationen zum Festlegen von Projekteigenschaften finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../ide/working-with-project-properties.md).  
  
 Ein Beispiel für die Verwendung der IDE zum Erstellen, Aufbauen und Debuggen eines C++-Projekts finden Sie unter [Exemplarische Vorgehensweise: Erste Schritte mit der Visual Studio-IDE mit C++](/visualstudio/ide/getting-started-with-cpp-in-visual-studio). Ein Beispiel für die Verwendung der IDE zum Erstellen eines C++-/CLR-Projekts finden Sie unter [Walkthrough: Compiling a C++ Program that Targets the CLR in Visual Studio (Exemplarische Vorgehensweise: Kompilieren eines C++-Programms für die CLR in Visual Studio)](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md). Ein Beispiel für die Verwendung der IDE zum Erstellen einer Windows-Runtime-App finden Sie unter [Create your first Windows Runtime app using C++ (Erstellen Ihrer ersten Windows-Runtime-App mit C++)](http://msdn.microsoft.com/library/windows/apps/hh974580.aspx).  
  
 Weitere Informationen zum Erstellen, Ändern von Buildeinstellungen und Angeben von benutzerdefinierten Buildschritten finden Sie in den folgenden Artikeln.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Grundlagen benutzerdefinierter Buildschritte und Buildereignisse](../ide/understanding-custom-build-steps-and-build-events.md)  
 Beschreibt, wie Sie den Buildprozess in der integrierten Entwicklungsumgebung anpassen.  
  
 [Gängige Makros für Buildbefehle und -eigenschaften.](../ide/common-macros-for-build-commands-and-properties.md)  
 Listet Makros auf, die Sie verwenden können, wenn Zeichenfolgen akzeptiert werden.  
  
 [Erstellen externer Projekte](../ide/building-external-projects.md)  
 Stellt das Erstellen von Projekten dar, die Funktionen außerhalb der integrierten Entwicklungsumgebung verwenden.  
  
 [Projektdateien](../ide/project-files.md)  
 Stellt die XML-Struktur einer .vcxproj-Datei dar.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [VC++ Directories, Projects, Options Dialog Box (VC++-Verzeichnisse, Projekte, Dialogfeld „Optionen“)](vcpp-directories-property-page.md)  
 (Nur MSBuild-Projekte) Stellt dar, wie Sie den Suchpfad für ausführbare Dateien ändern und Dateien, Bibliotheksdateien und Quellcodedateien während des Erstellens einfügen.  
  
 [Kompilieren und Erstellen](/visualstudio/ide/compiling-and-building-in-visual-studio)  
 Bietet Informationen zum Erstellen in Visual Studio.  
  
 [Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)  
 Bietet Links zu Themen, in denen das Erstellen von Programmen über die Befehlszeile oder die integrierte Entwicklungsumgebung von Visual Studio beschrieben sind.  
  
 [Referenz zur C/C++-Erstellung](../build/reference/c-cpp-building-reference.md)  
 Bietet Links zu einem Überblick für das Erstellen von Programmen C++, Compiler- und Linkeroptionen und zusätzlichen Buildtools.  
  
 [Aktualisieren von Projekten von früheren Versionen von Visual C++](../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md)  
 Enthält Links zu Artikeln über Probleme beim Upgrade von C++-Projekten auf neuere Versionen des Compilertoolsets.  
  
[Visual C++-Handbuch: Portieren und Aktualisieren](../porting/visual-cpp-porting-and-upgrading-guide.md)  
  Weitere Informationen zum Upgraden von C++-Anwendungen, die in früheren Versionen von Visual Studio erstellt wurden sowie zur Migration von Anwendungen, die mithilfe von anderen Tools als Visual Studio erstellt wurden.  
  
## <a name="see-also"></a>Siehe auch  
 [Universelle Windows-Apps (C++)](../windows/universal-windows-apps-cpp.md)