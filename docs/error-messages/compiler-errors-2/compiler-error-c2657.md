---
title: Compilerfehler C2657
ms.date: 11/04/2016
f1_keywords:
- C2657
helpviewer_keywords:
- C2657
ms.assetid: f7cf29a9-684a-4605-9469-ecfee9ba4b03
ms.openlocfilehash: 4e2816092b3c0c210ae2c544e9bf9a823a9c5d18
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661135"
---
# <a name="compiler-error-c2657"></a>Compilerfehler C2657

' Klasse:: * "zu Beginn einer Anweisung gefunden (fehlt die Typangabe?)

Die Zeile beginnt mit einem Zeiger-auf-Member-Bezeichner.

Dieser Fehler kann durch ein fehlender Typspezifizierer in der Deklaration eines Zeigers auf einem Member verursacht werden.

Im folgende Beispiel wird die C2657 generiert:

```
// C2657.cpp
class C {};
int main() {
   C::* pmc1;        // C2657
   int C::* pmc2;   // OK
}
```