---
title: "Referenz zur C/C++-Erstellung"
ms.custom: na
ms.date: "12/03/2016"
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
  - "Builds [C++], Weitere Informationen"
  - "cl.exe-Compiler [C++], Erstellen von Programmen"
  - "Kompilieren von Quellcode [C++], Weitere Informationen"
  - "Linker [C++], Referenz zur Erstellung"
ms.assetid: 100b4ccf-572c-4d1f-970c-fa0bc0cc0d2d
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Referenz zur C/C++-Erstellung
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Es gibt zwei Möglichkeiten, mit Visual C\+\+ ein C\/C\+\+\-Programm zu erstellen.  Die einfachste \(und verbreitetste\) Methode besteht darin, das Programm [in der Visual C\+\+\-Entwicklungsumgebung zu erstellen](../../ide/building-cpp-projects-in-visual-studio.md).  Es ist jedoch auch die [Erstellung über eine Befehlszeile mithilfe von Befehlszeilentools](../../build/building-on-the-command-line.md) möglich.  In jedem Fall können die Quelldateien mit dem Visual C\+\+\-Quellcode\-Editor oder einem beliebigen Editor eines Drittanbieters erstellt werden.  
  
 Wenn Ihr Programm anstelle einer VCXPROJ\-Datei ein Makefile verwendet, können Sie es trotzdem als [externes Projekt](../../ide/building-external-projects.md) in der Entwicklungsumgebung erstellen.  
  
## In diesem Abschnitt  
 [Kompilieren eines C\/C\+\+\-Programms](../../build/reference/compiling-a-c-cpp-program.md)  
 Beschreibt den Compiler, der eine Objektdatei erstellt, die Computercode, Linkerdirektiven, Abschnitte, externe Verweise und Namen für Funktionen\/Daten enthält.  
  
 [Linken](../../build/reference/linking.md)  
 Beschreibt den Linker, der Code aus den vom Compiler erstellten Objektdateien mit Code aus statisch verknüpften Bibliotheken kombiniert, Namensverweise auflöst und eine ausführbare Datei erstellt.  
  
 [Releasebuilds](../../build/reference/release-builds.md)  
 Enthält Informationen dazu, warum und wann ein Wechsel von einem Debugbuild zu einem Releasebuild angeraten sein kann, und erörtert einige der Probleme, die beim Wechsel von einem Debug\- zu einem Releasebuild auftreten können:  
  
 [Codeoptimierung](../../build/reference/optimizing-your-code.md)  
 Enthält Links zu Themen, in denen Mechanismen zur Codeoptimierung behandelt werden:  
  
 [C\/C\+\+\-Buildtools](../../build/reference/c-cpp-build-tools.md)  
 Stellt die folgenden Befehlszeilentools zur Verfügung, um Buildausgaben anzuzeigen und zu bearbeiten:  
  
 [C\/C\+\+\-Buildfehler](../../error-messages/compiler-errors-1/c-cpp-build-errors.md)  
 Einführung zum Buildfehlerabschnitt im Inhaltsverzeichnis.  
  
## Verwandte Abschnitte  
 [C\/C\+\+\-Präprozessorreferenz](../../preprocessor/c-cpp-preprocessor-reference.md)  
 Beschreibt den Präprozessor, der die Quelldateien für den Compiler vorbereitet, indem er Makros, Operatoren und Direktiven übersetzt.  
  
 [Grundlagen benutzerdefinierter Buildschritte und Buildereignisse](../../ide/understanding-custom-build-steps-and-build-events.md)  
 Erörtert das Anpassen des Buildprozesses.  
  
 [Erstellen eines C\/C\+\+\-Programms](../../build/building-c-cpp-programs.md)  
 Enthält Links zu Themen, in denen die Programmerstellung über die Befehlszeile oder in der integrierten Entwicklungsumgebung von Visual Studio beschrieben wird.  
  
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)  
 Beschreibt das Einstellen von Compileroptionen in der Entwicklungsumgebung oder über die Befehlszeile.  
  
 [Compileroptionen](../../build/reference/compiler-options.md)  
 Enthält Links zu Themen, in denen die Verwendung von Compileroptionen erörtert wird.  
  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)  
 Beschreibt das Einstellen von Linkeroptionen innerhalb oder außerhalb der integrierten Entwicklungsumgebung.  
  
 [Linkeroptionen](../../build/reference/linker-options.md)  
 Enthält Links zu Themen, in denen die Verwendung von Linkeroptionen erörtert wird.  
  
 [BSCMAKE\-Referenz](../../build/reference/bscmake-reference.md)  
 Beschreibt das Microsoft Browse Information Maintenance\-Dienstprogramm \(BSCMAKE.EXE\), das aus SBR\-Dateien, die während der Kompilierung angelegt werden, eine Browserinformationsdatei \(.bsc\) erstellt.  
  
 [LIB\-Referenz](../../build/reference/lib-reference.md)  
 Beschreibt den Bibliotheks\-Manager von Microsoft \(LIB.EXE\), der eine Bibliothek mit Objektdateien im COFF\-Format \(Common Object File Format\) erstellt und verwaltet.  
  
 [EDITBIN\-Referenz](../../build/reference/editbin-reference.md)  
 Beschreibt den COFF\-Binärdatei\-Editor von Microsoft \(EDITBIN.EXE\), der Binärdateien im COFF\-Format \(Common Object File Format\) bearbeitet.  
  
 [DUMPBIN\-Referenz](../../build/reference/dumpbin-reference.md)  
 Beschreibt das Anzeigeprogramm für Binärdateien von Microsoft \(DUMPBIN.EXE\), das Informationen über Binärdateien im COFF\-Format \(Common Object File Format\) anzeigt.  
  
 [NMAKE\-Referenz](../../build/nmake-reference.md)  
 Beschreibt das Microsoft Program Maintenance Utility \(NMAKE.EXE\), ein Tool, das Projekte basierend auf Befehlen erstellt, die in einer Beschreibungsdatei enthalten sind.