---
title: Erstellen und Verwalten von Visual C++-Projekten | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vcprojects
- creatingmanagingVC
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, creating
- Visual C++ projects, creating
- projects [C++], creating
- Visual C++ projects
- ATL projects
ms.assetid: 11003cd8-9046-4630-a189-a32bf3b88047
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c38f4c75a41de8b2f2b494941c6a52b1ff46fa4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-and-managing-msbuild-based-visual-c-projects"></a>Erstellen und Verwalten von MSBuild-basierte Visual C++-Projekten
MSBuild ist das native Buildsystem für Visual C++ und im Allgemeinen, dass die beste Buildsystem für uwp-apps als auch Desktop-Anwendungen, die MFC oder ATL-Bibliotheken verwenden. MSBuild ist eng mit dem Visual Studio-IDE und Projektsystem integriert, aber Sie können Sie auch über die Befehlszeile verwenden. Ab Visual Studio 2017 können Visual C++ unterstützt [CMake und anderen Systemen nicht MSBuild über das Feature Open Folder](non-msbuild-projects.md).

Ein MSBuild-basiertes Projekt enthält eine Projektdatei im XML-Format (.vcxproj), der angibt, die Dateien und Ressourcen benötigt zum Kompilieren des Programms sowie andere Konfigurationseinstellungen, z. B. die Zielplattform (x 86, X64 oder ARM) und gibt an, ob Sie erstellen eine Release-Version oder Debugversion des Programms. Ein Projekt bzw. mehrere Projekte befinden sich in einer *Projektmappe*. Eine Projektmappe kann zum Beispiel mehrere Win32-DLL-Projekte und eine einzelne Win32-Konsolenanwendung enthalten, die diese DLLs verwendet. Wenn Sie das Projekt erstellen, verarbeitet das MSBuild-Modul die Projektdatei und erstellt die ausführbare Datei und/oder jede weitere benutzerdefinierte Ausgabe, die Sie angegeben haben.

Sie können Visual C++-Projekte erstellen, indem Sie auswählen **Datei &#124; Neue &#124; Projekt**, sicherstellen, dass Visual C++ im linken Bereich ausgewählt ist, und klicken Sie dann aus der Liste der Projektvorlagen im mittleren Bereich auswählen. Wenn Sie in einer Vorlage klicken, wird in vielen Fällen ein Assistent angezeigt, mit dem Sie verschiedene Projekteigenschaften festlegen, bevor das Projekt erstellt wird. Sie können Eigenschaften anzeigen und ändern diese später mithilfe der Eigenschaftenseiten des Projekts (**Projekt &#124; Eigenschaften**).  
  
 Sie können auch neue Projekte erstellen:  
  
-   Auswählen von **Datei &#124; Neue &#124; Projekt aus vorhandenem Code** und den Anweisungen zum Hinzufügen von vorhandenen Quellcodedateien folgen. Diese Option ist am besten für relativ kleine und einfache Projekte geeignet, etwa 25 Quellcodedateien mit wenigen oder ohne komplexe Abhängigkeiten.  
  
-   Wählen Sie die Makefile-Projektvorlage auf der Registerkarte „Allgemein“.  
  
-   Erstellen ein leeres Projekt (unter der **allgemeine** Registerkarte ") und fügen Sie manuell Quellcodedateien, indem Sie mit der rechten Maustaste auf den Projektknoten im Projektmappen-Explorer und **hinzufügen &#124; Vorhandenes Element**.  
  
-   using the [Win32 Application Wizard](../windows/win32-application-wizard.md)  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Visual C++-Projekttypen](../ide/visual-cpp-project-types.md)  
 Beschreibt die MSBuild-basiertes Projekt-Typen, die in Visual C++ verfügbar sind.  
  
 [Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)  
 Beschreibt die Arten von Dateien, die mit verschiedenen MSBuild-Projekttypen verwendet werden.  
  
 [Erstellen von Desktopprojekten mit Anwendungs-Assistenten](../ide/creating-desktop-projects-by-using-application-wizards.md)  
 Erläutert, wie Sie die Assistenten verwenden können, um Projekte mit C++ zu erstellen.  
  
 [Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)  
 Erläutert, wie Sie Eigenschaftsseiten und Eigenschaftenblätter verwenden können, um Ihre Projekteinstellungen festzulegen.  
  
 [Hinzufügen neuer Funktionen mit Code-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md)  
 Beschreibt, wie Sie Klassen, Methoden, Variablen und andere Elemente Ihrem Projekt hinzufügen können, um weitere Funktionen hinzuzufügen.  
  
 [Vorgehensweise: Organisieren von Projektausgabedateien für Builds](../ide/how-to-organize-project-output-files-for-builds.md)  
 Beschreibt, wie Sie Projektausgabedateien organisieren.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)  
 Bietet Links zu Themen, in denen das Erstellen von Programmen über die Befehlszeile oder die integrierte Entwicklungsumgebung von Visual Studio beschrieben sind.  
  
 [Visual C++-Referenz](http://msdn.microsoft.com/en-us/1ba03b5c-8229-4f63-b08c-6c12141d6ab1)  
 Enthält Links zu Themen, in denen die C- und C++-Sprachreferenzen, die im Lieferumfang von Visual C++ enthaltenen Bibliotheken, das Visual C++-Erweiterbarkeitsobjektmodell und der Microsoft Macro Assembler (MASM) beschrieben werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Studio SDK](http://msdn.microsoft.com/vstudio/extend)
