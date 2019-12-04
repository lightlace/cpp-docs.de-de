---
title: Compilerfehler C2844
ms.date: 11/04/2016
f1_keywords:
- C2844
helpviewer_keywords:
- C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
ms.openlocfilehash: fdfd2200503f80addb120117ce06f5f837d6b9f2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752014"
---
# <a name="compiler-error-c2844"></a>Compilerfehler C2844

"Member": kann kein Member der Schnittstelle "Interface" sein.

Eine [Schnittstellen Klasse](../../extensions/interface-class-cpp-component-extensions.md) kann keinen Datenmember enthalten, es sei denn, Sie ist auch eine Eigenschaft.

In einer Schnittstelle ist nichts anderes als eine Eigenschaft oder eine Member-Funktion zulässig. Außerdem sind Konstruktoren, Dekonstruktoren und Operatoren nicht zulässig.

Im folgenden Beispiel wird C2844 generiert:

```cpp
// C2844a.cpp
// compile with: /clr /c
public interface class IFace {
   int i;   // C2844
   // try the following line instead
   // property int Size;
};
```
