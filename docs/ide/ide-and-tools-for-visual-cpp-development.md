---
title: "IDE und Tools für Visual C++-Entwicklung | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Visual C++, development tools
ms.assetid: 56eabafb-1956-4f0f-bec5-29b887763559
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1fc416d6856b2b84005e4e1d66e17a3b10e93eb6
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2017
---
# <a name="ide-and-tools-for-visual-c-development"></a>IDE und Tools für Visual C++-Entwicklung
Als Teil der integrierten Visual Studio-Entwicklungsumgebung (IDE) verwendet Visual C++ viele Fenster und Tools, die auch in zahlreichen anderen Sprachen verwendet werden. Viele davon, wie z. B. **Projektmappen-Explorer**, Code-Editor, und der Debugger, sind unter dokumentiert [Visual Studio-IDE](/visualstudio/ide/visual-studio-ide). Ein gemeinsam verwendetes Tool oder Fenster verfügt in C++ häufig über etwas andere Funktionen als für die .NET-Sprachen oder für JavaScript. Einige Fenster oder Tools sind nur in Visual Studio Pro oder Visual Studio Enterprise verfügbar.   
  
 Zusätzlich zu den gemeinsam verwendeten Tools in der integrierten Visual Studio-Entwicklungsumgebung verfügt Visual C++ über mehrere Tools, die speziell auf die Entwicklung von nativem Code ausgelegt sind. Diese Tools sind ebenfalls in diesem Artikel aufgeführt. Eine Liste der Tools in jeder Edition von Visual Studio verfügbar sind, finden Sie unter [Visual C++-Tools und Funktionen in Visual Studio-Editionen](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md).  
## <a name="creating-a-solution-and-projects"></a>Erstellen einer Projektmappe und von Projekten  

Ein "Projekt" ist im Grunde eine Reihe von Quellcodedateien und Ressourcen wie Bilder oder Datendateien, die in eine ausführbare Datei erstellt werden. Visual Studio-2017 unterstützen alle Buildsystem oder benutzerdefinierten Buildtools, die Sie mit vollständiger Unterstützung für Intellisense, durchsuchen und Debuggen verwenden möchten:
 - MSBuild ist das "systemeigene" Buildsystem für Visual Studio und ist häufig die beste Wahl für uwp-apps oder ältere Windows-desktopanwendungen, die MFC oder ATL verwenden Weitere Informationen zu MSBuild-basierte C++-Projekten finden Sie unter [erstellen und Verwalten von MSBuild-basierte Projekte](creating-and-managing-visual-cpp-projects.md).
 - CMake ist eine plattformübergreifende Buildsystem, die in der Visual Studio-IDE integriert ist, bei der Installation der C++-Desktop-arbeitsauslastung. Weitere Informationen finden Sie unter [CMake-Projekte in Visual C++](cmake-tools-for-visual-cpp.md).
 - Alle anderen C++-Buildsystems, einschließlich einer losen Auflistung von Dateien, wird über das Feature Open Folder unterstützt. Sie erstellen einfache JSON-Dateien zum Aufrufen des Programms erstellen und Konfigurieren von Debugsitzungen. Weitere Informationen finden Sie unter [bringen Sie C++-Code in Visual Studio](https://blogs.msdn.microsoft.com/vcblog/2017/04/14/bring-your-cpp-code-to-visual-studio/).
 
 
 **Projektvorlagen (MSBuild)**  
  
 Visual C++ enthält mehrere Vorlagen zum MSBuild-basierte Projekte; Diese Vorlagen enthalten startercode und die Einstellungen für verschiedene grundlegende Programmtypen benötigt. In der Regel beginnen Sie damit auszuwählen **Datei &#124; Neues Projekt** um ein Projekt von einer Vorlage zu erstellen, fügen Sie dann neue Quellcodedateien zu diesem Projekt, oder in den bereitgestellten Dateien codieren beginnen. Informationen zu C++-Projekten und Projektassistenten finden Sie unter [erstellen und Verwalten von Visual C++-Projekte](../ide/creating-and-managing-visual-cpp-projects.md).  
  
 **Anwendungsassistenten (MSBuild)**  
  
 Visual C++ stellt Assistenten für einige Projekttypen MSBuild, bei der Auswahl **Datei &#124; Neues Projekt**. Ein Assistent führt Sie schrittweise durch den Prozess zum Erstellen eines neuen Projekts. Dies ist nützlich für Projekttypen, für die es viele Optionen und Einstellungen gibt. Weitere Informationen finden Sie unter [erstellen Desktop-Projekten mithilfe von Anwendungsassistenten](../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
## <a name="creating-user-interfaces-with-designers-msbuild"></a>Erstellen von Benutzeroberflächen mit Designern (MSBuild) 
 Wenn Ihr Programm über eine Benutzeroberfläche verfügt, besteht eine der ersten Aufgaben darin, sie mit Steuerelementen wie Schaltflächen, Listenfeldern usw. auszustatten. Visual Studio enthält eine visuelle Entwurfsoberfläche und eine Toolbox für jede Art von C++-Anwendung. Unabhängig davon, welche Art von Anwendung Sie erstellen, ist die zugrunde liegende Idee gleich: Sie ziehen ein Steuerelement aus dem Toolboxfenster und legen es in der Entwurfsoberfläche an der gewünschten Stelle ab. Im Hintergrund generiert Visual Studio die Ressourcen und den Code, die erforderlich sind, damit alles funktioniert. Klicken Sie dann schreiben Sie den Code, um die Steuerelemente mit Daten aufgefüllt oder deren Aussehen und Verhalten anpassen.
  
 Weitere Informationen zum Entwerfen einer Benutzeroberfläche für eine universelle Windows-Plattform-app finden Sie unter [Entwurf und die Benutzeroberfläche](https://developer.microsoft.com/en-us/windows/design).  
  
 Weitere Informationen zum Erstellen einer Benutzeroberfläche für eine MFC-Anwendung finden Sie unter [MFC-Desktopanwendungen](../mfc/mfc-desktop-applications.md). Informationen über Win32-Windows-Programme finden Sie unter [Windows-Desktopanwendungen](../windows/windows-desktop-applications-cpp.md).  
  
 Informationen zu Windows Forms-Anwendung mit c++ / CLI finden Sie unter [Erstellen einer Windows Forms-Anwendung mithilfe der .NET Framework (C++)](http://msdn.microsoft.com/en-us/8e007885-6c8b-4fb2-a41d-91febd114a9b).  
  
## <a name="writing-and-editing-code"></a>Schreiben und Bearbeiten von Code  
 **Semantische Farbgebung**  
  
 Nachdem Sie ein Projekt erstellen, werden alle Projektdateien angezeigt, der **Projektmappen-Explorer** Fenster. Wenn Sie beim Klicken auf eine h- oder cpp-Datei im **Projektmappen-Explorer**, öffnet die Datei im Code-Editor. Der Code-Editor ist ein spezielles Textverarbeitungsprogramm für C++-Quellcode. Er versieht Sprachschlüsselwörter, Methoden- und Variablennamen sowie andere Elemente im Codes mit verschiedenen Farben, sodass der Code besser lesbar und einfacher zu verstehen ist.  
  
 **IntelliSense**  
  
 Der Code-Editor unterstützt auch einige Funktionen, die zusammen als IntelliSense bezeichnet werden. Wenn Sie den Mauszeiger über eine Methode halten, werden grundlegende Informationen dazu angezeigt. Wenn Sie einen Klassenvariablennamen und dann einen Punkt (.) oder einen Pfeil ( ->) eingeben, wird eine Liste von Instanzmembern dieser Klasse angezeigt. Wenn Sie einen Klassennamen und dann „::“ eingeben, wird eine Liste der statischen Member angezeigt. Wenn Sie die Eingabe eines Klassen- oder Methodennamens beginnen, bietet der Code-Editor Vorschläge an, um die Anweisung zu vervollständigen. Weitere Informationen finden Sie unter [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense).  
  
 **Codeausschnitte**  
  
 Sie können IntelliSense-Codeausschnitte verwenden, um häufig verwendete oder komplexe Codekonstrukte mit einer Tastenkombination zu generieren. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).  
  
## <a name="navigating-code"></a>Navigieren im Code  
 Die **Ansicht** Menü bietet Zugriff auf zahlreiche Fenster und Tools, denen Sie navigieren können, in Ihrem Code. Ausführliche Informationen zu diesen Fenstern finden Sie unter [Anzeigen der Codestruktur](/visualstudio/ide/viewing-the-structure-of-code).  
  
 **Projektmappen-Explorer**  
  
 Verwenden Sie in allen Editionen von Visual das Fenster „Projektmappen-Explorer“ zum Navigieren zwischen den Dateien in einem Projekt. Erweitern Sie das Symbol für eine H- oder CPP-Datei, um die Klassen in der Datei anzuzeigen. Erweitern Sie eine Klasse, um ihre Member anzuzeigen. Doppelklicken Sie auf ein Member, um zu seiner Definition oder Implementierung in der Datei zu gelangen.  
  
 **Klassenansicht "und" Codedefinition (Fenster)**  
  
 Verwenden der **Klassenansicht** Bereich, um die Namespaces und Klassen in allen Dateien angezeigt, einschließlich der partiellen Klassen zu finden. Sie können jeden Namespace oder jede Klasse erweitern, um deren Member anzuzeigen. Sie können dann auf ein Member doppelklicken, um an seine Stelle in der Quelldatei zu navigieren. Im geöffneten Codedefinitionsfenster können Sie die Definition oder Implementierung des Typs anzeigen, wenn Sie ihn in der Klassenansicht auswählen.  
  
 **Objektkatalog**  
  
 Verwendung **Objektkatalog** um Typinformationen in Windows-Runtime-Komponenten (winmd-Dateien) zu untersuchen, .NET-Assemblys und COM-Typbibliotheken. Der Objektkatalog wird nicht zusammen mit Win32-DLLs verwendet.  
  
 **Gehe zu Definition/Deklaration**  
  
 Wenn Sie bei einem API-Namen oder einer Membervariablen die Taste F12 drücken, gelangen Sie zu der jeweiligen Definition. Wenn sich die Definition in einer WINMD-Datei befindet (bei einer [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]-Anwendung), werden die Typinformationen im Objektkatalog angezeigt. Sie könne auch **Gehe zu Definition** oder **Gehe zu Deklaration** von mit der rechten Maustaste auf den Namen der Variablen oder Typ und die Option im Kontextmenü auswählen.  
  
 **Alle Verweise suchen**  
  
 Mit der rechten Maustaste des Mauszeigers über den Namen eines Typs oder die Methode oder die Variable in einer Quellcodedatei, und wählen Sie **"alle Verweise suchen"** um eine Liste mit allen Stellen in der Datei, das Projekt oder die Projektmappe, in dem der Typ verwendet wird. **"Alle Verweise suchen"** ist intelligent und gibt nur Instanzen derselben, identischen Variablen, aus, auch wenn andere Variablen in anderen geltungsbereichen den gleichen Namen aufweisen.  
  
 **Architektur-Explorer und Abhängigkeitsdiagramme (Ultimate)**  
  
 Verwendung **Architektur-Explorer** um Beziehungen zwischen verschiedenen Elementen in Ihren Code anzuzeigen. Weitere Informationen finden Sie unter [Suchen von Code im Architektur-Explorer](http://msdn.microsoft.com/en-us/b1707926-ef73-47f9-92cd-e00d0fac7e76). Verwenden Sie Abhängigkeitsdiagramme, um abhängigkeitsbeziehungen anzuzeigen. Weitere Informationen finden Sie unter [wie: Generieren von Abhängigkeitsdiagrammen für C- und C++-Code](http://msdn.microsoft.com/en-us/3bd5cf9f-62f6-41d0-9f35-d4b2637cba3c).  
  
## <a name="adding-and-editing-resources--msbuild"></a>Hinzufügen und Bearbeiten von Ressourcen (MSBuild)
 Der Begriff „Ressource“ im Kontext eines Visual Studio-Desktopprojekts umfasst Elemente wie z. B. Dialogfelder, Symbole, lokalisierbaren Zeichenfolgen, Begrüßungsbildschirme, Datenbankverbindungszeichenfolgen oder sonstigen Daten, die Sie in die ausführbare Datei einbeziehen möchten.  
  
 Weitere Informationen zum Hinzufügen und Bearbeiten von Ressourcen in systemeigenen Desktop-c++-Projekten finden Sie unter [arbeiten mit Ressourcendateien](../windows/working-with-resource-files.md).  
  
## <a name="building-compiling-and-linking"></a>Erstellen (Kompilieren und Verknüpfen)  
 Drücken Sie **STRG+UMSCHALT+B** , um ein Projekt zu kompilieren und zu verknüpfen. Zum Erstellen von ausführbarem Code, Visual Studio verwendet [MSBuild](/visualstudio/msbuild/msbuild1) oder CMake oder jeder beliebigen Umgebung erstellen Sie über eingerichteten **Ordner öffnen**. Bei MSBuild-Projekten legen Sie allgemeine Buildoptionen unter **Tools &#124; Optionen &#124; Projekte und Projektmappen** und die einstellbaren Eigenschaften für bestimmte Projekte unter **Projekt &#124; Eigenschaften**. Buildfehler und Warnungen werden in der Fehlerliste gemeldet (**STRG +\\, E**). Nicht-MSBuild-Projekte werden mit JSON-Dateien konfiguriert, die Sie im Projektmappen-Explorer zu erstellen. Was Sie verwenden, das Fenster "Ausgabe" ASP.NET-Buildsystem (**Alt + 2**) zeigt Informationen über die Build-Prozesses. Weitere Informationen zu MSBuild-Konfigurationen finden Sie unter [arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md) und [Erstellen von C++-Projekten in Visual Studio](../ide/building-cpp-projects-in-visual-studio.md).  
  
 Sie können auch den Visual C++-Compiler (cl.exe) und viele andere buildbezogene, eigenständigen Tools (z. B. NMAKE und LIB) direkt in der Befehlszeile verwenden. Weitere Informationen finden Sie unter [Erstellen von C/C++-Code in der Befehlszeile](../build/building-on-the-command-line.md) und [Referenz zur C/C++-Erstellung](../build/reference/c-cpp-building-reference.md).  
  
## <a name="testing"></a>Test  
 Visual Studio enthält einen Komponententest-Framework für systemeigenen C++- und C++/CLI-Code. Weitere Informationen finden Sie unter [Überprüfen von Code mithilfe von Komponententests](/visualstudio/test/unit-test-your-code) und [Schreiben von Komponententests für C/C++ mit dem Microsoft-Komponententestframework für C++](/visualstudio/test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp)  
  
## <a name="debugging"></a>Debuggen  
 Sie können das Programm debuggen, durch Drücken von **F5** Wenn die Projektkonfiguration auf Debuggen festgelegt ist. Beim Debuggen Sie durch Drücken von Haltepunkten kann **F9**, schrittweises Durchlaufen von Code durch Drücken von **F10**, die Werte angegebener Variablen oder Register anzeigen und sogar in einigen Fällen Änderungen am Code vornehmen und fortfahren Debuggen, ohne neu kompilieren zu müssen. Weitere Informationen finden Sie unter [Debuggen in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).  
  
## <a name="deploying-completed-applications"></a>Bereitstellen fertiger Anwendungen  
 Bereitstellung einer [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] an Kunden über den Windows Store über die **Projekt &#124; Store** Option des Menüs. Die Bereitstellung von CRT wird automatisch im Hintergrund durchgeführt. Weitere Informationen finden Sie unter [Veröffentlichen von Windows-Apps](http://go.microsoft.com/fwlink/p/?LinkId=262280).  
  
 Wenn Sie eine systemeigene C++-Desktopanwendung auf einem anderen Computer bereitstellen, müssen Sie die Anwendung selbst sowie alle Bibliotheksdateien, von denen die Anwendung abhängt, installieren. Es gibt drei Möglichkeiten zum Bereistellen der Visual C++-Runtime: eine zentrale Bereitstellung, lokale Bereitstellung oder statische Verknüpfung. Weitere Informationen finden Sie unter [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md).  
  
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
|[Visual C++](../top/visual-cpp-in-visual-studio.md)|Beschreibt die wichtigsten Features von Visual C++ in Visual Studio und verlinkt zum Rest der Visual C++-Dokumentation.|
