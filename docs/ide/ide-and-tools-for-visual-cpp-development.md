---
title: IDE und Tools für Visual C++-Entwicklung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, development tools
ms.assetid: 56eabafb-1956-4f0f-bec5-29b887763559
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3668fb438c2a0aa7fa14cff97f498a9becc67b36
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705399"
---
# <a name="ide-and-tools-for-visual-c-development"></a>IDE und Tools für Visual C++-Entwicklung

Als Teil der integrierten Visual Studio-Entwicklungsumgebung (IDE) verwendet Microsoft Visual C++ (MSVC) viele Fenster und Tools, die auch in zahlreichen anderen Sprachen verwendet werden. Viele davon, z.B. der **Projektmappen-Explorer**, der Code-Editor und der Debugger, sind unter [Visual Studio-IDE](/visualstudio/ide/visual-studio-ide) dokumentiert. Ein gemeinsam verwendetes Tool oder Fenster verfügt in C++ häufig über etwas andere Funktionen als für die .NET-Sprachen oder für JavaScript. Einige Fenster oder Tools sind nur in Visual Studio Pro oder Visual Studio Enterprise verfügbar.

Zusätzlich zu den gemeinsam verwendeten Tools in der integrierten Visual Studio-Entwicklungsumgebung verfügt MSVC über mehrere Tools, die speziell auf die Entwicklung von nativem Code ausgelegt sind. Diese Tools sind ebenfalls in diesem Artikel aufgeführt. Eine Liste der Tools, die in jeder Edition von Visual Studio verfügbar sind, finden Sie unter [Visual C++ Tools and Features in Visual Studio Editions (Tools und Features von Visual C++ in den Visual Studio-Editionen)](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md).

## <a name="creating-a-solution-and-projects"></a>Erstellen einer Projektmappe und von Projekten

Ein *Projekt* ist im Grunde eine Reihe von Quellcodedateien und Ressourcen wie Bilder oder Datendateien, aus denen eine ausführbare Datei erstellt wird. Visual Studio 2017 kann jedes Buildsystem und alle benutzerdefinierten Buildtools unterstützen, die Sie verwenden möchten, und bietet vollständige Unterstützung für IntelliSense, das Durchsuchen und das Debuggen:

- MSBuild ist das native Buildsystem für Visual Studio und häufig die beste Wahl für UWP-Apps (Universelle Windows-Plattform) oder ältere Windows-Desktopanwendungen, die MFC oder ATL verwenden. Weitere Informationen zu MSBuild-basierten C++-Projekten finden Sie unter [Creating and managing MSBuild-based projects (Erstellen und Verwalten von MSBuild-basierten Projekten)](creating-and-managing-visual-cpp-projects.md).
- CMake ist ein plattformübergreifendes Buildsystem, das in die Visual Studio-IDE integriert ist, wenn Sie die Workload „Desktopentwicklung mit C++“ installieren. Weitere Informationen finden Sie unter [CMake-Projekte in Visual C++](cmake-tools-for-visual-cpp.md).
- Alle anderen C++-Buildsysteme, einschließlich einer losen Dateisammlung, werden über das Feature „Ordner öffnen“ unterstützt. Sie erstellen einfache JSON-Dateien, um Ihr Buildprogramm aufzurufen und Debugsitzungen zu konfigurieren. Weitere Informationen finden Sie unter [Bring your C++ code to Visual Studio (Verwenden Ihres C++-Codes in Visual Studio)](https://blogs.msdn.microsoft.com/vcblog/2017/04/14/bring-your-cpp-code-to-visual-studio/).

### <a name="project-templates-msbuild"></a>Projektvorlagen (MSBuild)

Visual Studio enthält mehrere Vorlagen für MSBuild-basierte Projekte, die den Startercode und die Einstellungen für verschiedene grundlegende Programmtypen enthalten. Sie beginnen die Erstellung eines neuen Projekts aus einer Projektvorlage in der Regel, indem Sie auf **Datei** > **Neues Projekt** klicken. Anschließend fügen Sie diesem Projekt neue Quellcodedateien hinzu oder beginnen mit dem Schreiben von Code in den bereitgestellten Dateien. Spezielle Informationen zu C++-Projekten und -Projekt-Assistenten finden Sie unter [Creating and Managing Visual C++ Projects (Erstellen und Verwalten von C++-Projekten)](../ide/creating-and-managing-visual-cpp-projects.md).

### <a name="application-wizards-msbuild"></a>Anwendungs-Assistenten (MSBuild)

Visual Studio stellt Assistenten für einige MSBuild-Projekttypen bereit, wenn Sie auf **Datei** > **Neues Projekt** klicken. Ein Assistent führt Sie schrittweise durch den Prozess zum Erstellen eines neuen Projekts. Dies ist nützlich für Projekttypen, für die es viele Optionen und Einstellungen gibt. Weitere Informationen finden Sie unter [Creating Desktop Projects By Using Application Wizards (Erstellen von Desktopprojekten mithilfe von Anwendungs-Assistenten)](../ide/creating-desktop-projects-by-using-application-wizards.md).

## <a name="creating-user-interfaces-with-designers-msbuild"></a>Erstellen von Benutzeroberflächen mit Designern (MSBuild)

Wenn Ihr Programm über eine Benutzeroberfläche verfügt, besteht eine der ersten Aufgaben darin, sie mit Steuerelementen wie Schaltflächen, Listenfeldern usw. auszustatten. Visual Studio enthält eine visuelle Entwurfsoberfläche und eine Toolbox für jede Art von C++-Anwendung. Unabhängig davon, welche Art von Anwendung Sie erstellen, ist die zugrunde liegende Idee gleich: Sie ziehen ein Steuerelement aus dem Toolboxfenster und legen es in der Entwurfsoberfläche an der gewünschten Stelle ab. Im Hintergrund generiert Visual Studio die Ressourcen und den Code, die erforderlich sind, damit alles funktioniert. Anschließend schreiben Sie den Code, um die Steuerelemente mit Daten aufzufüllen oder um deren Aussehen und Verhalten anzupassen.

Weitere Informationen zum Entwerfen einer Benutzeroberfläche für eine UWP-App finden Sie unter [Design and UI (Design und Benutzeroberfläche)](https://developer.microsoft.com/en-us/windows/design).

Weitere Informationen zum Erstellen einer Benutzeroberfläche für eine MFC-Anwendung finden Sie unter [MFC Desktop Applications (MFC-Desktopanwendungen)](../mfc/mfc-desktop-applications.md). Weitere Informationen zu Win32-Windows-Programmen finden Sie unter [Windows Desktop Applications (Windows-Desktopanwendungen)](../windows/windows-desktop-applications-cpp.md).

## <a name="writing-and-editing-code"></a>Schreiben und Bearbeiten von Code

### <a name="semantic-colorization"></a>Semantische Farbgebung

Nachdem Sie ein Projekt erstellt haben, werden alle Projektdateien im Fenster des **Projektmappen-Explorers** angezeigt. Wenn Sie auf im **Projektmappen-Explorer** auf eine H- oder CPP-Datei klicken, wird die Datei im Code-Editor geöffnet. Der Code-Editor ist ein spezielles Textverarbeitungsprogramm für C++-Quellcode. Er versieht Sprachschlüsselwörter, Methoden- und Variablennamen sowie andere Elemente im Codes mit verschiedenen Farben, sodass der Code besser lesbar und einfacher zu verstehen ist.

### <a name="intellisense"></a>IntelliSense

Der Code-Editor unterstützt auch einige Features, die zusammen als IntelliSense bezeichnet werden. Wenn Sie den Mauszeiger über eine Methode halten, werden grundlegende Informationen dazu angezeigt. Wenn Sie einen Klassenvariablennamen und dann einen Punkt (.) oder einen Pfeil ( ->) eingeben, wird eine Liste von Instanzmembern dieser Klasse angezeigt. Wenn Sie einen Klassennamen und dann „::“ eingeben, wird eine Liste der statischen Member angezeigt. Wenn Sie die Eingabe eines Klassen- oder Methodennamens beginnen, bietet der Code-Editor Vorschläge an, um die Anweisung zu vervollständigen. Weitere Informationen finden Sie unter [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense).

### <a name="code-snippets"></a>Codeausschnitte

Sie können IntelliSense-Codeausschnitte verwenden, um häufig verwendete oder komplexe Codekonstrukte mit einer Tastenkombination zu generieren. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).

## <a name="navigating-code"></a>Navigieren im Code

Das Menü **Ansicht** bietet Ihnen Zugriff auf zahlreiche Fenster und Tools, mit denen Sie in Ihrem Code navigieren können. Ausführliche Informationen über diese Fenster finden Sie unter [Viewing the Structure of Code (Anzeigen der Codestruktur)](/visualstudio/ide/viewing-the-structure-of-code).

### <a name="solution-explorer"></a>Projektmappen-Explorer

Verwenden Sie in allen Editionen von Visual das Fenster **Projektmappen-Explorer** zum Navigieren zwischen den Dateien in einem Projekt. Erweitern Sie das Symbol für eine H- oder CPP-Datei, um die Klassen in der Datei anzuzeigen. Erweitern Sie eine Klasse, um ihre Member anzuzeigen. Doppelklicken Sie auf ein Member, um zu seiner Definition oder Implementierung in der Datei zu gelangen.

### <a name="class-view-and-code-definition-window"></a>Die Fenster „Klassenansicht“ und „Codedefinition“

Im Fenster **Klassenansicht** werden die Namespaces und Klassen in allen Dateien angezeigt, einschließlich der partiellen Klassen. Sie können jeden Namespace oder jede Klasse erweitern, um deren Member anzuzeigen. Sie können dann auf ein Member doppelklicken, um an seine Stelle in der Quelldatei zu navigieren. Im geöffneten **Codedefinitionsfenster** können Sie die Definition oder Implementierung des Typs anzeigen, wenn Sie ihn in der **Klassenansicht** auswählen.

### <a name="object-browser"></a>Objektkatalog

Verwenden Sie den **Objektkatalog**, um Typinformationen in Komponenten für Windows-Runtime (WINMD-Dateien), .NET-Assemblys und COM-Typbibliotheken anzuzeigen. Der Objektkatalog wird nicht zusammen mit Win32-DLLs verwendet.

### <a name="go-to-definitiondeclaration"></a>Gehe zu Definition/Deklaration

Wenn Sie bei einem API-Namen oder einer Membervariablen die Taste F12 drücken, gelangen Sie zu der jeweiligen Definition. Wenn sich die Definition in einer WINMD-Datei befindet (bei einer UWP- oder Windows 8.x-Store-App), werden die Typinformationen im Objektkatalog angezeigt. Sie können die Optionen **Gehe zu Definition** oder **Gehe zu Deklaration** verwenden, indem Sie mit der rechten Maustaste auf den Namen der Variablen oder des Typs klicken und die Option im Kontextmenü auswählen.

### <a name="find-all-references"></a>Alle Verweise suchen

Klicken Sie in einer Quellcodedatei, wenn sich der Mauszeiger auf dem Namen eines Typs, einer Methode oder Variablen befindet, mit der rechten Maustaste, und wählen Sie **Alle Verweise suchen** aus, um eine Liste mit allen Stellen in der Datei, dem Projekt oder einer Projektmappe anzuzeigen, an denen der Typ verwendet wird. **Alle Verweise suchen** ist intelligent und gibt auch dann nur Instanzen derselben identischen Variable zurück, wenn andere Variablen in einem anderen Bereich den gleichen Namen haben.

## <a name="add-and-edit-resources--msbuild"></a>Hinzufügen und Bearbeiten von Ressourcen (MSBuild)

Der Begriff *Ressource* im Kontext eines Visual Studio-Desktopprojekts umfasst Elemente wie Dialogfelder, Symbole, lokalisierbaren Zeichenfolgen, Begrüßungsbildschirme, Datenbankverbindungszeichenfolgen oder sonstigen Daten, die Sie in die ausführbare Datei einbeziehen möchten.

Weitere Informationen zum Hinzufügen und Bearbeiten von Ressourcen in nativen Desktop-C++-Projekten finden Sie unter [Working with Resource Files (Arbeiten mit Ressourcendateien)](../windows/working-with-resource-files.md).

## <a name="build-compile-and-link"></a>Erstellen (Kompilieren und Verknüpfen)

Klicken Sie in der Menüleiste auf **Erstellen** > **Projektmappe erstellen**, oder drücken Sie die Tastenkombination STRG+UMSCHALT+B, um ein Projekt zu kompilieren und zu verknüpfen. Visual Studio verwendet [MSBuild](/visualstudio/msbuild/msbuild1) oder CMake bzw. die Buildumgebung, die Sie über **Ordner öffnen** einrichten, um ausführbaren Code zu erstellen. Für MSBuild-Projekte legen Sie die allgemeinen Buildoptionen unter **Extras** > **Optionen** > **Projekte und Projektmappen** fest. Sie können Eigenschaften für bestimmte Projekte unter **Projekt** > **Eigenschaften** festlegen. Buildfehler und Warnungen werden in der Fehlerliste gemeldet (STRG+\\, E). Nicht-MSBuild-Projekte werden mit JSON-Dateien konfiguriert, die Sie im Projektmappen-Explorer erstellen. Unabhängig von Ihrem Buildsystem zeigt das **Ausgabefenster** (ALT+2) Informationen über den Buildprozess an. Weitere Informationen zu MSBuild-Konfigurationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../ide/working-with-project-properties.md) und [Building C++ Projects in Visual Studio (Erstellen von C++-Projekten in Visual Studio)](../ide/building-cpp-projects-in-visual-studio.md).

Sie können auch den Compiler (cl.exe) und viele andere buildbezogene, eigenständige Tools (z.B. NMAKE und LIB) direkt über die Befehlszeile verwenden. Weitere Informationen finden Sie unter [Build C/C++ code on the command line (Erstellen von C- oder C++-Code über die Befehlszeile)](../build/building-on-the-command-line.md) and [C/C++ Building Reference (Referenz zur C/C++-Erstellung)](../build/reference/c-cpp-building-reference.md).

## <a name="test"></a>Test

Visual Studio enthält einen Komponententest-Framework für systemeigenen C++- und C++/CLI-Code. Weitere Informationen finden Sie unter [Überprüfen von Code mit Komponententests](/visualstudio/test/unit-test-your-code) und [Schreiben von Komponententests für C/C++ mit dem Microsoft-Komponententest-Framework für C++](/visualstudio/test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp).

## <a name="debug"></a>Debug

Sie können das Programm debuggen, indem Sie **F5** drücken, wenn die Projektkonfiguration für das Debuggen festgelegt ist. Während des Debuggens können Sie mit **F9** Haltepunkte setzen, mit **F10** den Code schrittweise durchlaufen, die Werte angegebener Variablen oder Register anzeigen und in einigen Fällen sogar Änderungen am Code vornehmen und mit dem Debuggen fortfahren, ohne neu kompilieren zu müssen. Weitere Informationen finden Sie unter [Debuggen in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).

## <a name="deploy-completed-applications"></a>Bereitstellen fertiger Anwendungen

Sie stellen eine UWP-App über den Microsoft Store für Kunden bereit, indem Sie die Menüoption **Projekt** > **Store** verwenden. Die Bereitstellung von CRT wird automatisch im Hintergrund durchgeführt. Weitere Informationen finden Sie unter [Veröffentlichen von Windows-Apps](http://go.microsoft.com/fwlink/p/?LinkId=262280).

Wenn Sie eine systemeigene C++-Desktopanwendung auf einem anderen Computer bereitstellen, müssen Sie die Anwendung selbst sowie alle Bibliotheksdateien, von denen die Anwendung abhängt, installieren. Es gibt drei Möglichkeiten zum Bereitstellen der universellen C++-Runtime (UCRT): die zentrale Bereitstellung, die lokale Bereitstellung oder die statische Verknüpfung. Weitere Informationen finden Sie unter [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md).

Weitere Informationen zum Bereitstellen eines C++/CLI-Programms finden Sie im [Deployment Guide for Developers (Bereitstellungshandbuch für Entwickler)](/dotnet/framework/deployment/deployment-guide-for-developers).

## <a name="related-articles"></a>Verwandte Artikel

|||
|-|-|
|[Visual C++-Tools und -Features in Visual Studio-Editionen](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)|Gibt an, welche Features in den verschiedenen Editionen von Visual Studio verfügbar sind.|
|[Creating and managing MSBuild-based projects (Erstellen und Verwalten von MSBuild-basierten Projekten)](../ide/creating-and-managing-visual-cpp-projects.md)|Bietet eine Übersicht über MSBuild-basierte C++-Projekte in Visual Studio und Links zu anderen Artikeln, die beschreiben, wie diese Projekte erstellt und verwaltet werden.|
|[CMake-Projekte in Visual C++](cmake-tools-for-visual-cpp.md)|Beschreibt, wie CMake-Projekte oder andere Nicht-MSBuild-Projekte in Visual C++ erstellt werden.|
|[Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)|Beschreibt das Erstellen von C++-Projekten.|
|[Deploying Desktop Applications (Bereitstellen von Desktopanwendungen)](../ide/deploying-native-desktop-applications-visual-cpp.md)|Bietet einen Überblick über die Bereitstellung von C++-Apps sowie Links zu anderen Artikeln, die die Bereitstellung im Detail beschreiben.|
|[Visual C++-Handbuch: Portieren und Aktualisieren](../porting/visual-cpp-porting-and-upgrading-guide.md)|Weitere Informationen zum Upgraden von C++-Anwendungen, die in früheren Versionen von Visual Studio erstellt wurden sowie zur Migration von Anwendungen, die mithilfe von anderen Tools als Visual Studio erstellt wurden.|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Beschreibt die wichtigsten Features von Visual C++ in Visual Studio und verlinkt zum Rest der Visual C++-Dokumentation.|
