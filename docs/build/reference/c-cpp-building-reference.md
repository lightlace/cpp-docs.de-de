---
title: Referenz zur C/C++-Erstellung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- compiling source code [C++], additional information
- cl.exe compiler [C++], building programs
- linker [C++], building reference
- builds [C++], additional information
ms.assetid: 100b4ccf-572c-4d1f-970c-fa0bc0cc0d2d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 116ddca6ed9f5e0b3ea02652958931f88cc8fc13
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703221"
---
# <a name="cc-building-reference"></a>Referenz zur C/C++-Erstellung

Visual C++ bietet zwei Möglichkeiten zum Erstellen eines C/C++-Programms. Die einfachste (und am häufigsten verwendete) Möglichkeit ist [innerhalb der Visual C++-Entwicklungsumgebung erstellen](../../ide/building-cpp-projects-in-visual-studio.md). Die andere Möglichkeit besteht darin [erstellen, die über eine Eingabeaufforderung, die mithilfe von Befehlszeilentools](../../build/building-on-the-command-line.md). In beiden Fällen können Sie Ihre Quelldateien, die mithilfe der Visual C++-Quellcode-Editor oder einem Drittanbieter-Editor Ihrer Wahl erstellen.

Wenn Ihr Programm eine VCXPROJ-Datei, anstatt ein Makefile verwendet wird, können Sie immer noch erstellen sie in der Entwicklungsumgebung als ein [externen Projekt](../../ide/building-external-projects.md).

## <a name="in-this-section"></a>In diesem Abschnitt

[Kompilieren eines C/C++-Programms](../../build/reference/compiling-a-c-cpp-program.md) beschreibt den Compiler an, die eine Objektdatei mit Computercode, Linkerdirektiven, Abschnitte, externe Verweise und Namen von Funktionen/Daten erstellt.

[Verknüpfen von](../../build/reference/linking.md) beschreibt den Linker an, der Code aus der Objektdateien, die vom Compiler erstellt wird und statisch verknüpfte Bibliotheken kombiniert wird, löst die Namensverweise und erstellt eine ausführbare Datei.

[Releasebuilds](../../build/reference/release-builds.md) zeigt Informationen zu warum und wann Sie von einem Debugbuild in ein Releasebuild ändern möchten, und erörtert einige der Probleme auftreten, wenn von einer Debugversion in einem Releasebuild ändern.

[Optimieren Sie Ihren Code](../../build/reference/optimizing-your-code.md) enthält Links zu Themen, in denen die Mechanismen zur Optimierung von Code:

[C/C++-Buildtools](../../build/reference/c-cpp-build-tools.md) bietet die folgenden Befehlszeilentools zum Anzeigen oder Bearbeiten von Build-Ausgabe:

[C/C++-Buildfehler](../../error-messages/compiler-errors-1/c-cpp-build-errors.md) führt den Abschnitt über Build Fehler in der Tabelle des Inhalts.

## <a name="related-sections"></a>Verwandte Abschnitte

[Referenz zur C/C++-Präprozessor](../../preprocessor/c-cpp-preprocessor-reference.md) beschreibt den Präprozessor an, die Quelldateien für den Compiler vorbereitet, durch die Übersetzung von Makros, Operatoren und Anweisungen.

[Grundlagen benutzerdefinierter Buildschritte und Buildereignisse](../../ide/understanding-custom-build-steps-and-build-events.md) Anpassen des Buildprozesses erläutert.

[Erstellen eines C/C++-Programms](../../build/building-c-cpp-programs.md) enthält Links zu Themen, in denen die programmerstellung über die Befehlszeile oder aus der integrierten Entwicklungsumgebung von Visual Studio.

[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md) Festlegen von Compileroptionen in der Entwicklungsumgebung oder in der Befehlszeile beschrieben.

[Compileroptionen](../../build/reference/compiler-options.md) enthält Links zu Themen über die Verwendung von Compileroptionen.

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md) wird beschrieben, Festlegen von Linkeroptionen innerhalb oder außerhalb der integrierten Entwicklungsumgebung.

[Optionen des Linkers](../../build/reference/linker-options.md) enthält Links zu Themen über die Verwendung der Optionen des Linkers.

[BSCMAKE-Referenz](../../build/reference/bscmake-reference.md) beschreibt das Microsoft Browse Information Maintenance-Dienstprogramm (BSCMAKE. (EXE), erstellt die eine Browseinformationsdatei (.bsc) aus SBR-Dateien, die während der Kompilierung erstellt.

[LIB-Referenz](../../build/reference/lib-reference.md) wird beschrieben, die Microsoft Bibliotheksverwaltung (LIB.exe), die erstellt und verwaltet eine Bibliothek mit Objektdateien Common Object File Format (COFF).

[EDITBIN-Referenz](../../build/reference/editbin-reference.md) wird beschrieben, die Microsoft COFF-Binärdatei-Editor (EDITBIN. (EXE), ändert der Binärdateien Common Object File Format (COFF).

[DUMPBIN-Referenz](../../build/reference/dumpbin-reference.md) wird beschrieben, die Microsoft COFF-Binärdateidumper (DUMPBIN. (EXE), zeigt die Informationen über Common Object File Format (COFF)-Binärdateien.

[NMAKE-Referenz](../../build/nmake-reference.md) beschreibt das Microsoft Program Maintenance Utility (NMAKE. (EXE), dies ist ein Tool, das Projekte erstellt basierend auf in einer Beschreibungsdatei enthaltenen Befehlen.