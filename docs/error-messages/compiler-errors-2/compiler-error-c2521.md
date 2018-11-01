---
title: Compilerfehler C2521
ms.date: 11/04/2016
f1_keywords:
- C2521
helpviewer_keywords:
- C2521
ms.assetid: 6042821b-e345-4a54-a7e9-a2c9019ea016
ms.openlocfilehash: 27d822a3daf2c20aa57ebd8b45a7a6c7afa3d3cc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490424"
---
# <a name="compiler-error-c2521"></a>Compilerfehler C2521

Funktion akzeptiert keine Argumente

Es wurde versucht, Argumente mit einem Destruktor oder Finalizer zu verwenden.

Weitere Informationen finden Sie unter [Destruktoren und Finalizer](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2521 generiert.

```
// C2521.cpp
// compile with: /clr
ref class R {
protected:
   !R() {}

public:
   void CleanUp() {
      this->!R(4);   // C2521
      this->!R();   // OK
   }
};

int main() {
   R^ r = gcnew R();
   r->CleanUp();
}
```