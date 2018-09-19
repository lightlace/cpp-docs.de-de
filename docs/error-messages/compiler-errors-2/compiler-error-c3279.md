---
title: Compilerfehler C3279 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3279
dev_langs:
- C++
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 89c537da9bcf91e7774353cc1516a4c44e28649c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056767"
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