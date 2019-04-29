---
title: Linkertoolwarnung LNK4254
ms.date: 11/04/2016
f1_keywords:
- LNK4254
helpviewer_keywords:
- LNK4254
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
ms.openlocfilehash: 2c68e49d58b0fd6b28607eb0ba78c092441f6f4b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352488"
---
# <a name="linker-tools-warning-lnk4254"></a>Linkertoolwarnung LNK4254

Abschnitt 'Abschnitt1' (Offset), die in "" section2"zusammengeführt (offset), mit verschiedenen Attributen

Der Inhalt von einem Abschnitt mit einer anderen zusammengeführt wurden, aber die Attribute der beiden Abschnitte sind unterschiedlich. Das Programm möglicherweise unerwartete Ergebnisse zurückgibt. Beispielsweise können Daten zu lesen, werden nur jetzt in eine schreibbare Abschnitt sein.

Um LNK4254 zu beheben, ändern Sie oder entfernen Sie die Merge-Anforderung aus.

Wenn X86 auf Computern und Windows CE-Plattformen (ARM, MIPS, SH4 und Ziehpunkt) mit Visual C++, die. CRT-Abschnitt ist schreibgeschützt. Wenn Ihr Code auf dem vorherigen Verhalten abhängt (. CRT-Abschnitte sind Lese-/Schreibzugriff), kann unerwartetes Verhalten angezeigt.

Weitere Informationen finden Sie unter

- [/MERGE (Abschnitte kombinieren)](../../build/reference/merge-combine-sections.md)

- [comment (C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die LNK4254 generiert.

```
// LNK4254.cpp
// compile with: /W1 /link /WX
// LNK4254 expected
#pragma comment(linker, "/merge:.data=.text")
int main() {}
```