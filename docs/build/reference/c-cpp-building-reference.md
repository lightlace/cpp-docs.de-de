---
title: Referenz zur C/C++-Erstellung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- compiling source code [C++], additional information
- cl.exe compiler [C++], building programs
- linker [C++], building reference
- builds [C++], additional information
ms.assetid: 100b4ccf-572c-4d1f-970c-fa0bc0cc0d2d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e2269be27dd039357c11d38a2be83b5fc9d6504
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cc-building-reference"></a>Referenz zur C/C++-Erstellung
Visual C++ bietet zwei Methoden zum Erstellen eines C/C++-Programms. Die einfachste (und häufigste) besteht darin, [in der Visual C++-Entwicklungsumgebung erstellen](../../ide/building-cpp-projects-in-visual-studio.md). Eine andere Möglichkeit besteht darin [erstellen, die von einer Eingabeaufforderung mithilfe von Befehlszeilentools](../../build/building-on-the-command-line.md). In beiden Fällen können Sie mithilfe des Visual C++-Quellcode-Editors oder einer Drittanbieter-Editor Ihrer Wahl Quelldateien erstellen.  
  
 Wenn das Programm einem Makefile statt der VCXPROJ-Datei verwendet, Sie können weiterhin erstellen Sie sie in der Entwicklungsumgebung als ein [externen Projekt](../../ide/building-external-projects.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Kompilieren eines C/C++-Programms](../../build/reference/compiling-a-c-cpp-program.md)  
 Beschreibt den Compiler, der eine Objektdatei mit Computercode, Linkerdirektiven, Abschnitte, externe Verweise und Funktionsdaten/Namen erstellt.  
  
 [Verknüpfen](../../build/reference/linking.md)  
 Beschreibt den Linker an, der Code aus der vom Compiler erstellten Objektdateien und statisch verknüpfte Bibliotheken kombiniert wird, löst die Namensverweise, und erstellt eine ausführbare Datei.  
  
 [Releasebuilds](../../build/reference/release-builds.md)  
 Enthält Informationen dazu, wann und warum Sie ein Wechsel von möchten um einen Releasebuild zu erstellen und erörtert einige der Probleme, die möglicherweise auftreten, wenn von einem Debugbuild auf ein Releasebuild dahingehend ändern.  
  
 [Codeoptimierung](../../build/reference/optimizing-your-code.md)  
 Enthält Links zu Themen, in denen die Mechanismen zum Optimieren von Code:  
  
 [C/C++-Buildtools](../../build/reference/c-cpp-build-tools.md)  
 Bietet die folgenden Befehlszeilentools zum Anzeigen oder Bearbeiten von Buildausgabe an:  
  
 [C/C++-Buildfehler](../../error-messages/compiler-errors-1/c-cpp-build-errors.md)  
 Führt ein Buildfehlerabschnitt in der Tabelle des Inhalts.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [C/C++-Präprozessorreferenz](../../preprocessor/c-cpp-preprocessor-reference.md)  
 Erläutert den Präprozessor an, der Quelldateien für den Compiler wird vorbereitet, indem die Makros, Operatoren und Direktiven übersetzen.  
  
 [Grundlagen benutzerdefinierter Buildschritte und Buildereignisse](../../ide/understanding-custom-build-steps-and-build-events.md)  
 Erläutert das Anpassen des Buildprozesses.  
  
 [Erstellen eines C/C++-Programms](../../build/building-c-cpp-programs.md)  
 Bietet Links zu Themen, in denen das Erstellen von Programmen über die Befehlszeile oder die integrierte Entwicklungsumgebung von Visual Studio beschrieben sind.  
  
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)  
 Beschreibt, Festlegen von Compileroptionen in der Entwicklungsumgebung oder in der Befehlszeile angegeben.  
  
 [Compileroptionen](../../build/reference/compiler-options.md)  
 Enthält Links zu Themen über die Verwendung von Compileroptionen.  
  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)  
 Beschreibt, Festlegen von Linkeroptionen innerhalb oder außerhalb der integrierten Entwicklungsumgebung.  
  
 [Linkeroptionen](../../build/reference/linker-options.md)  
 Enthält Links zu Themen über die Verwendung der Optionen des Linkers.  
  
 [BSCMAKE-Referenz](../../build/reference/bscmake-reference.md)  
 Beschreibt das Microsoft Browse Information Maintenance-Dienstprogramm (BSCMAKE. EXE-Datei), erstellt die eine Browseinformationsdatei (.bsc) aus SBR-Dateien, die während der Kompilierung erstellt.  
  
 [LIB-Referenz](../../build/reference/lib-reference.md)  
 Beschreibt die Microsoft Bibliotheks-Manager (LIB.exe), das erstellt und verwaltet eine Bibliothek mit Objektdateien Common Object File Format (COFF).  
  
 [EDITBIN-Referenz](../../build/reference/editbin-reference.md)  
 Beschreibt die Microsoft COFF-Binär-Editor (EDITBIN. EXE-Datei), ändert die Binärdateien Common Object File Format (COFF).  
  
 [DUMPBIN-Referenz](../../build/reference/dumpbin-reference.md)  
 Beschreibt die Microsoft COFF-Binärdateidumper (DUMPBIN. (EXE) anzeigt, die Informationen zu den Binärdateien Common Object File Format (COFF).  
  
 [NMAKE-Referenz](../../build/nmake-reference.md)  
 Beschreibt das Microsoft Program Maintenance Utility (NMAKE. EXE-Datei), ist ein Tool, das Projekte erstellt basierend auf in einer Beschreibungsdatei enthaltenen Befehlen.