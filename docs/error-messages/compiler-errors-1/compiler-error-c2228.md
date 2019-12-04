---
title: Compilerfehler C2228
ms.date: 11/04/2016
f1_keywords:
- C2228
helpviewer_keywords:
- C2228
ms.assetid: 901cadb1-ce90-4ae0-a360-547a9ba2ca18
ms.openlocfilehash: 56eed6aeff5a955253a440d5931d66118f4604e0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759281"
---
# <a name="compiler-error-c2228"></a>Compilerfehler C2228

Links von '.identifier' muss eine Klasse/Struktur/Union stehen

Der Operand auf der linken Seite des Zeitraums (.) ist keine Klasse, Struktur oder Union.

Im folgenden Beispiel wird C2228 generiert:

```cpp
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
