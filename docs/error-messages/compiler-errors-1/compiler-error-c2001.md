---
title: Compilerfehler C2001
ms.date: 11/04/2016
f1_keywords:
- C2001
helpviewer_keywords:
- C2001
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
ms.openlocfilehash: 03b54fe2373063c8c0f9905da93822928392998d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596364"
---
# <a name="compiler-error-c2001"></a>Compilerfehler C2001

Zeilenvorschub in Konstante.

Eine Zeichenfolgenkonstante kann nicht in einer zweiten Zeile fortgesetzt werden, es sei denn, Sie folgendermaßen vor:

- Das Ende der ersten Zeile mit einem umgekehrten Schrägstrich.

- Schließen Sie die Zeichenfolge in der ersten Zeile mit einem doppelten Anführungszeichen, und öffnen Sie ein weiteres doppeltes Anführungszeichen der Zeichenfolge in der nächsten Zeile.

Beenden die erste Zeile \n ist nicht ausreichend.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2001 generiert:

```
// C2001.cpp
// C2001 expected
#include <stdio.h>

int main()
{
    printf_s("Hello,
             world");
    printf_s("Hello,\n
             world");
}
```

## <a name="example"></a>Beispiel

Leerzeichen am Anfang der nächsten Zeile nach der ein Zeilenfortsetzungszeichen sind in Zeichenfolgenkonstanten enthalten. Keine der oben aufgeführten Beispiele betten Sie ein neue Zeilenumbruchzeichen in die Zeichenfolgenkonstante. Sie können ein Zeilenumbruchzeichen einbetten, wie hier gezeigt:

```
// C2001b.cpp
#include <stdio.h>

int main()
{
    printf_s("Hello,\n\
             world");

    printf_s("Hello,\
             \nworld");

    printf_s("Hello,\n"
             "world");

    printf_s("Hello,"
             "\nworld");

    printf_s("Hello,"
             " world");

    printf_s("Hello,\
             world");
}
```