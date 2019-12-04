---
title: Compilerfehler C2001
ms.date: 11/04/2016
f1_keywords:
- C2001
helpviewer_keywords:
- C2001
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
ms.openlocfilehash: 2bf9bd322812764b2f63493d4b22b58d853a25fa
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756837"
---
# <a name="compiler-error-c2001"></a>Compilerfehler C2001

Zeilen-Zeilen Ausdruck in konstanter Konstante

Eine Zeichen folgen Konstante kann in einer zweiten Zeile nur dann fortgesetzt werden, wenn Sie die folgenden Schritte ausführen:

- Beenden Sie die erste Zeile mit einem umgekehrten Schrägstrich.

- Schließen Sie die Zeichenfolge in der ersten Zeile mit einem doppelten Anführungszeichen, und öffnen Sie die Zeichenfolge in der nächsten Zeile mit einem weiteren doppelten Anführungszeichen.

Das Beenden der ersten Zeile mit \n ist nicht ausreichend.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2001 generiert:

```cpp
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

Leerzeichen am Anfang der nächsten Zeile nach einem Zeilen Fortsetzungs Zeichen sind in der Zeichen folgen Konstante enthalten. Keines der oben gezeigten Beispiele bettet ein Zeilen einzeitiges Zeichen in die Zeichen folgen Konstante ein. Wie hier gezeigt, können Sie ein Zeilen Trennzeichen einbetten:

```cpp
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
