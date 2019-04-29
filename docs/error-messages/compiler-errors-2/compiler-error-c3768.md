---
title: Compilerfehler C3768
ms.date: 11/04/2016
f1_keywords:
- C3768
helpviewer_keywords:
- C3768
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
ms.openlocfilehash: e9c385fd178dc967e72f5e0ca7fab27b28ad962f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400213"
---
# <a name="compiler-error-c3768"></a>Compilerfehler C3768

> die Adresse einer virtuellen Vararg-Funktion in reinem verwaltetem Code kann nicht übernommen werden.

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** Compileroption ist in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt.

Beim Kompilieren mit **/CLR: pure**, Sie können die Adresse einer virtuellen nicht übernehmen `vararg` Funktion.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3768 generiert:

```cpp
// C3768.cpp
// compile with: /clr:pure
struct A
{
   virtual void f(...);
};

int main()
{
   &(A::f);   // C3768
}
```