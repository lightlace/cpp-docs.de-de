---
title: Compilerfehler C3279
ms.date: 11/04/2016
f1_keywords:
- C3279
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
ms.openlocfilehash: 5f39510ee9ec0e717d675aa8b396405bc33b4ea1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445005"
---
# <a name="compiler-error-c3279"></a>Compilerfehler C3279

Teilweise oder explizite Spezialisierungen sowie explizite Instanziierungen von Klassenvorlagen, die im cli-Namespace deklariert sind, sind nicht zulässig.

Der `cli` -Namespace wird von Microsoft definiert und enthält Pseudovorlagen. Der Visual C++-Compiler lässt keine benutzerdefinierten partiellen und expliziten Spezialisierungen und keine expliziten Instanziierungen von Klassenvorlagen in diesem Namespace zu.

Im folgenden Beispiel wird C3279 generiert:

```
// C3279.cpp
// compile with: /clr
namespace cli {
   template <> ref class array<int> {};   // C3279
   template <typename T> ref class array<T, 2> {};   // C3279
}
```