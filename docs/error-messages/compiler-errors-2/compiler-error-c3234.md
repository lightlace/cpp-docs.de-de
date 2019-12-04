---
title: Compilerfehler C3234
ms.date: 11/04/2016
f1_keywords:
- C3234
helpviewer_keywords:
- C3234
ms.assetid: ebefc15a-e40d-424b-a3dd-d7e185d0ed7b
ms.openlocfilehash: acfbd44444270f90ae79f498724fcec14aa408ac
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751091"
---
# <a name="compiler-error-c3234"></a>Compilerfehler C3234

Eine generische Klasse kann nicht von einem generischen Typparameter abgeleitet werden.

Eine generische Klasse kann nicht von einem generischen Typparameter erben.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3234 generiert:

```cpp
// C3234.cpp
// compile with: /clr /c
generic <class T>
public ref class C : T {};   // C3234
// try the following line instead
// public ref class C {};
```
