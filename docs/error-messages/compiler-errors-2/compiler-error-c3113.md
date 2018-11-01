---
title: Compilerfehler C3113
ms.date: 11/04/2016
f1_keywords:
- C3113
helpviewer_keywords:
- C3113
ms.assetid: 3afdc668-b29e-474e-9ea3-aa027d42db7c
ms.openlocfilehash: b8edd31db87587887d9e96522802ee9091caab91
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659159"
---
# <a name="compiler-error-c3113"></a>Compilerfehler C3113

"Struktur" darf keine Vorlagen-/generische sein.

Sie haben versucht, eine Klassenvorlage oder eine Klasse aus einer Schnittstelle oder einer Enumeration generisch zu gestalten.

Im folgende Beispiel wird die C3113 generiert:

```
// C3113.cpp
// compile with: /c
template <class T>
enum E {};   // C3113
// try the following line instead
// class MyClass{};
```