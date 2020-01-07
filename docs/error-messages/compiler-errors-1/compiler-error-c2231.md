---
title: Compilerfehler C2231
ms.date: 11/04/2016
f1_keywords:
- C2231
helpviewer_keywords:
- C2231
ms.assetid: 677c5c66-d30f-4c3b-bbb9-760858d56477
ms.openlocfilehash: 50230b3a9b609d281cddf996783287c270f844d5
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301820"
---
# <a name="compiler-error-c2231"></a>Compilerfehler C2231

".": der linke Operand zeigt auf "Class-Key", verwenden Sie "->".

Der Operand links vom Elementauswahl Vorgang (.) ist ein Zeiger anstelle einer Klasse, Struktur oder Union.

Im folgenden Beispiel wird C2231 generiert:

```c
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
