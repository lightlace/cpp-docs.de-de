---
title: Compileroptionen | Microsoft Docs
ms.custom: 
ms.date: 01/29/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler
- x86 Visual C++ compiler
- ARM Visual C++ compiler
- compiler options, C++
- x64 Visual C++ compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4addd9f5dce819f554e6ab04707929a32f7b7d9d
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2018
---
# <a name="compiler-options"></a>Compileroptionen

CL.exe ist ein Tool, das die Microsoft Visual C++ (MSVC) C und C++-Compiler und Linker steuert. CL.exe kann nur unter Betriebssystemen ausgeführt werden, die Microsoft Visual Studio für Windows zu unterstützen.

> [!NOTE]  
> Sie können dieses Tool nur von Visual Studio Developer-Eingabeaufforderung starten. Sie können es nicht von einer Systemeingabeaufforderung oder vom Datei-Explorer aus starten. Weitere Informationen finden Sie unter [Erstellen von C/C++-Code in der Befehlszeile](../building-on-the-command-line.md).

Die Compiler erzeugen Objektdateien (OBJ-Dateien) im Common Object File Format (COFF). Der Linker generiert ausführbare Dateien (EXE-Dateien) oder DLLs (Dynamic Link Libraries).

Beachten Sie, dass bei allen Compileroptionen die Groß- und Kleinschreibung berücksichtigt wird. Sie können entweder einen Schrägstrich (`/`) oder einen Gedankenstrich (`-`) eine Compileroption angeben.

Verwenden Sie zum Kompilieren ohne Verknüpfen der [/c](../../build/reference/c-compile-without-linking.md) Option.

## <a name="find-a-compiler-option"></a>Eine Compileroption suchen

Wenn Sie eine bestimmte Compileroption suchen, ziehen Sie eine der folgenden Listen zu Rate:

- [Compileroptionen alphabetisch sortiert](../../build/reference/compiler-options-listed-alphabetically.md)

- [Compileroptionen nach Kategorien sortiert](../../build/reference/compiler-options-listed-by-category.md)

## <a name="specify-compiler-options"></a>Festlegen von Compileroptionen

In den Themen zu den einzelnen Compileroptionen wird erläutert, wie die jeweilige Option in der Entwicklungsumgebung eingestellt werden kann. Informationen über das Festlegen von Optionen außerhalb der Entwicklungsumgebung, finden Sie unter:

- [Syntax für die Compilerbefehlszeile](../../build/reference/compiler-command-line-syntax.md)

- [CL-Befehlsdateien](../../build/reference/cl-command-files.md)

- [CL-Umgebungsvariablen](../../build/reference/cl-environment-variables.md)

## <a name="related-build-tools"></a>Verwandte Buildtools

[Optionen des Linkers](../../build/reference/linker-options.md) außerdem Auswirkungen auf die Erstellungsweise des Programms.

## <a name="see-also"></a>Siehe auch

[Referenz zur C/C++-Erstellung](../../build/reference/c-cpp-building-reference.md)  
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)  
[Schnelle Kompilierung](../../build/reference/fast-compilation.md)  
[CL: Starten des Linkers](../../build/reference/cl-invokes-the-linker.md)  
