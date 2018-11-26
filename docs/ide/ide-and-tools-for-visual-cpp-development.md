---
title: IDE und Tools für Visual C++-Entwicklung
description: Die Visual Studio-IDE unterstützt C++-Entwicklung unter Windows, Linux, Android und iOS mit einem Code-Editor, Debugger, Testframeworks, statischen Analysetools und weiteren Programmiertools.
ms.date: 11/18/2018
helpviewer_keywords:
- Visual C++, development tools
ms.assetid: 56eabafb-1956-4f0f-bec5-29b887763559
ms.openlocfilehash: a5dd7f681d05d36215c4086165165122a05be23c
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693957"
---
# <a name="ide-and-compiler-tools-for-visual-c-development"></a>IDE und Compilertools für die Visual C++-Entwicklung

Als Teil der integrierten Visual Studio-Entwicklungsumgebung (IDE) verwendet Microsoft Visual C++ (MSVC) viele Fenster und Tools, die auch in zahlreichen anderen Sprachen verwendet werden. Viele davon, z.B. der **Projektmappen-Explorer**, der Code-Editor und der Debugger, sind unter [Visual Studio-IDE](/visualstudio/ide/visual-studio-ide) dokumentiert. Ein gemeinsam verwendetes Tool oder Fenster verfügt in C++ häufig über etwas andere Funktionen als für die .NET-Sprachen oder für JavaScript. Einige Fenster oder Tools sind nur in den Editionen Visual Studio Professional oder Visual Studio Enterprise verfügbar.

Zusätzlich zu den gemeinsam verwendeten Tools in der integrierten Visual Studio-Entwicklungsumgebung verfügt MSVC über mehrere Tools, die speziell auf die Entwicklung von nativem Code ausgelegt sind. Diese Tools sind ebenfalls in diesem Artikel aufgeführt. Eine Liste der Tools, die in jeder Edition von Visual Studio verfügbar sind, finden Sie unter [Visual C++ Tools and Features in Visual Studio Editions (Tools und Features von Visual C++ in den Visual Studio-Editionen)](visual-cpp-tools-and-features-in-visual-studio-editions.md).

## <a name="create-projects"></a>Erstellen von Projekten

Ein *Projekt* ist im Grunde eine Reihe von Quellcodedateien und Ressourcen wie Bilder oder Datendateien, aus denen eine ausführbare Datei erstellt wird.

Visual Studio 2015 unterstützt MSBuild-Projekte. Sie können Visual Studio-Erweiterungen für andere Buildsysteme wie Qt oder CMake herunterladen.

Visual Studio 2017 unterstützt alle Buildsysteme und benutzerdefinierten Buildtools, die Sie verwenden möchten, und bietet vollständige Unterstützung für IntelliSense, das Durchsuchen und das Debuggen:

- Bei **MSBuild** handelt es sich um das native Buildsystem für Visual Studio. Wenn Sie im Hauptmenü **Datei** > **Neu** > **Projekt** auswählen, sehen Sie viele Arten von MSBuild-*Projektvorlagen*, die Sie beim schnellen Einstieg in die Entwicklung verschiedener Arten von C++-Anwendungen unterstützen.

   ![Projektvorlagen](media/vs2017-new-project.png "Visual Studio 2017-Dialogfeld „Neues Projekt“")

   Im Allgemeinen sollten Sie diese Vorlagen für neue Projekte verwenden, sofern kein bestimmter Grund vorliegt, CMake oder ein anderes Projektsystem zu verwenden. Einige Projekte verfügen über einen *Assistenten*, der Sie schrittweise durch den Prozess zum Erstellen eines neuen Projekts führt. Weitere Informationen finden Sie unter [Creating and managing MSBuild-based projects](creating-and-managing-visual-cpp-projects.md) (Erstellen und Verwalten von MSBuild-basierten Projekten).

- **CMake** ist ein plattformübergreifendes Buildsystem, das in die Visual Studio-IDE integriert ist, wenn Sie die Workload „Desktopentwicklung mit C++“ installieren. Weitere Informationen finden Sie unter [CMake-Projekte in Visual C++](cmake-tools-for-visual-cpp.md).
- Alle anderen C++-Buildsysteme, einschließlich einer losen Dateisammlung, werden über das Feature **Ordner öffnen** unterstützt. Sie erstellen einfache JSON-Dateien, um Ihr Buildprogramm aufzurufen und Debugsitzungen zu konfigurieren. Weitere Informationen finden Sie unter [Ordner öffnen-Projekte in Visual C++](non-msbuild-projects.md).

## <a name="add-to-source-control"></a>Zur Quellcodeverwaltung hinzufügen

Mithilfe von Quellcodeverwaltung können Sie die Arbeit mehrerer Entwickler koordinieren, im Bearbeitungsprozess stehende Arbeit von Produktionscode trennen und Ihren Quellcode sichern. Visual Studio unterstützt Git und [Team Foundation Version Control \(TFVC\)](/azure/devops/repos/tfvc/) über sein Fenster **Team Explorer**.

![Team Explorer](media/vs2017-team-explorer.png "Visual Studio 2017 Team Explorer")

Weitere Informationen zur Git-Integration mit Repositorys in Azure finden Sie unter [Share your code with Visual Studio 2017 and Azure Repos Git](/azure/devops/repos/git/share-your-code-in-git-vs-2017) (Teilen Ihres Codes mit Visual Studio 2017 und Azure Repos Git). Informationen zur Git-Integration mit GitHub finden Sie unter [GitHub Extension for Visual Studio (GitHub-Erweiterung für Visual Studio)](https://visualstudio.github.com/).

## <a name="create-user-interfaces-with-designers"></a>Erstellen von Benutzeroberflächen mit Designern

Wenn Ihr Programm über eine Benutzeroberfläche verfügt, können Sie einen Designer verwenden, um sie schnell mit Steuerelementen wie Schaltflächen, Listenfeldern usw. auszustatten. Wenn Sie ein Steuerelement aus dem Toolbox-Fenster ziehen und es auf der Entwurfsoberfläche ablegen, erstellt Visual Studio die erforderlichen Ressourcen und den Code, damit es funktioniert. Anschließend schreiben Sie den Code, um das Aussehen und Verhalten anzupassen.

![Designer und Toolbox](media/vs2017-toolbox-designer.png "Toolbox und Designer von Visual Studio 2017")

Weitere Informationen zum Entwerfen einer Benutzeroberfläche für eine UWP-App finden Sie unter [Design and UI (Design und Benutzeroberfläche)](https://developer.microsoft.com/windows/design).

Weitere Informationen zum Erstellen einer Benutzeroberfläche für eine MFC-Anwendung finden Sie unter [MFC Desktop Applications (MFC-Desktopanwendungen)](../mfc/mfc-desktop-applications.md). Weitere Informationen zu Win32-Windows-Programmen finden Sie unter [Windows Desktop Applications (Windows-Desktopanwendungen)](../windows/windows-desktop-applications-cpp.md).

## <a name="write-code"></a>Schreiben von Code

Nachdem Sie ein Projekt erstellt haben, werden alle Projektdateien im Fenster des **Projektmappen-Explorers** angezeigt. (Eine *Projektmappe* ist ein logischer Container für ein oder mehrere verwandte Projekte.) Wenn Sie auf im **Projektmappen-Explorer** auf eine H- oder CPP-Datei klicken, wird die Datei im Code-Editor geöffnet.

![Projektmappen-Explorer und Code-Editor](media/vs2017-solution-explorer-code-editor.png "Projektmappen-Explorer und Code-Editor von Visual Studio 2017")

Der Code-Editor ist ein spezielles Textverarbeitungsprogramm für C++-Quellcode. Er versieht Sprachschlüsselwörter, Methoden- und Variablennamen sowie andere Elemente im Codes mit verschiedenen Farben, sodass der Code besser lesbar und einfacher zu verstehen ist.

Weitere Informationen finden Sie unter [Schreiben und Umgestalten von Code](writing-and-refactoring-code-cpp.md).

## <a name="add-and-edit-resources"></a>Hinzufügen und Bearbeiten von Ressourcen

Der Begriff *Ressource* umfasst Elemente wie Dialogfelder, Symbole, Bilder, lokalisierbare Zeichenfolgen, Begrüßungsbildschirme, Datenbankverbindungszeichenfolgen oder sonstige Daten, die Sie in die ausführbare Datei einbeziehen möchten.

Weitere Informationen zum Hinzufügen und Bearbeiten von Ressourcen in nativen Desktop-C++-Projekten finden Sie unter [Working with Resource Files (Arbeiten mit Ressourcendateien)](../windows/working-with-resource-files.md).

## <a name="build-compile-and-link"></a>Erstellen (Kompilieren und Verknüpfen)

Klicken Sie in der Menüleiste auf **Erstellen** > **Projektmappe erstellen**, oder drücken Sie die Tastenkombination STRG+UMSCHALT+B, um ein Projekt zu kompilieren und zu verknüpfen. Buildfehler und Warnungen werden in der Fehlerliste gemeldet (STRG+\\, E). Das **Ausgabefenster** (ALT+2) zeigt Informationen über den Buildprozess an.

![Ausgabefenster und Fehlerliste](media/vs2017-output-error-list.png "Visual Studio 2017-Ausgabefenster und Fehlerliste") Weitere Informationen zu MSBuild-Konfigurationen finden Sie unter [Working with Project Properties](working-with-project-properties.md) (Arbeiten mit Projekteigenschaften) und [Building C++ Projects in Visual Studio](building-cpp-projects-in-visual-studio.md) (Erstellen von C++-Projekten in Visual Studio).

Sie können auch den Compiler (cl.exe) und viele andere buildbezogene, eigenständige Tools (z.B. NMAKE und LIB) direkt über die Befehlszeile verwenden. Weitere Informationen finden Sie unter [Build C/C++ code on the command line (Erstellen von C- oder C++-Code über die Befehlszeile)](../build/building-on-the-command-line.md) and [C/C++ Building Reference (Referenz zur C/C++-Erstellung)](../build/reference/c-cpp-building-reference.md).

## <a name="debug"></a>Debug

Debuggen Sie durch Drücken von **F5**. Die Ausführung hält bei allen Haltepunkten an, die Sie gesetzt haben. Sie können den Code auch jeweils zeilenweise durchlaufen, die Werte von Variablen oder Registern anzeigen und in einigen Fällen sogar Änderungen am Code vornehmen und das Debuggen fortsetzen, ohne neu zu kompilieren. Die folgende Abbildung zeigt eine Debugsitzung mit bei einem Haltepunkt angehaltener Ausführung. Die Werte der Datenstrukturelemente sind im Fenster **Überwachen** sichtbar.

![Debugsitzung](media/vs2017-debug-watch.png "Visual Studio 2017-Debugsitzung")

Weitere Informationen finden Sie unter [Debuggen in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).

## <a name="test"></a>Test

Visual Studio enthält Komponententest-Frameworks für systemeigenen C++- und C++/CLI-Code. Boost.Test, Google Test und CTest werden ebenfalls unterstützt. Führen Sie Ihre Tests im Fenster **Test-Explorer** aus:

![Test-Explorer](media/cpp-test-explorer-passed.png "Visual Studio 2017 Test-Explorer")

Weitere Informationen finden Sie unter [Verifying Code by Using Unit Tests](/visualstudio/test/unit-test-your-code) (Überprüfen von Code mithilfe von Komponententests) und [Write unit tests for C/C++ in Visual Studio](/visualstudio/test/writing-unit-tests-for-c-cpp) (Schreiben von Komponententests für C/C++ in Visual Studio).

## <a name="analyze"></a>Analysieren

Visual Studio enthält statische Codeanalysetools, die potenzielle Probleme in Ihrem Quellcode erkennen können. Diese Tools beinhalten eine Implementierung der [C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md)-Regelüberprüfung. Weitere Informationen finden Sie unter [Code analysis for C/C++ overview (Übersicht: Codeanalyse für C/C++)](/visualstudio/code-quality/code-analysis-for-c-cpp-overview).

## <a name="deploy-completed-applications"></a>Bereitstellen fertiger Anwendungen

Sowohl herkömmliche Desktopanwendungen als auch UWP-Apps können über den Microsoft Store bei Kunden bereitgestellt werden. Die Bereitstellung von CRT wird automatisch im Hintergrund durchgeführt. Weitere Informationen finden Sie unter [Veröffentlichen von Windows-Apps und -Spielen](/windows/uwp/publish/).

Auch die Bereitstellung von nativen C++-Desktops auf anderen Computern ist möglich. Weitere Informationen finden Sie unter [Bereitstellen von Desktopanwendungen](deploying-native-desktop-applications-visual-cpp.md).

Weitere Informationen zum Bereitstellen eines C++/CLI-Programms finden Sie im [Deployment Guide for Developers (Bereitstellungshandbuch für Entwickler)](/dotnet/framework/deployment/deployment-guide-for-developers).

## <a name="in-this-section"></a>In diesem Abschnitt

|||
|-|-|
|[Schreiben und Refactoring von Code (C++)](writing-and-refactoring-code-cpp.md)| So verwenden Sie den C++-Code-Editor zum Schreiben und Umgestalten von und für die Navigation im Code|
|[Visual C++-Tools und -Features in Visual Studio-Editionen](visual-cpp-tools-and-features-in-visual-studio-editions.md)|Gibt an, welche Features in den verschiedenen Editionen von Visual Studio verfügbar sind.|
|[C++ Open Folder projects in Visual Studio (Verwenden von „Ordner öffnen“-Projekten in C++ mit Visual Studio)](non-msbuild-projects.md)|So verwenden Sie ein beliebiges C++-Buildsystem über Visual Studio|
|[CMake-Projekte in Visual C++](cmake-tools-for-visual-cpp.md)|So erstellen Sie CMake-Projekte in Visual Studio|
|[Creating and managing MSBuild-based projects (Erstellen und Verwalten von MSBuild-basierten Projekten)](creating-and-managing-visual-cpp-projects.md)|Bietet eine Übersicht über MSBuild-basierte C++-Projekte in Visual Studio und Links zu anderen Artikeln, die beschreiben, wie diese Projekte erstellt und verwaltet werden.|
|[Deploying Desktop Applications (Bereitstellen von Desktopanwendungen)](deploying-native-desktop-applications-visual-cpp.md)|Bietet einen Überblick über die Bereitstellung von C++-Apps sowie Links zu anderen Artikeln, die die Bereitstellung im Detail beschreiben.|
|[Hinzufügen neuer Funktionen mit Code-Assistenten](adding-functionality-with-code-wizards-cpp.md)| So fügen Sie mithilfe von Assistenten Klassen, Dateien oder Benutzeroberflächenelemente zu einem Projekt hinzu|
|[XML-Dokumentation (Visual C++)](xml-documentation-visual-cpp.md)| So erstellen Sie eine XML-Dokumentation für Ihre APIs|
|[Erstellen von C++-Projekten in Visual Studio](building-cpp-projects-in-visual-studio.md)|So verwenden Sie die Visual Studio-IDE zum Erstellen von Projekten|

## <a name="related-articles"></a>Verwandte Artikel

|||
|-|-|
|[Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)|Ausführliche Informationen zum Erstellen von C++-Projekten|
|[Visual C++-Handbuch: Portieren und Aktualisieren](../porting/visual-cpp-porting-and-upgrading-guide.md)|Weitere Informationen zum Upgraden von C++-Anwendungen, die in früheren Versionen von Visual Studio erstellt wurden sowie zur Migration von Anwendungen, die mithilfe von anderen Tools als Visual Studio erstellt wurden.|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Beschreibt die wichtigsten Features von Visual C++ in Visual Studio und verlinkt zum Rest der Visual C++-Dokumentation.|
