---
title: Compilerfehler C2326
ms.date: 11/04/2016
f1_keywords:
- C2326
helpviewer_keywords:
- C2326
ms.assetid: 01a5ea40-de83-4e6f-a4e8-469f441258e0
ms.openlocfilehash: 9cf72cddbb1f71f29153ff8d544787285a077f9c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747799"
---
# <a name="compiler-error-c2326"></a>Compilerfehler C2326

"Deklarator": Funktion kann nicht auf "Name" zugreifen

Der Code versucht, eine Membervariable zu ändern, was nicht möglich ist.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2326 generiert:

```cpp
// C2326.cpp
void MyFunc() {
   int i;

   class MyClass  {
   public:
      void mf() {
         i = 4;   // C2326 i is inaccessible
      }
   };
}
```
