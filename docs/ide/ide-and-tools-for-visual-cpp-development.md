---
title: "IDE und Tools für Visual C++-Entwicklung | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, development tools
ms.assetid: 56eabafb-1956-4f0f-bec5-29b887763559
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4b6ff3f709e5db16f06569ab3406cfef44cabf11
ms.sourcegitcommit: a5a69d2dc3513261e9e28320e4e067aaf40d2ef2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2018
---
# <a name="ide-and-tools-for-visual-c-development"></a>IDE und Tools für Visual C++-Entwicklung

Als Teil der Visual Studio integrierten Entwicklung Umgebung (IDE) verwendet Microsoft Visual C++ (MSVC) auf, viele Fenster und Tools, die auch in zahlreichen anderen Sprachen. Viele davon, wie z. B. **Projektmappen-Explorer**, Code-Editor, und der Debugger, sind unter dokumentiert [Visual Studio-IDE](/visualstudio/ide/visual-studio-ide). Ein gemeinsam verwendetes Tool oder Fenster verfügt in C++ häufig über etwas andere Funktionen als für die .NET-Sprachen oder für JavaScript. Einige Fenster oder Tools sind nur in Visual Studio Pro oder Visual Studio Enterprise verfügbar.

Zusätzlich zu den gemeinsam verwendeten Tools in Visual Studio-IDE verfügt MSVC mehrere Tools, die speziell für die Entwicklung von systemeigenem Code. Diese Tools sind ebenfalls in diesem Artikel aufgeführt. Eine Liste der Tools in jeder Edition von Visual Studio verfügbar sind, finden Sie unter [Visual C++-Tools und Funktionen in Visual Studio-Editionen](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md).

## <a name="creating-a-solution-and-projects"></a>Erstellen einer Projektmappe und von Projekten

Ein *Projekt* ist im Grunde eine Reihe von Quellcodedateien und Ressourcen wie Bilder oder Datendateien, die in eine ausführbare Datei erstellt werden. Visual Studio-2017 unterstützen alle Buildsystem oder benutzerdefinierten Buildtools, die Sie mit vollständiger Unterstützung für Intellisense, durchsuchen und Debuggen verwenden möchten:

- MSBuild ist das native Buildsystem für Visual Studio und ist häufig die beste Wahl für apps der universellen Windows-Plattform (UWP) oder ältere Windows-desktopanwendungen, die MFC oder ATL verwenden Weitere Informationen zu MSBuild-basierte C++-Projekten finden Sie unter [erstellen und Verwalten von MSBuild-basierte Projekte](creating-and-managing-visual-cpp-projects.md).
- CMake ist eine plattformübergreifende Buildsystem, die bei der Installation der Desktopentwicklung Arbeitslast C++ in Visual Studio-IDE integriert ist. Weitere Informationen finden Sie unter [CMake-Projekte in Visual C++](cmake-tools-for-visual-cpp.md).
- Alle anderen C++-Buildsystems, einschließlich einer losen Auflistung von Dateien, wird über das Feature Open Folder unterstützt. Sie erstellen einfache JSON-Dateien zum Aufrufen des Programms erstellen und Konfigurieren von Debugsitzungen. Weitere Informationen finden Sie unter [bringen Sie C++-Code in Visual Studio](https://blogs.msdn.microsoft.com/vcblog/2017/04/14/bring-your-cpp-code-to-visual-studio/).

### <a name="project-templates-msbuild"></a>Projektvorlagen (MSBuild)

Visual Studio enthält mehrere Vorlagen zum MSBuild-basierte Projekte; Diese Vorlagen enthalten startercode und die Einstellungen für verschiedene grundlegende Programmtypen benötigt. In der Regel beginnen Sie damit auszuwählen **Datei** > **neues Projekt** um ein Projekt von einer Vorlage zu erstellen, fügen Sie dann neue Quellcodedateien zu diesem Projekt, oder in den bereitgestellten Dateien codieren beginnen. Informationen zu C++-Projekten und Projektassistenten finden Sie unter [erstellen und Verwalten von Visual C++-Projekte](../ide/creating-and-managing-visual-cpp-projects.md).

### <a name="application-wizards-msbuild"></a>Anwendungsassistenten (MSBuild)

Visual Studio enthält Assistenten für einige Projekttypen MSBuild, bei der Auswahl **Datei** > **neues Projekt**. Ein Assistent führt Sie schrittweise durch den Prozess zum Erstellen eines neuen Projekts. Dies ist nützlich für Projekttypen, für die es viele Optionen und Einstellungen gibt. Weitere Informationen finden Sie unter [erstellen Desktop-Projekten mithilfe von Anwendungsassistenten](../ide/creating-desktop-projects-by-using-application-wizards.md).

## <a name="creating-user-interfaces-with-designers-msbuild"></a>Erstellen von Benutzeroberflächen mit Designern (MSBuild)

Wenn Ihr Programm über eine Benutzeroberfläche verfügt, besteht eine der ersten Aufgaben darin, sie mit Steuerelementen wie Schaltflächen, Listenfeldern usw. auszustatten. Visual Studio enthält eine visuelle Entwurfsoberfläche und eine Toolbox für jede Art von C++-Anwendung. Unabhängig davon, welche Art von Anwendung Sie erstellen, ist die zugrunde liegende Idee gleich: Sie ziehen ein Steuerelement aus dem Toolboxfenster und legen es in der Entwurfsoberfläche an der gewünschten Stelle ab. Im Hintergrund generiert Visual Studio die Ressourcen und den Code, die erforderlich sind, damit alles funktioniert. Klicken Sie dann schreiben Sie den Code, um die Steuerelemente mit Daten aufgefüllt oder deren Aussehen und Verhalten anpassen.

Weitere Informationen zum Entwerfen einer Benutzeroberfläche für eine universelle Windows-Plattform-app finden Sie unter [Entwurf und die Benutzeroberfläche](https://developer.microsoft.com/en-us/windows/design).

Weitere Informationen zum Erstellen einer Benutzeroberfläche für eine MFC-Anwendung finden Sie unter [MFC-Desktopanwendungen](../mfc/mfc-desktop-applications.md). Informationen über Win32-Windows-Programme finden Sie unter [Windows-Desktopanwendungen](../windows/windows-desktop-applications-cpp.md).

## <a name="writing-and-editing-code"></a>Schreiben und Bearbeiten von Code

### <a name="semantic-colorization"></a>Semantische Farbgebung

Nachdem Sie ein Projekt erstellen, werden alle Projektdateien angezeigt, der **Projektmappen-Explorer** Fenster. Wenn Sie beim Klicken auf eine h- oder cpp-Datei im **Projektmappen-Explorer**, öffnet die Datei im Code-Editor. Der Code-Editor ist ein spezielles Textverarbeitungsprogramm für C++-Quellcode. Er versieht Sprachschlüsselwörter, Methoden- und Variablennamen sowie andere Elemente im Codes mit verschiedenen Farben, sodass der Code besser lesbar und einfacher zu verstehen ist.

### <a name="intellisense"></a>Intellisense

Der Code-Editor unterstützt auch einige Funktionen, die zusammen als IntelliSense bezeichnet werden. Wenn Sie den Mauszeiger über eine Methode halten, werden grundlegende Informationen dazu angezeigt. Wenn Sie einen Klassenvariablennamen und dann einen Punkt (.) oder einen Pfeil ( ->) eingeben, wird eine Liste von Instanzmembern dieser Klasse angezeigt. Wenn Sie einen Klassennamen und dann „::“ eingeben, wird eine Liste der statischen Member angezeigt. Wenn Sie die Eingabe eines Klassen- oder Methodennamens beginnen, bietet der Code-Editor Vorschläge an, um die Anweisung zu vervollständigen. Weitere Informationen finden Sie unter [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense).

### <a name="code-snippets"></a>Codeausschnitte

Sie können IntelliSense-Codeausschnitte verwenden, um häufig verwendete oder komplexe Codekonstrukte mit einer Tastenkombination zu generieren. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).

## <a name="navigating-code"></a>Navigieren im Code

Die **Ansicht** Menü bietet Zugriff auf zahlreiche Fenster und Tools, denen Sie navigieren können, in Ihrem Code. Ausführliche Informationen zu diesen Fenstern finden Sie unter [Anzeigen der Codestruktur](/visualstudio/ide/viewing-the-structure-of-code).

### <a name="solution-explorer"></a>Projektmappen-Explorer

Verwenden Sie in allen Editionen von Visual Studio die **Projektmappen-Explorer** Bereich zum Navigieren zwischen den Dateien in einem Projekt. Erweitern Sie das Symbol für eine H- oder CPP-Datei, um die Klassen in der Datei anzuzeigen. Erweitern Sie eine Klasse, um ihre Member anzuzeigen. Doppelklicken Sie auf ein Member, um zu seiner Definition oder Implementierung in der Datei zu gelangen.

### <a name="class-view-and-code-definition-window"></a>Die Fenster „Klassenansicht“ und „Codedefinition“

Verwenden der **Klassenansicht** Bereich, um die Namespaces und Klassen in allen Dateien angezeigt, einschließlich der partiellen Klassen zu finden. Sie können jeden Namespace oder jede Klasse erweitern, um deren Member anzuzeigen. Sie können dann auf ein Member doppelklicken, um an seine Stelle in der Quelldatei zu navigieren. Wenn Sie öffnen die **Codedefinition (Fenster)**, Sie können die Definition oder Implementierung des Typs anzeigen, wenn Sie ihn in auswählen **Klassenansicht**.

### <a name="object-browser"></a>Objektkatalog

Verwendung **Objektkatalog** um Typinformationen in Windows-Runtime-Komponenten (winmd-Dateien) zu untersuchen, .NET-Assemblys und COM-Typbibliotheken. Der Objektkatalog wird nicht zusammen mit Win32-DLLs verwendet.

### <a name="go-to-definitiondeclaration"></a>Gehe zu Definition/Deklaration

Wenn Sie bei einem API-Namen oder einer Membervariablen die Taste F12 drücken, gelangen Sie zu der jeweiligen Definition. Wenn die Definition in einer winmd-Datei (für universelle Windows-Plattform oder Windows 8.x Store-Apps) ist, werden Sie die Typinformationen im Objektkatalog angezeigt. Sie könne auch **Gehe zu Definition** oder **Gehe zu Deklaration** von mit der rechten Maustaste auf den Namen der Variablen oder Typ und die Option im Kontextmenü auswählen.

### <a name="find-all-references"></a>Alle Verweise suchen

Mit der rechten Maustaste des Mauszeigers über den Namen eines Typs oder die Methode oder die Variable in einer Quellcodedatei, und wählen Sie **"alle Verweise suchen"** um eine Liste mit allen Stellen in der Datei, das Projekt oder die Projektmappe, in dem der Typ verwendet wird. **"Alle Verweise suchen"** ist intelligent und gibt nur Instanzen derselben, identischen Variablen, aus, auch wenn andere Variablen in anderen geltungsbereichen den gleichen Namen aufweisen.

## <a name="add-and-edit-resources--msbuild"></a>Hinzufügen und Bearbeiten von Ressourcen (MSBuild)

Der Begriff *Ressource* im Kontext eines Visual Studio-Desktopprojekts umfasst Aufgaben wie Dialogfelder, Symbole, lokalisierbaren Zeichenfolgen, Begrüßungsbildschirme, Datenbankverbindungszeichenfolgen oder sonstigen Daten, die in enthalten sein sollen die die ausführbare Datei.

Weitere Informationen zum Hinzufügen und Bearbeiten von Ressourcen in systemeigenen Desktop-c++-Projekten finden Sie unter [arbeiten mit Ressourcendateien](../windows/working-with-resource-files.md).

## <a name="build-compile-and-link"></a>Erstellen Sie (Kompilieren und verknüpfen)

Wählen Sie **erstellen** > **Projektmappe** auf das Menü Balken- oder geben Sie die Tastenkombination "STRG + UMSCHALT + B" Informationen zum Kompilieren und verknüpfen ein Projekt. Zum Erstellen von ausführbarem Code, Visual Studio verwendet [MSBuild](/visualstudio/msbuild/msbuild1) oder CMake oder jeder beliebigen Umgebung erstellen Sie über eingerichteten **Ordner öffnen**. Bei MSBuild-Projekten legen Sie allgemeine Buildoptionen unter **Tools** > **Optionen** > **Projekte und Projektmappen** und Sie können Eigenschaften festlegen für bestimmte Projekte unter **Projekt** > **Eigenschaften**. Buildfehler und Warnungen werden in der Fehlerliste gemeldet (STRG +\\, E). Nicht-MSBuild-Projekte werden mit JSON-Dateien konfiguriert, die Sie im Projektmappen-Explorer zu erstellen. Alle von Ihnen gewünschten ASP.NET-Buildsystem Sie verwenden, die **Ausgabe** Fenster (Alt + 2) enthält Informationen zum Buildprozess. Weitere Informationen zu MSBuild-Konfigurationen finden Sie unter [arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md) und [Erstellen von C++-Projekten in Visual Studio](../ide/building-cpp-projects-in-visual-studio.md).

Sie können auch den Compiler (cl.exe) und viele andere buildbezogene, eigenständigen Tools wie z. B. NMAKE und LIB direkt über die Befehlszeile verwenden. Weitere Informationen finden Sie unter [Erstellen von C/C++-Code in der Befehlszeile](../build/building-on-the-command-line.md) und [Referenz zur C/C++-Erstellung](../build/reference/c-cpp-building-reference.md).

## <a name="test"></a>Test

Visual Studio enthält einen Komponententest-Framework für systemeigenen C++- und C++/CLI-Code. Weitere Informationen finden Sie unter [Überprüfen von Code mithilfe von Komponententests](/visualstudio/test/unit-test-your-code) und [Schreiben von Komponententests für C/C++ mit dem Microsoft-Komponententestframework für C++](/visualstudio/test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp)

## <a name="debug"></a>Debug

Sie können das Programm debuggen, durch Drücken von **F5** Wenn die Projektkonfiguration auf Debuggen festgelegt ist. Beim Debuggen Sie durch Drücken von Haltepunkten kann **F9**, schrittweises Durchlaufen von Code durch Drücken von **F10**, die Werte angegebener Variablen oder Register anzeigen und sogar in einigen Fällen Änderungen am Code vornehmen und fortfahren Debuggen, ohne neu kompilieren zu müssen. Weitere Informationen finden Sie unter [Debuggen in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).

## <a name="deploy-completed-applications"></a>Bereitstellen fertiger Anwendungen

Bereitstellung eine uwp-app an Kunden über Microsoft Store über die **Projekt** > **Store** Option des Menüs. Die Bereitstellung von CRT wird automatisch im Hintergrund durchgeführt. Weitere Informationen finden Sie unter [Veröffentlichen von Windows-Apps](http://go.microsoft.com/fwlink/p/?LinkId=262280).

Wenn Sie eine systemeigene C++-Desktopanwendung auf einem anderen Computer bereitstellen, müssen Sie die Anwendung selbst sowie alle Bibliotheksdateien, von denen die Anwendung abhängt, installieren. Es gibt drei Möglichkeiten, die universelle C++-Laufzeit (UCRT) mit einer Anwendung bereitzustellen: zentrale Bereitstellung, lokale Bereitstellung oder statische Verknüpfung. Weitere Informationen finden Sie unter [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md).

Weitere Informationen zum Bereitstellen von C + c++ / CLI-Programms finden Sie unter [Deployment Guide für Entwickler](/dotnet/framework/deployment/deployment-guide-for-developers),

## <a name="related-articles"></a>Verwandte Artikel

|||
|-|-|
|[Visual C++-Tools und -Features in Visual Studio-Editionen](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)|Gibt an, welche Features in den verschiedenen Editionen von Visual Studio verfügbar sind.|
|[MSBuild-basierte Projekte erstellen und verwalten](../ide/creating-and-managing-visual-cpp-projects.md)|Bietet eine Übersicht über MSBuild für C++-basierte Projekte in Visual Studio und Links zu anderen Artikeln, die erläutern, wie Sie erstellt und verwaltet werden.|
|[CMake Projekte in Visual C++](cmake-tools-for-visual-cpp.md).|Beschreibt, wie CMake oder andere nicht MSBuild-Projekte in Visual C++ zu erstellen.|
|[Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)|Beschreibt das Erstellen von C++-Projekten.|
|[Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)|Bietet einen Überblick über die Bereitstellung von C++-Apps sowie Links zu anderen Artikeln, die die Bereitstellung im Detail beschreiben.|
|[Visual C++-Handbuch: Portieren und Aktualisieren](../porting/visual-cpp-porting-and-upgrading-guide.md)|Ausführliche Informationen zu C++-Anwendungen zu aktualisieren, die in früheren Versionen von Visual Studio erstellt wurden, sowie die Informationen zum Migrieren von Anwendungen, die mit anderen Tools als Visual Studio erstellt wurden.|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Beschreibt die wichtigsten Features von Visual C++ in Visual Studio und verlinkt zum Rest der Visual C++-Dokumentation.|
