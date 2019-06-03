---
title: Compilerfehler C3873
ms.date: 11/04/2016
f1_keywords:
- C3873
helpviewer_keywords:
- C3873
ms.assetid: e68fd3be-2391-492b-ac3f-d2428901b2e9
ms.openlocfilehash: ca70af12ef3223c8c5950f0fa98b1c63a2dd3a4c
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450819"
---
# <a name="compiler-error-c3873"></a>Compilerfehler C3873

„char“: Dieses Zeichen ist nicht als erstes Zeichen eines Bezeichners zulässig.

Der C++-Compiler folgt hinsichtlich Zeichen, die in einem Bezeichner zulässig sind, dem C++11-Standard. Nur bestimmte Bereiche von Zeichen und universelle Zeichennamen sind in einem Bezeichner zulässig. Zusätzliche Einschränkungen gelten für das erste Zeichen eines Bezeichners. Weitere Informationen hierzu und eine Liste der zulässigen Zeichen sowie Bereiche universeller Zeichennamen finden Sie unter [Identifiers](../../cpp/identifiers-cpp.md).

Der Bereich der in einem Bezeichner zulässigen Zeichen ist weniger restriktiv, wenn C++ /CLI-Code kompiliert wird. Im Code mit/CLR kompiliert entsprechen [Standard ECMA-335: Common Language Infrastructure (CLI)](https://www.ecma-international.org/publications/standards/Ecma-335.htm).

Im folgenden Beispiel wird C3873 generiert:

```
// C3873.cpp
int main() {
   int \u036F_abc;   // C3873, not in allowed range for initial character
   int abc_\u036F;   // OK, in allowed range for non-initial character
}
```