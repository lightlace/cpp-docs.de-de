---
title: Compilerwarnung (Stufe 1) C4407
ms.date: 11/04/2016
f1_keywords:
- C4407
helpviewer_keywords:
- C4407
ms.assetid: 32bc2c21-363a-4bb8-b486-725faeaededc
ms.openlocfilehash: 5142e3800f3ad716166a27e3b0407a40999b5746
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436828"
---
# <a name="compiler-warning-level-1-c4407"></a>Compilerwarnung (Stufe 1) C4407

Umwandeln von verschiedenen Zeigern in Memberrepräsentationen, kann Compiler falschen Code generieren

Es wurde eine falsche Typumwandlung erkannt.

C4407 kann aufgrund einer konformitätsverbesserung für Compiler generiert werden, die in Visual C++ 2005 durchgeführt wurde. Pointer-to-Member erfordert jetzt ein qualifizierter Name und Address-of-Operators (&).

C4407 kann auftreten, wenn Sie die Umwandlung zwischen einem mehrere Vererbung Pointer-to-Member auf eine einzelne Vererbung Pointer-to-Member. Manchmal kann dies funktionieren, aber manchmal es nicht möglich, da die einfache Vererbung Pointer-to-Member-Darstellung über ausreichende Informationen enthalten, nicht. Beim Kompilieren mit der **/VMM** kann hilfreich sein (Weitere Informationen finden Sie unter [/VMM, / VMs, / vmv (allgemeine Darstellung)](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)). Sie können auch versuchen, die Basisklassen Neuanordnen; der Compiler ist ein Verlust von Informationen bei der Konvertierung erkannt werden, da an einem NULL-Offset von der abgeleiteten Basisklasse ist.

Im folgende Beispiel wird die C4407 generiert:

```
// C4407.cpp
// compile with: /W1 /c
struct C1 {};
struct C2 {};
struct C3 : C1, C2 {};

typedef void(C3::*PMF_C3)();
typedef void(C2::*PMF_C2)();

PMF_C2 f1(PMF_C3 pmf) {
   return (PMF_C2)pmf;   // C4407, change type of cast,
   // or reverse base class inheritance of C3 (i.e. : C2, C1)
}
```