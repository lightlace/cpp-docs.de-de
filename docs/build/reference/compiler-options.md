---
title: MSVC-Compiler-Optionen
ms.date: 01/29/2018
helpviewer_keywords:
- cl.exe compiler
- x86 MSVC compiler
- ARM MSVC compiler
- compiler options, C++
- x64 MSVC compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
ms.openlocfilehash: 831aade72cd728ec42aee5ef1f320deb7bdf173d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294264"
---
# <a name="compiler-options"></a>Compileroptionen

CL.exe ist ein Tool, das Microsoft Visual C++ (MSVC) C und C++-Compiler und Linker steuert. CL.exe kann nur auf Betriebssystemen ausgeführt werden, die Microsoft Visual Studio für Windows zu unterstützen.

> [!NOTE]
> Sie können dieses Tool nur von Visual Studio Developer-Eingabeaufforderung starten. Sie können es nicht von einer Systemeingabeaufforderung oder vom Datei-Explorer aus starten. Weitere Informationen finden Sie unter [verwenden Sie das MSVC-Toolset, über die Befehlszeile](../building-on-the-command-line.md).

Die Compiler erzeugen Objektdateien (OBJ-Dateien) im Common Object File Format (COFF). Der Linker generiert ausführbare Dateien (EXE-Dateien) oder DLLs (Dynamic Link Libraries).

Beachten Sie, dass bei allen Compileroptionen die Groß- und Kleinschreibung berücksichtigt wird. Sie können entweder einen Schrägstrich verwenden (`/`) oder einen Gedankenstrich (`-`) an eine Compileroption.

Verwenden Sie zum Kompilieren ohne Verknüpfen der [/c](c-compile-without-linking.md) Option.

## <a name="find-a-compiler-option"></a>Eine Compileroption suchen

Wenn Sie eine bestimmte Compileroption suchen, ziehen Sie eine der folgenden Listen zu Rate:

- [Compileroptionen alphabetisch sortiert](compiler-options-listed-alphabetically.md)

- [Compileroptionen nach Kategorien sortiert](compiler-options-listed-by-category.md)

## <a name="specify-compiler-options"></a>Geben Sie Optionen für den compiler

In den Themen zu den einzelnen Compileroptionen wird erläutert, wie die jeweilige Option in der Entwicklungsumgebung eingestellt werden kann. Informationen über das Festlegen von Optionen außerhalb der Entwicklungsumgebung, finden Sie unter:

- [Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)

- [CL-Befehlsdateien](cl-command-files.md)

- [CL-Umgebungsvariablen](cl-environment-variables.md)

## <a name="related-build-tools"></a>Verwandte Buildtools

[Optionen des Linkers MSVC](linker-options.md) außerdem Auswirkungen auf die Erstellungsweise des Programms.

## <a name="see-also"></a>Siehe auch

[Referenz zur C/C++-Erstellung](c-cpp-building-reference.md)<br/>
[CL: Starten des Linkers](cl-invokes-the-linker.md)
