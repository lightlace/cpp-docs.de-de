---
title: Compilerwarnung (Stufe 1) C4183
ms.date: 11/04/2016
f1_keywords:
- C4183
helpviewer_keywords:
- C4183
ms.assetid: dc48312c-4b34-44dd-80ff-eb5f11d5ca47
ms.openlocfilehash: be79c664f09f80d8f0c8779babf236dccac90ea8
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626230"
---
# <a name="compiler-warning-level-1-c4183"></a>Compilerwarnung (Stufe 1) C4183

' Identifier ': fehlender Rückgabetyp. angenommen, eine Member-Funktion gibt "int" zurück.

Die Inline Definition einer Member-Funktion in einer Klasse oder einer Struktur weist keinen Rückgabetyp auf. Bei dieser Member-Funktion wird davon ausgegangen, dass der Standard Rückgabetyp `int`ist.

Im folgenden Beispiel wird C4183 generiert:

```cpp
// C4183.cpp
// compile with: /W1 /c
#pragma warning(disable : 4430)
class MyClass1;
class MyClass2 {
   MyClass1() {};   // C4183
};
```