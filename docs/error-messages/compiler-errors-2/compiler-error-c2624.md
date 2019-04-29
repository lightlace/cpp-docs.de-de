---
title: Compilerfehler C2624
ms.date: 11/04/2016
f1_keywords:
- C2624
helpviewer_keywords:
- C2624
ms.assetid: 32f2ec15-a7cd-4049-a64b-131746d3152b
ms.openlocfilehash: 407629ad2eecd0d3ca6081fefa59ddd60702f913
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395481"
---
# <a name="compiler-error-c2624"></a>Compilerfehler C2624

lokale Klassen können nicht zum Deklarieren von Variablen in "Extern" verwendet werden

Eine lokale Klasse oder Struktur kann nicht zum Deklarieren verwendet werden `extern` Variablen.

Im folgende Beispiel wird die C2624 generiert:

```
// C2624.cpp
int main() {
   struct C {};
   extern C ac;   // C2624
}
```