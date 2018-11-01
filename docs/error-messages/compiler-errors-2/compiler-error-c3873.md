---
title: Compilerfehler C3873
ms.date: 11/04/2016
f1_keywords:
- C3873
helpviewer_keywords:
- C3873
ms.assetid: e68fd3be-2391-492b-ac3f-d2428901b2e9
ms.openlocfilehash: eb2a6935073c3b4a2b9eb3d9b099b372cfa34303
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467356"
---
# <a name="compiler-error-c3873"></a>Compilerfehler C3873

„char“: Dieses Zeichen ist nicht als erstes Zeichen eines Bezeichners zulässig.

Der C++-Compiler folgt hinsichtlich Zeichen, die in einem Bezeichner zulässig sind, dem C++11-Standard. Nur bestimmte Bereiche von Zeichen und universelle Zeichennamen sind in einem Bezeichner zulässig. Zusätzliche Einschränkungen gelten für das erste Zeichen eines Bezeichners. Weitere Informationen hierzu und eine Liste der zulässigen Zeichen sowie Bereiche universeller Zeichennamen finden Sie unter [Identifiers](../../cpp/identifiers-cpp.md).

Der Bereich der in einem Bezeichner zulässigen Zeichen ist weniger restriktiv, wenn C++ /CLI-Code kompiliert wird. Bezeichner in Code, der mit „/clr“ kompiliert wurde, müssen dem folgenden Standard entsprechen:  [Standard ECMA-335: Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).

Im folgenden Beispiel wird C3873 generiert:

```
// C3873.cpp
int main() {
   int \u036F_abc;   // C3873, not in allowed range for initial character
   int abc_\u036F;   // OK, in allowed range for non-initial character
}
```