---
title: /SYMBOLS
ms.date: 09/05/2018
f1_keywords:
- /symbols
helpviewer_keywords:
- symbols, dumping
- public symbols
- symbols, displaying COFF symbol table
- symbol tables
- SYMBOLS dumpbin option
- /SYMBOLS dumpbin option
- -SYMBOLS dumpbin option
ms.assetid: 34bcae90-4561-4c77-a80c-065508dec39a
ms.openlocfilehash: a47b7da9f0b01353ef15e8b5c070c19e7c521c37
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822547"
---
# <a name="symbols"></a>/SYMBOLS

```
/SYMBOLS
```

Diese Option zeigt die COFF-Symboltabelle. Symboltabellen, die in allen Objektdateien vorhanden sind. Nur dann, wenn sie "/ Debug" verknüpft ist, wird in einer Bilddatei eine COFF-Symboltabelle angezeigt.

Im folgenden finden eine Beschreibung der Ausgabe für/Symbols. Weitere Informationen zur Bedeutung der/Symbols Ausgabe kann anhand der in "Winnt.h" (IMAGE_SYMBOL und IMAGE_AUX_SYMBOL) oder in COFF-Dokumentation gefunden werden.

Betrachten Sie das folgende Beispiel-Abbild:

```
Dump of file main.obj
File Type: COFF OBJECT

COFF SYMBOL TABLE
000 00000000 DEBUG    notype       Filename     | .file
    main.cpp
002 000B1FDB ABS      notype       Static       | @comp.id
003 00000000 SECT1    notype       Static       | .drectve
    Section length     26, #relocs    0, #linenums    0, checksum 722C964F
005 00000000 SECT2    notype       Static       | .text
    Section length     23, #relocs    1, #linenums    0, checksum 459FF65F, selection    1 (pick no duplicates)
007 00000000 SECT2    notype ()    External     | _main
008 00000000 UNDEF    notype ()    External     | ?MyDump@@YAXXZ (void __cdecl MyDump(void))

String Table Size = 0x10 bytes

  Summary

         26 .drectve
         23 .text
```

## <a name="remarks"></a>Hinweise

Die folgende Beschreibung für die Zeilen, die beginnen mit einer Zahl Symbol, werden die Spalten mit Informationen, die relevant für Benutzer beschrieben:

- Die erste dreistellige Zahl ist die Symbol Indexnummer.

- Wenn die dritte Spalte SECT enthält*x*, das Symbol wird im Abschnitt über die Objektdatei definiert. Aber wenn UNDEF angezeigt wird, nicht in dieses Objekt definiert ist und an anderer Stelle behoben werden müssen.

- Die fünfte Spalte (statisch und extern) informiert, ob das Symbol nur innerhalb dieses Objekt sichtbar ist, oder gibt an, ob er öffentlich ist (sichtbar extern). Ein statisches Symbol, _sym wäre nicht mit einem öffentlichen Symboldateien _sym verknüpft sein; Dies wäre, dass zwei verschiedene Instanzen der Funktionen, die mit dem Namen _sym.

Die letzte Spalte in einer nummerierten Zeile den Symbolnamen, beide versehen und nicht ergänzten Form.

Nur die [/Headers](headers.md) DUMPBIN-Option ist verfügbar für die Verwendung in Dateien mit der ["/ GL"](gl-whole-program-optimization.md) -Compileroption.

## <a name="see-also"></a>Siehe auch

[DUMPBIN-Optionen](dumpbin-options.md)
