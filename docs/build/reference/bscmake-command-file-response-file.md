---
title: BSCMAKE-Befehlsdatei (Antwortdatei)
ms.date: 11/04/2016
helpviewer_keywords:
- BSCMAKE, response file
- BSCMAKE, command file
- response files, BSCMAKE
- command files, BSCMAKE
- response files
- command files
ms.assetid: abdffeea-35c7-4f2d-8c17-7d0d80bac314
ms.openlocfilehash: 6a55fd616a00aeb3ade229bf7cff8220f86085b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295044"
---
# <a name="bscmake-command-file-response-file"></a>BSCMAKE-Befehlsdatei (Antwortdatei)

> [!WARNING]
> Obwohl BSCMAKE weiterhin mit Visual Studio installiert wird, wird es nicht mehr von der IDE verwendet. Seit Visual Studio 2008 werden Browse- und Symbolinformationen automatisch in einer SQL Server-.SDF-Datei im Projektmappenordner gespeichert.

Sie können teilweise oder vollständig die Befehlszeileneingabe in einer Befehlsdatei bereitstellen. Geben Sie die Befehlsdatei, die mit der folgenden Syntax ein:

```
BSCMAKE @filename
```

Nur eine Befehlsdatei ist zulässig. Sie können einen Pfad angeben *Filename*. Vorausgehen *Filename* mit einem at-Zeichen (**\@**). BSCMAKE wird nicht davon eine Erweiterung aus. Sie können zusätzliche angeben *Sbrfiles* in der Befehlszeile nach *Filename*. Die Befehlsdatei ist eine Textdatei, die die Eingabe für BSCMAKE in der gleichen Reihenfolge enthält, wie Sie es in der Befehlszeile angeben möchten. Trennen Sie die Befehlszeilenargumente durch eine oder mehrere Leerzeichen, Tabstopps oder neue Zeilenumbruchzeichen an.

Der folgende Befehl ruft mithilfe einer Befehlsdatei BSCMAKE:

```
BSCMAKE @prog1.txt
```

Im folgenden finden eine Beispieldatei-Befehl:

```
/n /v /o main.bsc /El
/S (
toolbox.h
verdate.h c:\src\inc\screen.h
)
file1.sbr file2.sbr file3.sbr file4.sbr
```

## <a name="see-also"></a>Siehe auch

[BSCMAKE-Referenz](bscmake-reference.md)
