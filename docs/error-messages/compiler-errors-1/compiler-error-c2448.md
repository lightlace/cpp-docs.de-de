---
title: Compilerfehler C2448
ms.date: 11/04/2016
f1_keywords:
- C2448
helpviewer_keywords:
- C2448
ms.assetid: e255df3c-f861-4b4d-a193-8768cef061a5
ms.openlocfilehash: 8a71fe05e2a046a65b659840f94d104a3c526778
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744159"
---
# <a name="compiler-error-c2448"></a>Compilerfehler C2448

"Bezeichner": Funktions Stil-Initialisierer scheint eine Funktionsdefinition zu sein

Die Funktionsdefinition ist falsch.

Dieser Fehler kann durch eine formale Liste im alten C-Format verursacht werden.

Im folgenden Beispiel wird C2448 generiert:

```cpp
// C2448.cpp
void func(c)
   int c;
{}   // C2448
```
