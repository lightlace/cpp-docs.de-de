---
title: Referenz zur C/C++-Erstellung – Visual Studio
description: Referenzmaterial für C/C++-Projekt und die Build Tools in Visual Studio.
ms.date: 12/10/2018
helpviewer_keywords:
- compiling source code [C++], additional information
- cl.exe compiler [C++], building programs
- linker [C++], building reference
- builds [C++], additional information
ms.assetid: 100b4ccf-572c-4d1f-970c-fa0bc0cc0d2d
ms.openlocfilehash: 4c3f7aa598a9c43af04c148ed0d4b3f555566ec7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294758"
---
# <a name="cc-building-reference"></a>Referenz zur C/C++-Erstellung

Visual C++ bietet zwei Möglichkeiten zum Erstellen eines C/C++-Programms. Die einfachste (und am häufigsten verwendete) Möglichkeit ist [Entwicklung innerhalb von Visual Studio-IDE](../creating-and-managing-visual-cpp-projects.md). Die andere Möglichkeit besteht darin [erstellen, die über eine Eingabeaufforderung, die mithilfe von Befehlszeilentools](../building-on-the-command-line.md). In beiden Fällen können Sie erstellen und bearbeiten Ihre Quelldateien, die mit Visual Studio oder ein Drittanbieter-Editor Ihrer Wahl.

## <a name="in-this-section"></a>In diesem Abschnitt

[MSBuild-Referenz für C++-Projekte](msbuild-visual-cpp-overview.md)

[MSVC-Compilerreferenz](compiling-a-c-cpp-program.md)<br/>
Beschreibt die MSVC-Compiler, der eine Objektdatei mit Computercode, Linkerdirektiven, Abschnitte, externe Verweise und Namen von Funktionen/Daten erstellt.

[MSVC-Linkerreferenz](linking.md)<br/>
Beschreibt den Linker an, der Code aus der Objektdateien, die vom Compiler erstellt wird und statisch verknüpfte Bibliotheken kombiniert wird, löst die Namensverweise, und erstellt eine ausführbare Datei.

[Unicode-Unterstützung im Compiler und Linker](unicode-support-in-the-compiler-and-linker.md)

[Zusätzliche MSVC-Buildtools](c-cpp-build-tools.md)<br/>
Weitere Befehlszeilenprogramme für C++.

[C/C++-Buildfehler](../../error-messages/compiler-errors-1/c-cpp-build-errors.md)<br/>
Führt den Abschnitt über Build Fehler in der Tabelle des Inhalts an.

## <a name="related-sections"></a>Verwandte Abschnitte

[C/C++-Präprozessorreferenz](../../preprocessor/c-cpp-preprocessor-reference.md)<br/>
Beschreibt den Präprozessor an, der Quelldateien für den Compiler vorbereitet, durch die Übersetzung von Makros, Operatoren und Anweisungen an.

[Grundlagen benutzerdefinierter Buildschritte und Buildereignisse](../understanding-custom-build-steps-and-build-events.md)<br/>
Beschreibt das Anpassen des Buildprozesses.

[Erstellen eines C/C++-Programms](../projects-and-build-systems-cpp.md)<br/>
Bietet Links zu Themen, in denen das Erstellen von Programmen über die Befehlszeile oder die integrierte Entwicklungsumgebung von Visual Studio beschrieben sind.

[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
Beschreibt, Festlegen von Compileroptionen in der Entwicklungsumgebung oder in der Befehlszeile.

[MSVC-Compileroptionen](compiler-options.md)<br/>
Enthält Links zu Themen über die Verwendung von Compileroptionen.

[MSVC-Linkerreferenz](linking.md)<br/>
Beschreibt, Festlegen von Linkeroptionen innerhalb oder außerhalb der integrierten Entwicklungsumgebung.

[MSVC-Linkeroptionen](linker-options.md)<br/>
Enthält Links zu Themen über die Verwendung der Optionen des Linkers.

[BSCMAKE-Referenz](bscmake-reference.md)<br/>
Beschreibt das Microsoft Browse Information Maintenance-Dienstprogramm (BSCMAKE. (EXE), erstellt die eine Browseinformationsdatei (.bsc) aus SBR-Dateien, die während der Kompilierung erstellt.

[LIB-Referenz](lib-reference.md)<br/>
Beschreibt die Microsoft Bibliotheksverwaltung (LIB.exe), die erstellt und verwaltet eine Bibliothek mit Objektdateien Common Object File Format (COFF).

[EDITBIN-Referenz](editbin-reference.md)<br/>
Beschreibt die Microsoft COFF-Binär-Editor (EDITBIN. (EXE), ändert der Binärdateien Common Object File Format (COFF).

[DUMPBIN-Referenz](dumpbin-reference.md)<br/>
Beschreibt die Microsoft COFF-Binärdateidumper (DUMPBIN. (EXE), zeigt die Informationen über Common Object File Format (COFF)-Binärdateien.

[NMAKE-Referenz](nmake-reference.md)<br/>
Beschreibt das Microsoft Program Maintenance Utility (NMAKE. (EXE), dies ist ein Tool, das Projekte erstellt basierend auf in einer Beschreibungsdatei enthaltenen Befehlen.
