---
title: Compilerfehler C2766
ms.date: 11/04/2016
f1_keywords:
- C2766
helpviewer_keywords:
- C2766
ms.assetid: 8032f4ca-6827-4f04-9c61-c44643c85cc4
ms.openlocfilehash: 87ea9f693265080d744746c6a8014b2b8b6db13a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50446488"
---
# <a name="compiler-error-c2766"></a>Compilerfehler C2766

explizite Spezialisierung; "Spezialisierung" wurde bereits definiert.

Doppelte explizite spezialisierungen sind nicht zulässig. Weitere Informationen finden Sie unter [explizite Spezialisierung von Funktionsvorlagen](../../cpp/explicit-specialization-of-function-templates.md).

Im folgende Beispiel wird die C2766 generiert:

```
// C2766.cpp
// compile with: /c
template<class T>
struct A {};

template<>
struct A<int> {};

template<>
struct A<int> {};   // C2766
// try the following line instead
// struct A<char> {};
```