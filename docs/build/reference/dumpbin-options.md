---
title: DUMPBIN-Optionen
ms.date: 10/24/2019
f1_keywords:
- dumpbin
helpviewer_keywords:
- DUMPBIN program, options
ms.assetid: 563b696e-7599-4480-94b9-014776289ec8
ms.openlocfilehash: 81c66f1971294531a2904a0b681819476bcc1eb2
ms.sourcegitcommit: 6ed1bc5b26dc60a780c1fc5f2f19d57ba1dc47d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73144558"
---
# <a name="dumpbin-options"></a>DUMPBIN-Optionen

Eine Option besteht aus einem *optionsspezifizierer*, bei dem es sich entweder um einen Bindestrich (`-`) oder einen Schrägstrich (`/`) handelt, gefolgt vom Namen der Option. Optionsnamen können nicht abgekürzt werden. Einige Optionen übernehmen Argumente, die nach einem Doppelpunkt (`:`) angegeben sind. Innerhalb einer Optionsangabe sind keine Leerzeichen oder Tabstopps zulässig. Verwenden Sie eines oder mehrere Leerzeichen bzw. Tabstopps, um Optionsangaben in der Befehlszeile voneinander zu trennen. Bei Optionsnamen und Schlüsselwörtern oder Dateinamen Argumenten wird die Groß-/Kleinschreibung nicht beachtet. Die meisten Optionen gelten für alle Binärdateien, aber ein paar gilt nur für bestimmte Dateitypen. Standardmäßig sendet DUMPBIN die Informationen an die Standardausgabe. Verwenden Sie die Option [/out](out-dumpbin.md) , um die Ausgabe an eine Datei zu senden.

## <a name="options-list"></a>Options Liste

DUMPBIN hat die folgenden Optionen:

- [/ALL](all.md)

- [/ARCHIVEMEMBERS](archivemembers.md)

- [/CLRHEADER](clrheader.md)

- [/DEPENDENTS](dependents.md)

- [/DIRECTIVES](directives.md)

- [/DISASM\[: {Bytes\|nobytes}\]](disasm.md)

- [/ERRORREPORT: {None | Eingabeaufforderung | Warteschlange | Aussendet](errorreport-dumpbin-exe.md)

- [/EXPORTS](dash-exports.md)

- [/FPO](fpo.md)

- [/HEADERS](headers.md)

- [/Imports\[: Dateiname\]](imports-dumpbin.md)

- [/LINENUMBERS](linenumbers.md)

- [/LINKERMEMBER\[: {1 | 2}\]](linkermember.md)

- [/LOADCONFIG](loadconfig.md)

- [/NOPDB](nopdb.md)

- [/Out: Dateiname](out-dumpbin.md)

- [/PDATA](pdata.md)

- [/PDBPATH\[: Ausführliche\]](pdbpath.md)

- [/RANGEE: vamin\[, vamax\]](range.md)

- [/RawData\[: {None\|1\|2\|4\|8}\[, #\]\]](rawdata.md)

- [/RELOCATIONS](relocations.md)

- [/Section: Name](section-dumpbin.md)

- [/SUMMARY](summary.md)

- [/SYMBOLS](symbols.md)

- [/TLS](tls.md)

Verwenden Sie zum Auflisten der Optionen, die von DUMPBIN in der Befehlszeile unterstützt werden, das **/?** andere.

## <a name="see-also"></a>Siehe auch

[Zusätzliche MSVC-Buildtools](c-cpp-build-tools.md)\
[DUMPBIN-Befehlszeilen](dumpbin-command-line.md)\
[DUMPBIN-Referenz](dumpbin-reference.md)
