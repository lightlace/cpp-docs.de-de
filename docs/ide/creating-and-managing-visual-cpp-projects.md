---
title: Erstellen und Verwalten von Visual C++-Projekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 17b608ec68e0c4456b8789a4891da355ec732d2a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423623"
---
# <a name="creating-and-managing-msbuild-based-visual-c-projects"></a>Erstellen und Verwalten von MSBuild-basierten Visual C++-Projekten

MSBuild ist das native Buildsystem für Visual C++ und im Allgemeinen das beste Buildsystem für die Verwendung von UWP-Apps und Desktopanwendungen, die MFC- oder ATL-Bibliotheken verwenden. MSBuild ist eng in die Visual Studio-IDE und das Projektsystem integriert. Sie können MSBuild jedoch auch über die Befehlszeile verwenden. Ab Visual Studio 2017 unterstützt Visual C++ [CMake- und andere nicht MSBuild-Systeme mithilfe des Features „Ordner öffnen“](non-msbuild-projects.md).

Ein Projekt, das auf MSBuild basiert, enthält eine Projektdatei im XML-Format (VCXPROJ), die alle Dateien und Ressourcen angibt, die zum Kompilieren des Programms notwendig sind. Außerdem gibt sie andere Konfigurationseinstellungen an, wie z.B. die Zielplattform (x86, x64 oder ARM), und ob Sie eine Releaseversion oder Debugversion des Programms erstellen. Ein Projekt bzw. mehrere Projekte befinden sich in einer *Projektmappe*. Eine Projektmappe kann zum Beispiel mehrere Win32-DLL-Projekte und eine einzelne Win32-Konsolenanwendung enthalten, die diese DLLs verwendet. Wenn Sie das Projekt erstellen, verarbeitet die MSBuild-Engine die Projektdatei und erstellt die ausführbare Datei und/oder jede weitere benutzerdefinierte Ausgabe, die Sie angegeben haben.

Sie können Visual C++-Projekte erstellen, indem Sie **Datei > Neu > Projekt** auswählen und dabei sicherstellen, dass Visual C++ im linken Bereich ausgewählt ist, und dann aus der Liste der Projektvorlagen im mittleren Bereich wählen. Wenn Sie auf eine Vorlage klicken, wird in vielen Fällen ein Assistent angezeigt, mit dem Sie verschiedene Projekteigenschaften festlegen können, bevor das Projekt erstellt wird. Sie können diese Eigenschaften mithilfe der Eigenschaftenseiten des Projekts (**Projekt > Eigenschaften**) später anzeigen und ändern.

Sie können auch mit den folgenden Vorgehensweisen neue Projekte erstellen:

- Klicken Sie auf **Datei > Neu > Projekt aus vorhandenem Code**, und führen Sie die Anweisungen zum Hinzufügen von vorhandenen Quellcodedateien aus. Diese Option ist am besten für relativ kleine und einfache Projekte geeignet, etwa 25 Quellcodedateien mit wenigen oder ohne komplexe Abhängigkeiten.

- Wählen Sie die Makefile-Projektvorlage auf der Registerkarte „Allgemein“.

- Erstellen Sie ein leeres Projekt (auf der Registerkarte **Allgemein**), und fügen Sie manuell Quellcodedateien hinzu, indem Sie mit der rechten Maustaste auf den Projektknoten im Projektmappen-Explorer und auf **Hinzufügen > Vorhandenes Element** klicken.

- using the [Win32 Application Wizard](../windows/win32-application-wizard.md)

## <a name="in-this-section"></a>In diesem Abschnitt

[Visual C++-Projekttypen](../ide/visual-cpp-project-types.md)<br>
Beschreibt die MSBuild-basierten Projekttypen, die in Visual C++ verfügbar sind.

[Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)<br>
Beschreibt die Arten von Dateien, die mit verschiedenen MSBuild-Projekttypen verwendet werden.

[Erstellen von Desktopprojekten mit Anwendungs-Assistenten](../ide/creating-desktop-projects-by-using-application-wizards.md)<br>
Erläutert, wie Sie die Assistenten verwenden können, um Projekte mit C++ zu erstellen.

[Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)<br>
Erläutert, wie Sie Eigenschaftsseiten und Eigenschaftenblätter verwenden können, um Ihre Projekteinstellungen festzulegen.

[Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../ide/adding-functionality-with-code-wizards-cpp.md)<br>
Beschreibt, wie Sie Klassen, Methoden, Variablen und andere Elemente Ihrem Projekt hinzufügen können, um weitere Funktionen hinzuzufügen.

[Vorgehensweise: Organisieren von Projektausgabedateien für Builds](../ide/how-to-organize-project-output-files-for-builds.md)<br>
Beschreibt, wie Sie Projektausgabedateien organisieren.

## <a name="related-sections"></a>Verwandte Abschnitte

[Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)<br>
Bietet Links zu Themen, in denen das Erstellen von Programmen über die Befehlszeile oder die integrierte Entwicklungsumgebung von Visual Studio beschrieben sind.

## <a name="see-also"></a>Siehe auch

[Visual Studio SDK](https://msdn.microsoft.com/vstudio/extend)
