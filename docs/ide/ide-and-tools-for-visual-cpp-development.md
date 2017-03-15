---
title: "IDE und Tools f&#252;r Visual C++-Entwicklung"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Visual C++, Entwicklungstools"
ms.assetid: 56eabafb-1956-4f0f-bec5-29b887763559
caps.latest.revision: 17
caps.handback.revision: "17"
ms.author: "mblome"
manager: "ghogen"
---
# IDE und Tools f&#252;r Visual C++-Entwicklung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Als Teil der integrierten Visual Studio-Entwicklungsumgebung (IDE) verwendet Visual C++ viele Fenster und Tools, die auch in zahlreichen anderen Sprachen verwendet werden. Viele davon, wie z. B. der **Projektmappen-Explorer**, der Code-Editor und der Debugger, sind in der MSDN-Bibliothek unter [Visual Studio IDE](../Topic/Visual%20Studio%20IDE.md)dokumentiert. Ein gemeinsam verwendetes Tool oder Fenster verfügt in C++ häufig über etwas andere Funktionen als für die .NET-Sprachen oder für JavaScript. Einige Fenster oder Tools sind nur in Visual Studio Pro oder Visual Studio Enterprise verfügbar. Dieses Thema erläutert die integrierte Visual Studio-Entwicklungsumgebung in Bezug auf Visual C++ und stellt Links zu anderen Themen bereit, die für Visual C++ relevant sind.  
  
 Zusätzlich zu den gemeinsam verwendeten Tools in der integrierten Visual Studio-Entwicklungsumgebung verfügt Visual C++ über mehrere Tools, die speziell auf die Entwicklung von systemeigenem Code ausgelegt sind. Diese Tools sind ebenfalls in diesem Artikel aufgeführt. Eine Liste, welche Tools in jeder Edition von Visual Studio verfügbar sind, finden Sie unter [Visual C++ Tools and Templates in Visual Studio Editions](../ide/visual-cpp-tools-and-templates-in-visual-studio-editions.md).  
  
## <a name="creating-a-solution-and-projects"></a>Erstellen einer Projektmappe und von Projekten  
 In allen Editionen von Visual C++ organisieren Sie den Quellcode und zugehörige Dateien für eine ausführbare Datei (z. B. eine EXE-, DLL- oder LIB-Datei) in einem Projekt. Ein Projekt enthält eine Projektdatei im XML-Format (.vcxproj), die alle Dateien und Ressourcen angibt, die zum Kompilieren des Programms notwendig sind. Außerdem gibt sie andere Konfigurationseinstellungen an, wie z. B. die Zielplattform (x 86, X 64 oder ARM), und ob Sie eine Releaseversion oder Debugversion des Programms erstellen. Ein Projekt bzw. mehrere Projekte befinden sich in einer *Projektmappe*. Eine Projektmappe kann zum Beispiel mehrere Win32-DLL-Projekte und eine einzelne Win32-Konsolenanwendung enthalten, die diese DLLs verwendet. Wenn Sie das Projekt erstellen, verarbeitet das MSBuild-Modul die Projektdatei und erstellt die ausführbare Datei und/oder jede weitere benutzerdefinierte Ausgabe, die Sie angegeben haben.  
  
 **Projektvorlagen**  
  
 Visual C++ enthält mehrere Projektvorlagen, die den Startercode und die Einstellungen für verschiedene grundlegende Programmtypen enthalten. Sie beginnen normalerweise durch Auswahl **Datei &#124; Neues Projekt** zum Erstellen eines Projekts von einer Vorlage müssen Sie dann das Projekt neue Quellcodedateien hinzu, oder in den bereitgestellten Dateien codieren beginnen. Spezielle Informationen zu C++-Projekten und -Projekt-Assistenten finden Sie unter [Creating and Managing Visual C++ Projects](../ide/creating-and-managing-visual-cpp-projects.md).  
  
 **Anwendungsassistenten**  
  
 Visual C++ stellt Assistenten für einige Projekttypen bereit. Ein Assistent führt Sie schrittweise durch den Prozess zum Erstellen eines neuen Projekts. Dies ist nützlich für Projekttypen, für die es viele Optionen und Einstellungen gibt. Weitere Informationen finden Sie unter [Creating Desktop Projects By Using Application Wizards](../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
## <a name="creating-user-interfaces-with-designers"></a>Erstellen von Benutzeroberflächen mit Designern  
 Wenn Ihr Programm über eine Benutzeroberfläche verfügt, besteht eine der ersten Aufgaben darin, sie mit Steuerelementen wie Schaltflächen, Listenfeldern usw. auszustatten. Visual Studio enthält eine visuelle Entwurfsoberfläche und eine Toolbox für jede Art von C++-Anwendung. Unabhängig davon, welche Art von Anwendung Sie erstellen, ist die zugrunde liegende Idee gleich: Sie ziehen ein Steuerelement aus dem Toolboxfenster und legen es in der Entwurfsoberfläche an der gewünschten Stelle ab. Im Hintergrund generiert Visual Studio die Ressourcen und den Code, die erforderlich sind, damit alles funktioniert.  
  
 Weitere Informationen zum Entwerfen einer Benutzeroberfläche für eine universelle Windows-Plattform-app finden Sie unter  [Design und die Benutzeroberfläche](https://developer.microsoft.com/en-us/windows/design).  
  
 Weitere Informationen zum Erstellen einer Benutzeroberfläche für eine MFC-Anwendung finden Sie unter [MFC Desktop Applications](../mfc/mfc-desktop-applications.md). Informationen zu Win32-Windows-Programmen finden Sie unter [Windows-Desktopanwendungen](../windows/windows-desktop-applications-cpp.md).  
  
 Informationen zu Windows Forms-Anwendung mit C++/CLI finden Sie unter [Erstellen einer Windows Forms-Anwendung mit dem .NET Framework (C++)](assetId:///8e007885-6c8b-4fb2-a41d-91febd114a9b).  
  
## <a name="writing-and-editing-code"></a>Schreiben und Bearbeiten von Code  
 **Semantische Farbgebung**  
  
 Nachdem Sie ein Projekt erstellt haben, werden alle Projektdateien im Fenster des Projektmappen-Explorers angezeigt. Wenn Sie auf im Projektmappen-Explorer auf eine H- oder CPP-Datei klicken, wird die Datei im Code-Editor geöffnet. Der Code-Editor ist ein spezielles Textverarbeitungsprogramm für C++-Quellcode. Er versieht Sprachschlüsselwörter, Methoden- und Variablennamen sowie andere Elemente im Codes mit verschiedenen Farben, sodass der Code besser lesbar und einfacher zu verstehen ist.  
  
 **IntelliSense**  
  
 Der Code-Editor unterstützt auch einige Funktionen, die zusammen als IntelliSense bezeichnet werden. Wenn Sie den Mauszeiger über eine Methode halten, werden grundlegende Informationen dazu angezeigt. Wenn Sie einen Klassenvariablennamen und dann einen Punkt (.) oder einen Pfeil ( ->) eingeben, wird eine Liste von Instanzmembern dieser Klasse angezeigt. Wenn Sie einen Klassennamen und dann „::“ eingeben, wird eine Liste der statischen Member angezeigt. Wenn Sie die Eingabe eines Klassen- oder Methodennamens beginnen, bietet der Code-Editor Vorschläge an, um die Anweisung zu vervollständigen. Weitere Informationen finden Sie unter [Using IntelliSense](../Topic/Using%20IntelliSense.md).  
  
 **Codeausschnitte**  
  
 Sie können IntelliSense-Codeausschnitte verwenden, um häufig verwendete oder komplexe Codekonstrukte mit einer Tastenkombination zu generieren. Weitere Informationen finden Sie unter [Code Snippets](../Topic/Code%20Snippets.md).  
  
## <a name="navigating-code"></a>Navigieren im Code  
 Das Menü „Ansicht“ bietet Ihnen Zugriff auf zahlreiche Fenster und Tools, mit denen Sie in Ihrem Code navigieren können. Ausführliche Informationen über diese Fenster finden Sie unter [Viewing the Structure of Code](../Topic/Viewing%20the%20Structure%20of%20Code.md).  
  
 **Projektmappen-Explorer**  
  
 Verwenden Sie in allen Editionen von Visual das Fenster „Projektmappen-Explorer“ zum Navigieren zwischen den Dateien in einem Projekt. Erweitern Sie das Symbol für eine H- oder CPP-Datei, um die Klassen in der Datei anzuzeigen. Erweitern Sie eine Klasse, um ihre Member anzuzeigen. Doppelklicken Sie auf ein Member, um zu seiner Definition oder Implementierung in der Datei zu gelangen.  
  
 **Klassenansicht und Codedefinition (Fenster)**  
  
 Im Fenster „Klassenansicht“ werden die Namespaces und Klassen in allen Dateien angezeigt, einschließlich der partiellen Klassen. Sie können jeden Namespace oder jede Klasse erweitern, um deren Member anzuzeigen. Sie können dann auf ein Member doppelklicken, um an seine Stelle in der Quelldatei zu navigieren. Im geöffneten Codedefinitionsfenster können Sie die Definition oder Implementierung des Typs anzeigen, wenn Sie ihn in der Klassenansicht auswählen.  
  
 **Objektkatalog**  
  
 Verwenden Sie den Objektkatalog, um Typinformationen in Windows Runtime-Komponenten (WINMD-Dateien), .NET-Assemblys und COM-Typbibliotheken anzuzeigen. Der Objektkatalog wird nicht zusammen mit Win32-DLLs verwendet.  
  
 **Gehe zu Definition-Deklaration**  
  
 Wenn Sie bei einem API-Namen oder einer Membervariablen die Taste F12 drücken, gelangen Sie zu der jeweiligen Definition. Wenn sich die Definition in einer WINMD-Datei befindet (bei einer [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] -Anwendung), werden die Typinformationen im Objektkatalog angezeigt. Sie können die Optionen „Gehe zu Definition“ oder „Gehe zu Deklaration“ auch aufrufen, indem Sie mit der rechten Maustaste auf den Namen der Variablen oder des Typs klicken und die Option im Kontextmenü auswählen.  
  
 **Alle Verweise suchen**  
  
 Klicken Sie in einer Quellcodedatei, wenn sich der Mauszeiger auf dem Namen eines Typs, einer Methode oder Variablen befindet, mit der rechten Maustaste , und wählen Sie „Alle Verweise suchen“, um eine Liste mit allen Stellen in der Datei, dem Projekt oder einer Projektmappe anzuzeigen, an denen der Typ verwendet wird. "Alle Verweise suchen" ist intelligent und gibt auch dann nur Instanzen derselben identischen Variable zurück, wenn andere Variablen in einem anderen Bereich den gleichen Namen haben.  
  
 **Architektur-Explorer und Abhängigkeitsdiagramme (Ultimate)**  
  
 Verwenden Sie den Architektur-Explorer, um Beziehungen zwischen verschiedenen Elementen in Ihren Code anzuzeigen. Weitere Informationen finden Sie unter [Suchen von Code im Architektur-Explorer](assetId:///b1707926-ef73-47f9-92cd-e00d0fac7e76). Verwenden Sie Abhängigkeitsdiagramme, um Abhängigkeitsbeziehungen anzuzeigen. Weitere Informationen finden Sie unter [How to: Generate Dependency Graphs for C and C++ Code](assetId:///3bd5cf9f-62f6-41d0-9f35-d4b2637cba3c).  
  
## <a name="adding-and-editing-resources"></a>Hinzufügen und Bearbeiten von Ressourcen  
 Der Begriff „Ressource“ im Kontext eines Visual Studio-Desktopprojekts umfasst Elemente wie z. B. Dialogfelder, Symbole, lokalisierbaren Zeichenfolgen, Begrüßungsbildschirme, Datenbankverbindungszeichenfolgen oder sonstigen Daten, die Sie in die ausführbare Datei einbeziehen möchten.  
  
 Weitere Informationen über das Hinzufügen und Bearbeiten von Ressourcen in systemeigenen Desktop-C++-Projekten finden Sie unter [Working with Resource Files](../mfc/working-with-resource-files.md).  
  
## <a name="building-compiling-and-linking"></a>Erstellen (Kompilieren und Verknüpfen)  
 Drücken Sie **STRG+UMSCHALT+B** , um ein Projekt zu kompilieren und zu verknüpfen. Visual Studio verwendet [MSBuild](MSBuild1.md) zum Erstellen von ausführbarem Code. Sie können festlegen, dass allgemeine Buildoptionen unter **Tools &#124; Optionen &#124; Projekte und Projektmappen** und Sie können Eigenschaften für bestimmte Projekte unter **Projekt &#124; Eigenschaften**. Buildfehler und Warnungen werden in der Fehlerliste gemeldet (**STRG +\\, E**). Zusätzliche Informationen werden manchmal im Ausgabefenster angezeigt (**ALT+2**). Weitere Informationen finden Sie unter  [Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md) und [Erstellen von C++-Projekten in Visual Studio](../ide/building-cpp-projects-in-visual-studio.md).  
  
 Sie können auch den Visual C++-Compiler (cl.exe) und viele andere buildbezogene, eigenständigen Tools (z. B. NMAKE und LIB) direkt in der Befehlszeile verwenden. Weitere Informationen finden Sie unter [Building on the Command Line](../build/building-on-the-command-line.md) und [C/C++ Building Reference](../build/reference/c-cpp-building-reference.md).  
  
## <a name="testing"></a>Test  
 Visual Studio enthält einen Komponententest-Framework für systemeigenen C++- und C++/CLI-Code. Weitere Informationen finden Sie unter [Überprüfen von Code mit Komponententests](../Topic/Unit%20Test%20Your%20Code.md) und [Schreiben von Komponententests für C/C++ mit dem Microsoft-Komponententest-Framework für C++](../Topic/Writing%20Unit%20tests%20for%20C-C++%20with%20the%20Microsoft%20Unit%20Testing%20Framework%20for%20C++.md)  
  
## <a name="debugging"></a>Debuggen  
 Sie können das Programm debuggen, indem Sie die Taste F5 drücken wenn die Projektkonfiguration für das Debuggen festgelegt ist. Während des Debuggens können Sie durch Drücken der Taste F9 Haltepunkte setzen, durch Drücken der Taste F10 den Code schrittweise durchlaufen, die Werte angegebener Variablen oder Register anzeigen und in einigen Fällen sogar Änderungen am Code vornehmen und mit dem Debuggen fortfahren, ohne neu kompilieren zu müssen. Weitere Informationen finden Sie unter [Debugging in Visual Studio](../Topic/Debugging%20in%20Visual%20Studio.md).  
  
## <a name="deploying-completed-applications"></a>Bereitstellen fertiger Anwendungen  
 Bereitstellung einer [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] Kunden über den Windows Store über das **PROJEKT &#124; Store** Menüoption. Die Bereitstellung von CRT wird automatisch im Hintergrund durchgeführt. Weitere Informationen finden Sie unter [Veröffentlichen von Windows-Apps](http://go.microsoft.com/fwlink/p/?LinkId=262280).  
  
 Wenn Sie eine systemeigene C++-Desktopanwendung auf einem anderen Computer bereitstellen, müssen Sie die Anwendung selbst sowie alle Bibliotheksdateien, von denen die Anwendung abhängt, installieren. Es gibt drei Möglichkeiten zum Bereistellen der Visual C++-Runtime: eine zentrale Bereitstellung, lokale Bereitstellung oder statische Verknüpfung. Weitere Informationen finden Sie unter [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md).  
  
 Weitere Informationen zum Bereitstellen eines c++ / CLI-Programm finden Sie unter [Bereitstellungshandbuch für Entwickler](../Topic/.NET%20Framework%20Deployment%20Guide%20for%20Developers.md),  
  
## <a name="other-tools"></a>Sonstige Tools  
  
## <a name="related-articles"></a>Verwandte Artikel  
  
|||  
|-|-|  
|[Visual C++-Tools und Vorlagen in Visual Studio-Editionen](../ide/visual-cpp-tools-and-templates-in-visual-studio-editions.md)|Gibt an, welche Features in den verschiedenen Editionen von Visual Studio verfügbar sind.|  
|[Einführung in Visual C++](assetId:///499cb66f-7df1-45d6-8b6b-33d94fd1f17c)|Bietet eine Übersicht der Visual Studio-Entwicklungsumgebung und der Typen von C++-Apps, die Sie erstellen können.|  
|[Erstellen und Verwalten von Visual C++-Projekte](../ide/creating-and-managing-visual-cpp-projects.md)|Bietet eine Übersicht über C++-Projekten in Visual Studio und Links zu anderen Artikeln, die beschreiben, wie sie erstellt und verwaltet werden.|  
|[Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)|Beschreibt das Erstellen von C++-Projekten.|  
|[Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)|Bietet einen Überblick über die Bereitstellung von C++-Apps sowie Links zu anderen Artikeln, die die Bereitstellung im Detail beschreiben.|  
|[Portieren und Aktualisieren von Programmen](assetId:///c36c44b3-5a9b-4bb4-9b7a-469aa770ed00)|Enthält Links zu Artikeln, in denen das Öffnen von C++-Apps beschrieben wird, die in früheren Versionen von Visual Studio erstellt wurden, sowie Informationen zum Öffnen von Apps, die mit anderen Tools als Visual Studio erstellt wurden.|  
|||  
|[Visual C++](../top/visual-cpp-in-visual-studio-2015.md)|Beschreibt die wichtigsten Features von Visual C++ in Visual Studio und verlinkt zum Rest der Visual C++-Dokumentation.|