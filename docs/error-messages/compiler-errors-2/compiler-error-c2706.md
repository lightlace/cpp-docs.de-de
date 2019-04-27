---
title: Compilerfehler C2706
ms.date: 11/04/2016
f1_keywords:
- C2706
helpviewer_keywords:
- C2706
ms.assetid: e18da924-c42d-4b09-8e29-f4e0382d7dc6
ms.openlocfilehash: 9767d36d44b99423d600d299d0803901d3dbfec5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161107"
---
# <a name="compiler-error-c2706"></a>Compilerfehler C2706

illegal __except ohne Übereinstimmung \__finally (fehlende '}' in \__finally Block?)

Der Compiler wurde nicht gefunden für eine schließende geschweifte Klammer für eine `__try` Block.

Im folgende Beispiel wird die C2706 generiert:

```
// C2706.cpp
int main() {
   __try {
      void f();
   // C2706  } missing here
   __except(GetExceptionCode() == 0x0) {
   }
}
```