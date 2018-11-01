---
title: Compilerfehler C2228
ms.date: 11/04/2016
f1_keywords:
- C2228
helpviewer_keywords:
- C2228
ms.assetid: 901cadb1-ce90-4ae0-a360-547a9ba2ca18
ms.openlocfilehash: 20e295d09e39a12ed8163ec980fa304cd4167218
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628396"
---
# <a name="compiler-error-c2228"></a>Compilerfehler C2228

Links von '.identifier' muss eine Klasse/Struktur/Union stehen

Der Operand links vom Punktoperator (.) ist nicht an eine Klasse, Struktur oder Union.

Im folgenden Beispiel wird C2228 generiert:

```
// C2228.cpp
int i;
struct S {
public:
    int member;
} s, *ps = &s;

int main() {
   i.member = 0;   // C2228 i is not a class type
   ps.member = 0;  // C2228 ps is a pointer to a structure

   s.member = 0;   // s is a structure type
   ps->member = 0; // ps points to a structure S
}
```

Dieser Fehler wird auch angezeigt, wenn Sie bei der Verwendung von Managed Extensions fehlerhafte Syntax verwenden. Während Sie in anderen Visual Studio-Sprachen den Punktoperator für den Zugriff auf ein Member einer verwalteten Klasse verwenden können, bedeutet ein Zeiger auf das Objekt in C++, dass Sie den Operator '->' für den Zugriff auf das Member verwenden müssen:

Falsch: `String * myString = checkedListBox1->CheckedItems->Item[0].ToString();`

Richtig: `String * myString = checkedListBox1->CheckedItems->Item[0]->ToString();`