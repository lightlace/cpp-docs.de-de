---
title: Compilerfehler C3413
ms.date: 11/04/2016
f1_keywords:
- C3413
helpviewer_keywords:
- C3413
ms.assetid: de6c9b05-c373-4bd8-8cb0-12c2cd2e5674
ms.openlocfilehash: e344d06345c0f3a79b86e9cab4e1c5dacb47e9c2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173423"
---
# <a name="compiler-error-c3413"></a>Compilerfehler C3413

'name': Ungültige explizite Instanziierung

Der Compiler hat eine explizite Instanziierung in einem ungültigen Format erkannt.

Im folgenden Beispiel wird C3413 generiert:

```
// C3413.cpp
template
class MyClass {};   // C3413
```

Mögliche Lösung:

```
// C3413b.cpp
// compile with: /c
template <class T>
class MyClass {};

template <>
class MyClass<int> {};
```