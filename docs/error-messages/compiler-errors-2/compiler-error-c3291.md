---
title: Compilerfehler C3291
ms.date: 11/04/2016
f1_keywords:
- C3291
helpviewer_keywords:
- C3291
ms.assetid: ed2e9f89-8dbc-4387-bc26-cc955e840858
ms.openlocfilehash: eb98be3677de6c93fdb7bedf7c0d482115891697
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760139"
---
# <a name="compiler-error-c3291"></a>Compilerfehler C3291

"default": Kann nicht der Name einer trivial-Eigenschaft sein.

Eine trivial-Eigenschaft kann nicht als `default`benannt werden. Weitere Informationen finden Sie unter [property](../../extensions/property-cpp-component-extensions.md) .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3291 generiert:

```cpp
// C3291.cpp
// compile with: /clr /c
ref struct C {
   property System::String ^ default;   // C3291
   property System::String ^ Default;   // OK
};
```
