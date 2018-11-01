---
title: Referenz zur C/C++-Erstellung
ms.date: 11/04/2016
helpviewer_keywords:
- compiling source code [C++], additional information
- cl.exe compiler [C++], building programs
- linker [C++], building reference
- builds [C++], additional information
ms.assetid: 100b4ccf-572c-4d1f-970c-fa0bc0cc0d2d
ms.openlocfilehash: 36f261ee993932d1a08d5cdb02e2d4681ae60f0c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481730"
---
# <a name="cc-building-reference"></a>Referenz zur C/C++-Erstellung

Visual C++ bietet zwei Möglichkeiten zum Erstellen eines C/C++-Programms. Die einfachste (und am häufigsten verwendete) Möglichkeit ist [innerhalb der Visual C++-Entwicklungsumgebung erstellen](../../ide/building-cpp-projects-in-visual-studio.md). Die andere Möglichkeit besteht darin [erstellen, die über eine Eingabeaufforderung, die mithilfe von Befehlszeilentools](../../build/building-on-the-command-line.md). In beiden Fällen können Sie Ihre Quelldateien, die mithilfe der Visual C++-Quellcode-Editor oder einem Drittanbieter-Editor Ihrer Wahl erstellen.

Wenn Ihr Programm eine VCXPROJ-Datei, anstatt ein Makefile verwendet wird, können Sie immer noch erstellen sie in der Entwicklungsumgebung als ein [externen Projekt](../../ide/building-external-projects.md).

## <a name="in-this-section"></a>In diesem Abschnitt

[Kompilieren eines C/C++-Programms](../../build/reference/compiling-a-c-cpp-program.md)<br/>
Beschreibt den Compiler, der eine Objektdatei mit Computercode, Linkerdirektiven, Abschnitte, externe Verweise und Namen von Funktionen/Daten erstellt.

[Verknüpfen](../../build/reference/linking.md)<br/>
Beschreibt den Linker an, der Code aus der Objektdateien, die vom Compiler erstellt wird und statisch verknüpfte Bibliotheken kombiniert wird, löst die Namensverweise, und erstellt eine ausführbare Datei.

[Releasebuilds](../../build/reference/release-builds.md)<br/>
Enthält Informationen dazu, warum und wann Sie von einem Debugbuild ändern möchten, einen Releasebuild zu erstellen und erörtert einige der Probleme, die möglicherweise auftreten, wenn von einer Debugversion in einem Releasebuild ändern.

[Codeoptimierung](../../build/reference/optimizing-your-code.md)<br/>
Enthält Links zu Themen, in denen die Mechanismen zur Optimierung von Code:

[C/C++-Buildtools](../../build/reference/c-cpp-build-tools.md)<br/>
Bietet die folgenden Befehlszeilentools zum Anzeigen oder Bearbeiten von Build-Ausgabe:

[C/C++-Buildfehler](../../error-messages/compiler-errors-1/c-cpp-build-errors.md)<br/>
Führt den Abschnitt über Build Fehler in der Tabelle des Inhalts an.

## <a name="related-sections"></a>Verwandte Abschnitte

[C/C++-Präprozessorreferenz](../../preprocessor/c-cpp-preprocessor-reference.md)<br/>
Beschreibt den Präprozessor an, der Quelldateien für den Compiler vorbereitet, durch die Übersetzung von Makros, Operatoren und Anweisungen an.

[Grundlagen benutzerdefinierter Buildschritte und Buildereignisse](../../ide/understanding-custom-build-steps-and-build-events.md)<br/>
Beschreibt das Anpassen des Buildprozesses.

[Erstellen eines C/C++-Programms](../../build/building-c-cpp-programs.md)<br/>
Bietet Links zu Themen, in denen das Erstellen von Programmen über die Befehlszeile oder die integrierte Entwicklungsumgebung von Visual Studio beschrieben sind.

[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
Beschreibt, Festlegen von Compileroptionen in der Entwicklungsumgebung oder in der Befehlszeile.

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
Enthält Links zu Themen über die Verwendung von Compileroptionen.

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
Beschreibt, Festlegen von Linkeroptionen innerhalb oder außerhalb der integrierten Entwicklungsumgebung.

[Linkeroptionen](../../build/reference/linker-options.md)<br/>
Enthält Links zu Themen über die Verwendung der Optionen des Linkers.

[BSCMAKE-Referenz](../../build/reference/bscmake-reference.md)<br/>
Beschreibt das Microsoft Browse Information Maintenance-Dienstprogramm (BSCMAKE. (EXE), erstellt die eine Browseinformationsdatei (.bsc) aus SBR-Dateien, die während der Kompilierung erstellt.

[LIB-Referenz](../../build/reference/lib-reference.md)<br/>
Beschreibt die Microsoft Bibliotheksverwaltung (LIB.exe), die erstellt und verwaltet eine Bibliothek mit Objektdateien Common Object File Format (COFF).

[EDITBIN-Referenz](../../build/reference/editbin-reference.md)<br/>
Beschreibt die Microsoft COFF-Binär-Editor (EDITBIN. (EXE), ändert der Binärdateien Common Object File Format (COFF).

[DUMPBIN-Referenz](../../build/reference/dumpbin-reference.md)<br/>
Beschreibt die Microsoft COFF-Binärdateidumper (DUMPBIN. (EXE), zeigt die Informationen über Common Object File Format (COFF)-Binärdateien.

[NMAKE-Referenz](../../build/nmake-reference.md)<br/>
Beschreibt das Microsoft Program Maintenance Utility (NMAKE. (EXE), dies ist ein Tool, das Projekte erstellt basierend auf in einer Beschreibungsdatei enthaltenen Befehlen.