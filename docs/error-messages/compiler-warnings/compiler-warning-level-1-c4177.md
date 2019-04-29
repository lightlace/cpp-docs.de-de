---
title: Compilerwarnung (Stufe 1) C4177
ms.date: 11/04/2016
f1_keywords:
- C4177
helpviewer_keywords:
- C4177
ms.assetid: 2b05a5b3-696e-4f21-818e-227b9335e748
ms.openlocfilehash: 5c8f3dc37c76ad0d016108b792ee61c67cce63d1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391659"
---
# <a name="compiler-warning-level-1-c4177"></a>Compilerwarnung (Stufe 1) C4177

\#Pragma-Pragma sollte sich im globalen Gültigkeitsbereich befinden.

Das [pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) -Pragma sollte nicht innerhalb eines lokalen Gültigkeitsbereichs verwendet werden. Das **Pragma** ist erst gültig, wenn der globale Gültigkeitsbereich im Anschluss an den aktuellen Bereich gefunden wurde.

Im folgenden Beispiel wird C4177 generiert.

```
// C4177.cpp
// compile with: /W1
// #pragma bss_seg("global")   // OK

int main() {
   #pragma bss_seg("local")    // C4177
}
```