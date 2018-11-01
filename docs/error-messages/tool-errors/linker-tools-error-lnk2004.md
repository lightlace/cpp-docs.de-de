---
title: Linkertoolfehler LNK2004
ms.date: 11/04/2016
f1_keywords:
- LNK2004
helpviewer_keywords:
- LNK2004
ms.assetid: 07645371-e67b-4a2c-b0e0-dde24c94ef7e
ms.openlocfilehash: 37eb01b5dd8266bce34e1a932271d5d9a9d15c52
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529323"
---
# <a name="linker-tools-error-lnk2004"></a>Linkertoolfehler LNK2004

Gp relativer Fixup-Überlauf zu 'Ziel'; short-Abschnitt "Abschnitt" ist zu groß ist oder außerhalb des gültigen Bereichs.

Der Abschnitt war zu groß.

Um diesen Fehler zu beheben, verringern Sie die Größe der short-Abschnitts, indem Sie Daten explizit in der long-Abschnitten mit #pragma-Abschnitt (".sectionname", read, Write, Long) einfügen und `__declspec(allocate(".sectionname"))` für Definitionen und Deklarationen.  Ein auf ein Objekt angewendeter

```
#pragma section(".data$mylong", read, write, long)
__declspec(allocate(".data$mylong"))
char    rg0[1] = { 1 };
char    rg1[2] = { 1 };
char    rg2[4] = { 1 };
char    rg3[8] = { 1 };
char    rg4[16] = { 1 };
char    rg5[32] = { 1 };
```

Sie können auch logisch gruppierte Daten in ihre eigene Struktur verschieben, die eine Sammlung von Daten, die mehr als 8 Bytes, die der Compiler in einem long-Daten-Abschnitt zuweist.  Ein auf ein Objekt angewendeter

```
// from this...
int     w1  = 23;
int     w2 = 46;
int     w3 = 23*3;
int     w4 = 23*4;

// to this...
struct X {
    int     w1;
    int     w2;
    int     w3;
    int     w4;
} x  = { 23, 23*2, 23*3, 23*4 };

```

Diesem Fehler folgt der schwerwiegende Fehler `LNK1165`.