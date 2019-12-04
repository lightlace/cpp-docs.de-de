---
title: Compilerfehler C3110
ms.date: 11/04/2016
f1_keywords:
- C3110
helpviewer_keywords:
- C3110
ms.assetid: 821dc71f-896e-4b2d-af0e-aa9932934b7b
ms.openlocfilehash: 21f1308c8dff0409d927fed5d5817f63015c709f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746291"
---
# <a name="compiler-error-c3110"></a>Compilerfehler C3110

"function_name": eine COM-Schnittstellen Methode kann nicht überladen werden.

Eine Schnittstelle, der ein Schnittstellen Attribut vorangestellt ist, z. b.:

- [custom](../../windows/custom-cpp.md)

- [dispinterface](../../windows/dispinterface.md)

- [dual](../../windows/dual.md)

- [object](../../windows/object-cpp.md)

kann nicht überladen werden. Beispiel:

```cpp
// C3110.cpp
#include <unknwn.h>
[ object, uuid= "4F98A180-EF37-11D1-978D-0000F805D73B" ]
__interface ITestInterface
{
   HRESULT mf1(void);
   HRESULT mf1(BSTR); // C3110
};

int main()
{
}
```
