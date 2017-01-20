---
title: "Erstellen von C++-Projekten in Visual&#160;Studio"
ms.custom: na
ms.date: "12/15/2016"
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
  - "Builds [C++], Informationen über Erstellen in Visual Studio"
  - "Projekte [C++], Erstellen"
  - "Visual C++-Projekte, Erstellen"
ms.assetid: 9e8bc1a2-bb17-4951-937a-c757ed88d2d1
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "corob"
manager: "ghogen"
---
# Erstellen von C++-Projekten in Visual&#160;Studio
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In der integrierten Entwicklungsumgebung \(Integrated Development Environment, IDE\) vom Visual Studio gibt es verschiedene Möglichkeiten für das Erstellen einer kompletten Lösung oder nur eines Projekts.  Sie können außerdem Buildeinstellungen ändern und benutzerdefiniere Buildschritte angeben, um Ihren Entwicklungsprozess effizienter zu gestalten.  
  
 Sie können wie folgt vorgehen, um eine Lösung zu erstellen, die [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] geöffnet und im **Projektmappen\-Explorer** ausgewählt ist:  
  
-   Wählen Sie in der Menüleiste **Erstellen**, **Projektmappe erstellen**.  
  
-   Oder öffnen Sie im **Projektmappen\-Explorer** das Kontextmenü für die Projektmappe, und wählen Sie dann **Projektmappe erstellen** aus.  
  
-   Oder drücken Sie F7.  \(Das ist das Standardtastenkürzel für die C\-\/C\+\+\-Entwicklungseinstellungen.\)  
  
-   Oder geben Sie im [Befehlsfenster](../Topic/Command%20Window.md) \(wählen Sie in der Menüleiste **Ansicht**, **Andere Fenster**, **Befehlsfenster** aus\), `Build.BuildSolution` ein.  
  
-   Oder geben Sie in das Feld [Schnellstart](../Topic/Quick%20Launch,%20Environment,%20Options%20Dialog%20Box.md) `build build solution` ein.  
  
 Sie können wie folgt vorgehen, um ein Projekt zu erstellen, das im **Projektmappen\-Explorer** ausgewählt ist:  
  
-   Wählen Sie in der Menüleiste **Erstellen**, **\<Projektname\> erstellen** aus.  
  
-   Oder öffnen Sie im **Projektmappen\-Explorer** das Kontextmenü für das Projekt, und wählen Sie dann **Erstellen** aus.  
  
-   Oder geben Sie im Befehlsfenster \(wählen Sie in der Menüleiste **Ansicht**, **Andere Fenster**, **Befehlsfenster** aus\) `Build.BuildOnlyProject` ein.  
  
-   Oder geben Sie in das Schnellstartfeld `build project only build only <Projektname>` ein.  
  
 Wenn Sie eine Visual C\+\+\-Anwendung in Visual Studio erstellen, können Sie viele der Buildeinstellungen im Dialogfeld für die Eigenschaftenseiten des Projekts ändern.  Informationen zum Festlegen von Projekteigenschaften finden Sie unter [Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md).  
  
 Ein Beispiel für die Verwendung der IDE zum Erstellen, Aufbauen und Debuggen eines C\+\+\-Projekts finden Sie unter [Exemplarische Vorgehensweise: Erkunden der Visual Studio IDE mit C\+\+](../Topic/Getting%20Started%20with%20C++%20in%20Visual%20Studio.md).  Ein Beispiel für die Verwendung der IDE für das Erstellen eines C\+\+\-\/CLR\-Projekts finden Sie unter [Exemplarische Vorgehensweise: Kompilieren eines C\+\+\-Programms für die CLR in Visual Studio](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md).  Ein Beispiel für die Verwendung der IDE zum Erstellen einer Windows Runtime\-App finden Sie unter [Erstellen Ihrer ersten Windows Runtime\-App mit C\+\+](http://msdn.microsoft.com/library/windows/apps/hh974580.aspx).  
  
 Weitere Informationen zum Erstellen, Ändern von Buildeinstellungen und Angeben von benutzerdefinierten Buildschritten finden Sie in den folgenden Artikeln.  
  
## In diesem Abschnitt  
 [Grundlagen benutzerdefinierter Buildschritte und Buildereignisse](../ide/understanding-custom-build-steps-and-build-events.md)  
 Beschreibt, wie Sie den Buildprozess in der integrierten Entwicklungsumgebung anpassen.  
  
 [Makros für Buildbefehle und \-eigenschaften](../ide/common-macros-for-build-commands-and-properties.md)  
 Listet Makros auf, die Sie verwenden können, wenn Zeichenfolgen akzeptiert werden.  
  
 [Erstellen externer Projekte](../ide/building-external-projects.md)  
 Stellt das Erstellen von Projekten dar, die Funktionen außerhalb der integrierten Entwicklungsumgebung verwenden.  
  
 [Projektdateien](../ide/project-files.md)  
 Stellt die XML\-Struktur einer .vcxproj\-Datei dar.  
  
## Verwandte Abschnitte  
 [VC\+\+ Directories, Projects, Options Dialog Box](assetId:///e027448b-c811-4c3d-8531-4325ad3f6e02)  
 Stellt dar, wie Sie den Suchpfad für ausführbare Dateien ändern und Dateien, Bibliotheksdateien und Quellcodedateien während des Erstellens einschließen.  
  
 [Anwendungen in Visual Studio erstellen](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md)  
 Bietet Informationen zum Erstellen in Visual Studio.  
  
 [Erstellen von C\/C\+\+\-Programmen](../build/building-c-cpp-programs.md)  
 Bietet Links zu Themen, in denen das Erstellen von Programmen über die Befehlszeile oder die integrierte Entwicklungsumgebung von Visual Studio beschrieben sind.  
  
 [Referenz zur C\/C\+\+\-Erstellung](../build/reference/c-cpp-building-reference.md)  
 Bietet Links zu einem Überblick für das Erstellen von Programmen C\+\+, Compiler\- und Linkeroptionen und zusätzlichen Buildtools.  
  
 [Aktualisieren von Projekten von früheren Versionen von Visual C\+\+](../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md)  
 Bietet Links zu Themen, in denen Probleme beim Upgrade von Visual C\+\+ 6.0\- und späteren Projekten auf Visual C\+\+ .NET abgedeckt sind.  
  
 [Porting and Upgrading Programs](assetId:///c36c44b3-5a9b-4bb4-9b7a-469aa770ed00)  
 Stellt Details zum Portieren von Anwendungen bereit und beschreibt Makefiles.  
  
## Siehe auch  
 [Roadmap for Windows Store apps using C\+\+](assetId:///0b71e4a4-5d8a-4a20-b2ec-e40062675ec1)