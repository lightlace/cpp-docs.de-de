---
title: Compilerfehler C2231
ms.date: 11/04/2016
f1_keywords:
- C2231
helpviewer_keywords:
- C2231
ms.assetid: 677c5c66-d30f-4c3b-bbb9-760858d56477
ms.openlocfilehash: 0d6519bd12cdb5ee5a86fa4a6915b51b0dc59fc5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383307"
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