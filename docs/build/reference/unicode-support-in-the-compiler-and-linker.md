---
title: Unicode-Unterstützung im Compiler und Linker
ms.date: 12/15/2017
f1_keywords:
- VC.Project.VCLinkerTool.UseUnicodeResponseFiles
- VC.Project.VCLibrarianTool.UseUnicodeResponseFiles
- VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles
- VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles
helpviewer_keywords:
- Unicode, Visual C++
ms.openlocfilehash: 71458ab345670c0a5715576a7da80c4e6ff2955b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317327"
---
# <a name="unicode-support-in-the-compiler-and-linker"></a>Unicode-Unterstützung im Compiler und Linker

Die meisten Visual C++ Buildtools unterstützt Unicode-Eingaben und Ausgaben.

## <a name="filenames"></a>Dateinamen

Dateinamen angegeben, in der Befehlszeile oder in compileranweisungen (wie z. B. `#include`) können Unicode-Zeichen enthalten.

## <a name="source-code-files"></a>Quellcodedateien

Unicode-Zeichen werden in Bezeichnern, Makros, Zeichenfolgen und Zeichenliteralen sowie in Kommentaren unterstützt.  Universelle Zeichennamen werden ebenfalls unterstützt.

Unicode kann in den folgenden Codierungen in eine Quellcodedatei eingegeben werden:

- UTF-16-Little-Endian mit oder ohne Bytereihenfolgemarkierung (BOM)

- UTF-16-Big-Endian mit oder ohne BOM

- UTF-8 mit BOM

## <a name="output"></a>Output

Während der Kompilierung gibt der Compiler diagnosemeldungen an die Konsole in UTF-16.  Welche Zeichen auf Ihrer Konsole angezeigt werden können, ist von den Eigenschaften des Konsolenfensters abhängig.  Die in eine Datei umgeleitete Compilerausgabe entspricht der aktuellen ANSI-Konsolencodepage.

## <a name="linker-response-files-and-def-files"></a>Antwortdateien für den Linker und DEF-Dateien

Antwortdateien und DEF-Dateien können entweder UTF-16 mit einer Bytereihenfolge-Marke oder ANSI sein.

## <a name="asm-and-cod-dumps"></a>ASM- und COD-Dumps

ASM- und COD-Dumps müssen standardmäßig in ANSI sein, damit die Kompatibilität mit MASM gewährleistet ist. Verwendung [/FAu](fa-fa-listing-file.md) zur Ausgabe von UTF-8. Beachten Sie, dass bei Angabe von **/FAS**, die vermischte Quelle einfach direkt ausgegeben und verstümmelt aussehen kann, z. B. wenn Quellcode UTF-8 ist und Sie nicht angeben, **/FAsu**.

## <a name="see-also"></a>Siehe auch

[Verwenden des MSVC-Toolsets über die Befehlszeile](../building-on-the-command-line.md)