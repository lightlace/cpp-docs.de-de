---
title: Compilerfehler C2147
ms.date: 11/04/2016
f1_keywords:
- C2147
helpviewer_keywords:
- C2147
ms.assetid: d1adb3bf-7ece-4815-922c-ad7492fb6670
ms.openlocfilehash: 0af88d89ff264ca9efd02477a62e5bd7532271bd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756486"
---
# <a name="compiler-error-c2147"></a>Compilerfehler C2147

Syntax Fehler: "Bezeichner" ist ein neues Schlüsselwort.

Ein Bezeichner wurde verwendet, der jetzt ein reserviertes Schlüsselwort in der Sprache ist.

Im folgenden Beispiel wird C2147 generiert:

```cpp
// C2147.cpp
// compile with: /clr
int main() {
   int gcnew = 0;   // C2147
   int i = 0;   // OK
}
```
