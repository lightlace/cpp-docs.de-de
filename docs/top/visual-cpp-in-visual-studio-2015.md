---
title: "Visual C++ in Visual Studio 2015"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "visual c++"
  - "visual c"
  - "vc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Nicht verwalteter Code, C++"
  - "Entwicklungsumgebung, Visual C++"
  - "Code, nicht verwalteter"
  - "Visual C++"
  - "Visual C++, Referenz"
ms.assetid: e8dcc44c-a3e2-4ffe-887c-fd15b18dc458
caps.latest.revision: 61
caps.handback.revision: "61"
ms.author: "mblome"
manager: "ghogen"
---
# Visual C++ in Visual Studio 2015
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit der [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Programmiersprache und \-Entwicklungstools können Sie native universelle Windows\-Apps, native Desktop\- und Serveranwendungen, plattformübergreifende Bibliotheken, die unter Android, iOS und Windows ausgeführt werden können, und verwaltete Apps für .NET Framework entwickeln.  
  
 **An wen richtet sich diese Dokumentation?**  
  
 Dieser Inhalt ist für C\+\+\-Entwickler gedacht, die Programme schreiben.  
  
-   Wenn Sie zum Ausführen eines Programms ein verteilbares C\+\+\-Paket sowie Laufzeitkomponenten suchen, wechseln Sie zum [Microsoft Download Center](http://www.microsoft.com/en-us/download/), und geben Sie **Visual C\+\+** in das Suchfeld ein.  
  
-   Wenn Sie eine Einführung in C\+\+\-Programmierkonzepte suchen, besuchen Sie eine der zahlreichen Websites mit dem entsprechenden Inhalt, oder holen Sie sich ein Exemplar von [Programming – Principles and Practice Using C\+\+ \(Second Edition\)](http://stroustrup.com/Programming/) vom C\+\+\-Erfinder Bjarne Stroustrup. Der Buchinhalt setzt voraus, dass Sie bereits über grundlegende C\+\+\-Kenntnisse verfügen.  
  
-   Wenn Sie den Visual C\+\+\-Compiler suchen, müssen Sie entweder eine kostenpflichtige oder eine kostenlose Edition von Visual Studio 2015 von [https:\/\/www.visualstudio.com\/](https://www.visualstudio.com/) herunterladen.  
  
> [!WARNING]
>  In Visual Studio 2015 ist Visual C\+\+ nicht standardmäßig installiert  Achten Sie bei der Installation darauf, **Benutzerdefiniert** und anschließend die erforderlichen C\+\+\-Komponenten auszuwählen. Wenn Visual Studio bereits installiert ist, wählen Sie **Datei &#124; Neu &#124; Projekt &#124; C\+\+**, anschließend werden Sie aufgefordert, die erforderlichen Komponenten zu installieren.  
  
## Allgemeine Informationen über Visual C\+\+  
 [Neues bei Visual C\+\+](../top/what-s-new-for-visual-cpp-in-visual-studio-2015.md)  
 Neue Funktionen in Visual C\+\+.  
  
 [Wichtige Änderungen in Visual C\+\+ 2015](../porting/visual-cpp-change-history-2003-20151.md)  
 Weitere Informationen über die wichtigen Änderungen in dieser Version.  
  
 [Willkommen zurück bei C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)  
 Erfahren Sie mehr über moderne C\+\+\-Programmiertechniken, die auf C\+\+11 und C\+\+14 basieren, und mithilfe derer Sie schnellen und sicheren Code schreiben und viele Probleme der C\-Programmierung vermeiden können.  
  
 [How to Report a Problem with the Visual C\+\+ Toolset](../Topic/How%20to%20Report%20a%20Problem%20with%20the%20Visual%20C++%20Toolset.md)  
 Erfahren Sie mehr über die Erstellung effektiver Fehlerberichte für das Visual C\+\+\-Toolset \(Compiler, Linker und andere Tools\) und über die verschiedenen Wege, auf denen Sie den Bericht versenden können.  
  
 [Visual C\+\+\-Handbuch: Portieren und Aktualisieren](../porting/visual-cpp-porting-and-upgrading-guide.md)  
 Leitfaden für das Portieren von Code und das Aktualisieren von Projekten auf Visual C\+\+ in [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)], einschließlich der Portierung von C\+\+\-Code zu Windows 10 und der universellen Windows\-Plattform.  
  
 [Unterstützung für C\+\+11\/14\/17\-Funktionen](../cpp/support-for-cpp11-14-17-features-modern-cpp.md)  
 Weitere Informationen über die Unterstützung für C\+\+11\- und C\+\+14\-Funktionen in Visual C\+\+.  
  
 [Visual C\+\+\-Team\-Blog](http://blogs.msdn.com/b/vcblog/)  
 Weitere Informationen über neue Funktionen und die neuesten Informationen von den Entwicklern von [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)].  
  
 [Visual Studio\-Downloads](http://go.microsoft.com/fwlink/?LinkId=235233)  
 Laden Sie Visual C\+\+ herunter.  
  
 [Visual C\+\+\-Tools und \-Vorlagen in Visual Studio\-Editionen](../ide/visual-cpp-tools-and-templates-in-visual-studio-editions.md)  
 Informieren Sie sich über die verschiedenen Visual Studio\-Editionen.  
  
 [Unterstützte Plattformen](../top/supported-platforms-visual-cpp.md)  
 Stellen Sie fest, welche Plattformen unterstützt werden.  
  
 [Visual C\+\+\-Beispiele](../top/visual-cpp-samples.md)  
 Informationen zu Beispielen.  
  
 [Visual Studio\-Community](http://go.microsoft.com/fwlink/?LinkId=235296)  
 Informieren Sie sich, wie Sie Hilfe erhalten, Fehler melden und Vorschläge für Visual Studio unterbreiten.  
  
## Schreiben von Anwendungen in C\+\+  
 [Universelle Windows\-Apps](../windows/universal-windows-apps-cpp.md)  
 Rufen Sie Anleitungen und Referenzmaterial im Windows Developer Center ab. Informationen zum Entwickeln von Windows Store\-Apps finden Sie unter [Entwickeln von Windows Store\-Apps mit Visual Studio](http://go.microsoft.com/fwlink/p/?LinkId=248364) und [Roadmap für Windows Store\-Apps mit C\+\+](http://go.microsoft.com/fwlink/p/?LinkId=244654).  
  
 [Windows\-Desktopanwendungen \(Visual C\+\+\)](../windows/desktop-applications-visual-cpp.md)  
 Erfahren Sie, wie Sie Desktopanwendungen erstellen, die eine Nachrichtenschleife und Rückrufe haben.  
  
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)  
 Stellen Sie fest, wie Win32, ATL und MFC zum Erstellen von Windows\-Desktop DLLs verwendet werden und Informationen zum Kompilieren und Registrieren der DLL bereitstellen.  
  
 [Parallele Programmierung](../parallel/parallel-programming-in-visual-cpp.md)  
 Erfahren Sie, wie Sie die Parallel Patterns Library, C\+\+ AMP, OpenMP und andere Funktionen in Verbindung mit Multithreading unter Windows verwenden.  
  
 [Empfohlene Vorgehensweisen bezüglich der Sicherheit](../top/security-best-practices-for-cpp.md)  
 Erfahren Sie, wie Sie Anwendungen vor bösartigem Code und nicht autorisierter Verwendung schützen.  
  
 [Cloud\- und Webprogrammierung](../top/cloud-and-web-programming-in-visual-cpp.md)  
 In C\+\+ haben Sie mehrere Optionen, um eine Verbindung mit dem Web und der Cloud herzustellen.  
  
 [Datenzugriff](../Topic/Data%20Access%20in%20Visual%20C++.md)  
 Herstellen einer Verbindung mit Datenbanken mit ODBC und anderen Datenzugriffstechnologien  
  
 [Text und Zeichenfolgen](../text/text-and-strings-in-visual-cpp.md)  
 Hier erhalten Sie Informationen zum Arbeiten mit verschiedenen Text\- und Zeichenfolgenformaten und Codierungen für die lokale und internationale Entwicklung.  
  
## C\+\+\-Entwicklungstools  
 Weitere Informationen zum Erstellen von Projekten, Arbeiten mit Quellcodedateien, Verknüpfen mit Bibliotheken, Kompilieren, Debuggen, Erstellen von Profilen, Bereitstellen und mehr finden Sie unter [IDE und Entwicklungstools](../ide/ide-and-tools-for-visual-cpp-development.md).  
  
## C\+\+\-Programmiersprachenreferenz  
 Weitere Informationen zur C\+\+\-Sprache finden Sie unter [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md).  
  
 Weitere Informationen zum C\+\+\-Präprozessor finden Sie unter [C\/C\+\+\-Präprozessorreferenz](../preprocessor/c-cpp-preprocessor-reference.md).  
  
## C\+\+\-Bibliotheken in Visual Studio  
 Die folgenden Abschnitte enthalten Informationen über die verschiedenen C\+\+\-Bibliotheken.  
  
 [C\-Laufzeitbibliotheksverweis](../c-runtime-library/c-run-time-library-reference.md)  
 Umfasst Alternativen mit erhöhter Sicherheit für Funktionen, die bekanntermaßen Sicherheitsprobleme aufwerfen.  
  
 [C\+\+\-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)  
 Standard Template Library \(STL\).  
  
 [Active Template Library \(ATL\)](../atl/atl-com-desktop-components.md)  
 Unterstützung für COM\-Komponenten und Apps.  
  
 [Microsoft Foundation Class \(MFC\)\-Bibliotheken](../mfc/mfc-desktop-applications.md)  
 Unterstützung zur Erstellung von Desktop\-Apps mit herkömmlichen oder Office\-Formatbenutzeroberflächen.  
  
 [Parallel Patterns Library \(PPL\)](../parallel/concrt/parallel-patterns-library-ppl.md)  
 Asynchrone und parallele Algorithmen, die auf der CPU ausgeführt werden.  
  
 [C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)  
 Enorm parallele Algorithmen, die auf der GPU ausgeführt werden.  
  
 [Windows Runtime Template Library \(WRL\)](http://msdn.microsoft.com/library/windows/apps/hh438466.aspx)  
 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-Apps und \-Komponenten.  
  
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)  
 Programmierung für die Common Language Runtime \(CLR\).  
  
 Siehe auch die Dokumentation für [STL\/CLR](../dotnet/stl-clr-library-reference.md) und [C\+\+\-Unterstützungsbibliothek](../dotnet/cpp-support-library.md).  
  
## Weitere Visual C\+\+\-Bibliotheken  
 Dieser Abschnitt enthält Links zu Bibliotheken, die nicht in Visual Studio enthalten sind jedoch heruntergeladen und mit Visual C\+\+ verwendet werden können.  
  
 [Boost](http://www.boost.org/)  
 Eine beliebte und häufig verwendete Bibliothek.  
  
 [C\+\+\-REST\-SDK](http://casablanca.codeplex.com).  
 Eine Microsoft\-Bibliothek für die Kommunikation mit Webdiensten über HTTP.  
  
## Weitere Ressourcen  
 [Visual C\+\+\-Ressourcen](http://msdn.microsoft.com/vstudio/hh386302.aspx)  
 Weitere Visual C\+\+\-Ressourcen.  
  
 [Standard C\+\+](http://isocpp.org/)  
 Lernen Sie C\+\+ kennen, verschaffen Sie sich einen Überblick über das moderne C\+\+, und greifen Sie auf Links für Bücher, Artikel, Gespräche und Ereignisse zu.  
  
 [Visual C\+\+ kennen lernen](http://msdn.microsoft.com/vstudio/hh386302.aspx)  
 Beginnen Sie mit dem Erlernen von C\+\+.  
  
## Siehe auch  
 [C\-Sprachreferenz](../c-language/c-language-reference.md)   
 [C\-Laufzeitbibliotheksverweis](../c-runtime-library/c-run-time-library-reference.md)   
 [Intrinsische Compilerfunktionen und Assemblysprache](../intrinsics/compiler-intrinsics-and-assembly-language.md)