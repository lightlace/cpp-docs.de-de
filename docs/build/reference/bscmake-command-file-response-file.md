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
ms.openlocfilehash: 43f5a886dd41941a0675e31bc8c9d3f23c607023
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57426237"
---
# <a name="bscmake-command-file-response-file"></a>BSCMAKE-Befehlsdatei (Antwortdatei)

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

[BSCMAKE-Referenz](../../build/reference/bscmake-reference.md)
