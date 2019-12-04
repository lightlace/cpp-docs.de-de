---
title: Compilerfehler C3640
ms.date: 11/04/2016
f1_keywords:
- C3640
helpviewer_keywords:
- C3640
ms.assetid: fcc56894-0f98-48af-8561-3bf7c7b2b93f
ms.openlocfilehash: 73f353aff42afdee649104d9f578c9061d236d1f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742482"
---
# <a name="compiler-error-c3640"></a>Compilerfehler C3640

"Member": eine referenzierte oder virtuelle Member-Funktion einer lokalen Klasse muss definiert werden.

Der Compiler erfordert, dass bestimmte Funktionen definiert werden.

Im folgenden Beispiel wird C3640 generiert:

```cpp
// C3640.cpp
void f()
{
   struct S
   {
      virtual void f1();   // C3640
      // Try the following line instead:
      // virtual void f1(){}
   };
}
```
