---
title: Unicode-Unterstützung im Compiler und Linker | Microsoft Docs
ms.custom: ''
ms.date: 12/15/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.UseUnicodeResponseFiles
- VC.Project.VCLibrarianTool.UseUnicodeResponseFiles
- VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles
- VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles
dev_langs:
- C++
helpviewer_keywords:
- Unicode, Visual C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec0b84cd62f3fcca378ab55de16006925e685b37
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="unicode-support-in-the-compiler-and-linker"></a>Unicode-Unterstützung im Compiler und Linker

Die meisten Visual C++-Buildtools unterstützt Unicode-Eingaben und Ausgaben.

## <a name="filenames"></a>Dateinamen

Dateinamen angegeben, in der Befehlszeile oder in Compilerdirektiven (wie z. B. `#include`) können Unicode-Zeichen enthalten.

## <a name="source-code-files"></a>Quellcodedateien

Unicode-Zeichen werden in Bezeichnern, Makros, Zeichenfolgen und Zeichenliteralen sowie in Kommentaren unterstützt.  Universelle Zeichennamen werden ebenfalls unterstützt.

Unicode kann in den folgenden Codierungen in eine Quellcodedatei eingegeben werden:

- UTF-16-Little-Endian mit oder ohne Bytereihenfolgemarkierung (BOM)

- UTF-16-Big-Endian mit oder ohne BOM

- UTF-8 mit BOM

## <a name="output"></a>Ausgabe

Während der Kompilierung gibt der Compiler diagnosemeldungen an die Konsole in UTF-16.  Welche Zeichen auf Ihrer Konsole angezeigt werden können, ist von den Eigenschaften des Konsolenfensters abhängig.  Die in eine Datei umgeleitete Compilerausgabe entspricht der aktuellen ANSI-Konsolencodepage.

## <a name="linker-response-files-and-def-files"></a>Antwortdateien für den Linker und DEF-Dateien

Antwortdateien und DEF-Dateien können entweder UTF-16 mit einer BOM oder ANSI sein.

## <a name="asm-and-cod-dumps"></a>ASM- und COD-Dumps

ASM- und COD-Dumps müssen standardmäßig in ANSI sein, damit die Kompatibilität mit MASM gewährleistet ist. Verwendung [/FAu für](../../build/reference/fa-fa-listing-file.md) zur Ausgabe von UTF-8. Beachten Sie, dass bei Angabe von **Angabe von/FAS**, die vermischte Quelle einfach direkt ausgegeben wird und verstümmelt aussehen kann, z. B. wenn Quellcode UTF-8 ist und Sie angegeben haben **/FAsu**.

## <a name="see-also"></a>Siehe auch

[Erstellen von C/C++-Code in der Befehlszeile](../../build/building-on-the-command-line.md)