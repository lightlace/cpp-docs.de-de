---
title: Compilerfehler C3279
ms.date: 11/04/2016
f1_keywords:
- C3279
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
ms.openlocfilehash: 3025dbf7c6bf4701218c2d9a956cae26d7180848
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757604"
---
# <a name="compiler-error-c3279"></a>Compilerfehler C3279

Teilweise oder explizite Spezialisierungen sowie explizite Instanziierungen von Klassenvorlagen, die im cli-Namespace deklariert sind, sind nicht zulässig.

Der `cli` -Namespace wird von Microsoft definiert und enthält Pseudovorlagen. Der Microsoft C++ -Compiler lässt keine benutzerdefinierten, partiellen und expliziten Spezialisierungs-und expliziten Instanziierungen von Klassen Vorlagen in diesem Namespace zu.

Im folgenden Beispiel wird C3279 generiert:

```cpp
// C3279.cpp
// compile with: /clr
namespace cli {
   template <> ref class array<int> {};   // C3279
   template <typename T> ref class array<T, 2> {};   // C3279
}
```
