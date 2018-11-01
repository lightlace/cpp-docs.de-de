---
title: Compilerfehler C2231
ms.date: 11/04/2016
f1_keywords:
- C2231
helpviewer_keywords:
- C2231
ms.assetid: 677c5c66-d30f-4c3b-bbb9-760858d56477
ms.openlocfilehash: 0d6519bd12cdb5ee5a86fa4a6915b51b0dc59fc5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50592802"
---
# <a name="compiler-error-c2231"></a>Compilerfehler C2231

".": Linker Operand zeigt auf "Klassenschlüssel", verwenden Sie "->"

Der Operand auf der linken Seite des Vorgangs Memberauswahl (.) ist ein Zeiger und keine Klasse, Struktur oder Union.

Im folgenden Beispiel wird C2231 generiert:

```
// C2231.c
struct S {
   int member;
} s, *ps = &s;
int main() {
   ps.member = 0;   // C2231

   // OK
   ps->member = 0;   // crash
   s.member = 0;
}
```