---
title: Compilerfehler C3062
ms.date: 11/04/2016
f1_keywords:
- C3062
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
ms.openlocfilehash: 9b1fbc8f4ca2ce3434a30e833f4741bc17015bbb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749528"
---
# <a name="compiler-error-c3062"></a>Compilerfehler C3062

' Enumeration ': der Enumerator erfordert einen Wert, da der zugrunde liegende Typ ' type ' ist.

Sie können einen zugrunde liegenden Typ für eine Enumeration angeben. Einige Typen erfordern jedoch, dass Sie jedem Enumerator Werte zuweisen.

Weitere Informationen zu Enumerationen finden Sie unter [Enumerationsklasse](../../extensions/enum-class-cpp-component-extensions.md).

Im folgenden Beispiel wird C3062 generiert:

```cpp
// C3062.cpp
// compile with: /clr

enum class MyEnum : bool { a };   // C3062
enum class MyEnum2 : bool { a = true};   // OK
```
