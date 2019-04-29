---
title: MSVC C-/C++ compilerreferenz – Visual Studio
description: MSVC-Compiler-Toolset-Optionen.
ms.date: 12/10/2018
helpviewer_keywords:
- cl.exe compiler
- cl.exe compiler, setting options
ms.assetid: f3eef5ab-d0be-4fb2-90f9-927e6ed58736
ms.openlocfilehash: 2269ba69cea2702ff190c791eb6753acb3619f7d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294147"
---
# <a name="compiling-a-cc-project"></a>Kompilieren eines C/C++-Projekts

C- und C++-Compileroptionen können entweder in Visual Studio-IDE oder über die Befehlszeile festgelegt werden. 

## <a name="in-visual-studio"></a>In Visual Studio

Sie können Compileroptionen für jedes Projekt in der Visual Studio festlegen **Eigenschaftenseiten** Dialogfeld. Wählen Sie im linken Bereich **Konfigurationseigenschaften**, **C/C++-** und wählen Sie dann die Kategorie der Compiler-Option. In den Themen zu den einzelnen Compileroptionen wird erläutert, wo die jeweilige Option in der Entwicklungsumgebung zu finden ist und wie sie eingestellt werden kann. Finden Sie unter [MSVC-Compiler-Optionen](compiler-options.md) für eine vollständige Liste.

## <a name="from-the-command-line"></a>Über die Befehlszeile

Sie können die Optionen für den Compiler (CL.exe) an folgenden Stellen festlegen:

- [In der Befehlszeile](compiler-command-line-syntax.md)

- [In Befehlsdateien](cl-command-files.md)

- [In der CL-Umgebungsvariablen](cl-environment-variables.md)

Die in der CL-Umgebungsvariablen festgelegten Optionen werden bei jedem Aufrufen von CL.EXE verwendet. Wenn eine Befehlsdatei in der CL-Umgebungsvariablen oder in der Befehlszeile angegeben wird, werden die in der Befehlsdatei festgelegten Optionen verwendet. Anders als in der Befehlszeile oder in der CL-Umgebungsvariablen können Sie in einer Befehlsdatei mehrzeilige Optionen und Dateinamen verwenden.

Compileroptionen werden "von links nach rechts" verarbeitet. Wird ein Konflikt erkannt, überwiegt die letzte Option (ganz rechts). Die CL-Umgebungsvariable wird vor der Befehlszeile verarbeitet. Sollte es also zu Konflikten zwischen CL und der Befehlszeile kommen, so hat die Befehlszeile Vorrang.

## <a name="additional-compiler-topics"></a>Weitere Themen zum Compiler

- [MSVC-Compileroptionen](compiler-options.md)

- [Vorkompilierte Headerdateien](../creating-precompiled-header-files.md)

- [CL: Starten des Linkers](cl-invokes-the-linker.md)

Informationen zum Auswählen der Compiler Hostserver und-Zielserver-Architektur finden Sie unter [Konfigurieren von C++-Projekte für 64-Bit, X64 Ziele](../configuring-programs-for-64-bit-visual-cpp.md).

## <a name="see-also"></a>Siehe auch

[Referenz zur C/C++-Erstellung](c-cpp-building-reference.md)
