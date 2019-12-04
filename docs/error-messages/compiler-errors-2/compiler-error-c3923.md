---
title: Compilerfehler C3923
ms.date: 11/04/2016
f1_keywords:
- C3923
helpviewer_keywords:
- C3923
ms.assetid: db8838e9-6344-4cd6-83e0-a8abeb12c4c0
ms.openlocfilehash: e688afcfd477ce88c437f22f864bfb97b1d2ade1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757773"
---
# <a name="compiler-error-c3923"></a>Compilerfehler C3923

„member“: Definitionen für lokale Klassen, Strukturen oder Unions sind in einer Memberfunktion einer verwalteten oder WinRT-Klasse nicht zulässig.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3923 generiert.

```cpp
// C3923.cpp
// compile with: /clr /c
ref struct x {
   void Test() {
      struct a {};   // C3923
      class b {};   // C3923
      union c {};   // C3923
   }
};
```
