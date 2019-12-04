---
title: Compilerfehler C2766
ms.date: 11/04/2016
f1_keywords:
- C2766
helpviewer_keywords:
- C2766
ms.assetid: 8032f4ca-6827-4f04-9c61-c44643c85cc4
ms.openlocfilehash: 48faee02bba18754972954a2ca464417bd552758
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759801"
---
# <a name="compiler-error-c2766"></a>Compilerfehler C2766

explizite Spezialisierung; "Spezialisierung" wurde bereits definiert.

Doppelte explizite Spezialisierung sind nicht zulässig. Weitere Informationen finden Sie unter [explizite Spezialisierung von Funktions Vorlagen](../../cpp/explicit-specialization-of-function-templates.md).

Im folgenden Beispiel wird C2766 generiert:

```cpp
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
