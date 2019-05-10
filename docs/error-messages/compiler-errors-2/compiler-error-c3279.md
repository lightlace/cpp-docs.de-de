---
title: Compilerfehler C3279
ms.date: 11/04/2016
f1_keywords:
- C3279
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
ms.openlocfilehash: 72646d7611163748fe7e27ea6c78cd38426eb6ad
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447813"
---
# <a name="compiler-error-c3279"></a>Compilerfehler C3279

Teilweise oder explizite Spezialisierungen sowie explizite Instanziierungen von Klassenvorlagen, die im cli-Namespace deklariert sind, sind nicht zulässig.

Der `cli` -Namespace wird von Microsoft definiert und enthält Pseudovorlagen. Microsoft C++ Compiler lässt keine benutzerdefinierten partiellen und expliziten spezialisierungen sowie explizite Instanziierungen von Klassenvorlagen in diesem Namespace zu.

Im folgenden Beispiel wird C3279 generiert:

```
// C3279.cpp
// compile with: /clr
namespace cli {
   template <> ref class array<int> {};   // C3279
   template <typename T> ref class array<T, 2> {};   // C3279
}
```