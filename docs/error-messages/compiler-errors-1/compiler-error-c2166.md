---
title: Compilerfehler C2166
ms.date: 11/04/2016
f1_keywords:
- C2166
helpviewer_keywords:
- C2166
ms.assetid: 12789c3a-cc76-48bb-ae2e-64283e0964ed
ms.openlocfilehash: 36b4bcbd3eda213b840194cb635172a241f04b14
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174718"
---
# <a name="compiler-error-c2166"></a>Compilerfehler C2166

L-Wert gibt ein const-Objekt an

Code versucht, ein als `const`deklariertes Element zu ändern.

Im folgenden Beispiel wird C2166 generiert:

```
// C2166.cpp
int f();
int main() {
   ( (const int&) 1 ) = 5;   // C2166
}
```