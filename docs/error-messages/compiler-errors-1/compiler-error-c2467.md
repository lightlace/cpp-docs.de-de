---
title: Compilerfehler C2467
ms.date: 11/04/2016
f1_keywords:
- C2467
helpviewer_keywords:
- C2467
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
ms.openlocfilehash: aa45cbb19519dea7bd5c8fb96abd2c76ea30a786
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598024"
---
# <a name="compiler-error-c2467"></a>Compilerfehler C2467

Ungültige Deklaration des anonymen '– benutzerdefinierte-Typ'

Ein geschachtelter Typ mit den benutzerdefinierten deklariert wurde. Dies ist ein Fehler beim Kompilieren von C-Quellcode mit ANSI-Kompatibilitätsoption ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) aktiviert.

Im folgende Beispiel wird die C2467 generiert:

```
//C2467.c
// compile with: /Za
int main() {
   struct X {
      union { int i; };   // C2467, nested declaration
   };
}
```