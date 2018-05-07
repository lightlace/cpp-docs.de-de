---
title: Erstellen von C++-Projekten in Visual Studio | Microsoft Docs
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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="building-c-projects-in-visual-studio"></a>Erstellen von C++-Projekten in Visual Studio
In der integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) vom Visual Studio gibt es verschiedene Möglichkeiten für das Erstellen einer kompletten Lösung oder nur eines Projekts. Sie können außerdem Buildeinstellungen ändern und benutzerdefiniere Buildschritte angeben, um Ihren Entwicklungsprozess effizienter zu gestalten.  
  
 Erstellen eine Projektmappe, die in Visual Studio geöffnet und im ausgewählten **Projektmappen-Explorer**, können Sie:  
  
-   Wählen Sie in der Menüleiste **Erstellen**, **Projektmappe erstellen**.  
  
-   Oder geben Sie im **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für die Projektmappe, und wählen Sie dann **Projektmappe**.  
  
-   Oder drücken Sie F7. (Das ist das Standardtastenkürzel für die C-/C++-Entwicklungseinstellungen.)  
  
-   Oder klicken Sie in der [Befehlsfenster](/visualstudio/ide/reference/command-window) (Wählen Sie in der Menüleiste **Ansicht**, **Weitere Fenster**, **Befehlsfenster**), geben Sie `Build.BuildSolution`.  
  
-   Oder klicken Sie in der [Schnellstart](/visualstudio/ide/reference/quick-launch-environment-options-dialog-box) geben `build build solution`.  
  
 Um ein Projekt zu erstellen, die ausgewählt wurde **Projektmappen-Explorer**, können Sie:  
  
-   Wählen Sie in der Menüleiste **erstellen**, **erstellen \<Projektname >**.  
  
-   Oder geben Sie im **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für das Projekt, und wählen Sie dann **erstellen**.  
  
-   Oder, im Befehlsfenster (Wählen Sie in der Menüleiste **Ansicht**, **Weitere Fenster**, **Befehlsfenster**), geben Sie `Build.BuildOnlyProject`.  
  
-   Oder geben Sie in das schnellstartfeld `build project only build only <project name>`.  
  
 Wenn Sie eine Visual C++-Anwendung in Visual Studio erstellen, können Sie viele der Buildeinstellungen im Dialogfeld für die Eigenschaftenseiten des Projekts ändern. Informationen zum Festlegen von Projekteigenschaften, finden Sie unter [arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md).  
  
 Ein Beispiel zur Verwendung die IDE erstellen, erstellen und Debuggen eines C++-Projekts finden Sie unter [Exemplarische Vorgehensweise: Untersuchen der Visual Studio-IDE mit C++](/visualstudio/ide/getting-started-with-cpp-in-visual-studio). Ein Beispiel zur Verwendung die IDE zum Erstellen von C + c++ / CLR-Projekts finden Sie unter [Exemplarische Vorgehensweise: Kompilieren eines C++-Programms, die die CLR in Visual Studio](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md). Ein Beispiel zur Verwendung die IDE zum Erstellen einer Windows-Runtime-app, finden Sie unter [Erstellen Ihrer ersten Windows-Runtime-app mit C++](http://msdn.microsoft.com/library/windows/apps/hh974580.aspx).  
  
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
 [VC++-Verzeichnisse, Projekte, Optionen (Dialogfeld)](vcpp-directories-property-page.md)  
 (Gilt nur für MSBuild-Projekte) Erläutert, wie Sie den Suchpfad für ausführbare Dateien ändern, schließen Sie Dateien, Bibliotheksdateien und Quellcodedateien während eines Builds.  
  
 [Kompilieren und Erstellen](/visualstudio/ide/compiling-and-building-in-visual-studio)  
 Bietet Informationen zum Erstellen in Visual Studio.  
  
 [Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)  
 Bietet Links zu Themen, in denen das Erstellen von Programmen über die Befehlszeile oder die integrierte Entwicklungsumgebung von Visual Studio beschrieben sind.  
  
 [Referenz zur C/C++-Erstellung](../build/reference/c-cpp-building-reference.md)  
 Bietet Links zu einem Überblick für das Erstellen von Programmen C++, Compiler- und Linkeroptionen und zusätzlichen Buildtools.  
  
 [Aktualisieren von Projekten von früheren Versionen von Visual C++](../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md)  
 Enthält Links zu Themen über Probleme beim Upgrade von C++-Projekt auf neuere Versionen von das Compilertoolset.  
  
[Visual C++-Handbuch: Portieren und Aktualisieren](../porting/visual-cpp-porting-and-upgrading-guide.md)  
  Ausführliche Informationen zu C++-Anwendungen zu aktualisieren, die in früheren Versionen von Visual Studio erstellt wurden, sowie die Informationen zum Migrieren von Anwendungen, die mit anderen Tools als Visual Studio erstellt wurden.  
  
## <a name="see-also"></a>Siehe auch  
 [Universelle Windows-Apps (C++)](../windows/universal-windows-apps-cpp.md)