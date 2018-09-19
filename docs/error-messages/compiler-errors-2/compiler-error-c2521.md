---
title: Compilerfehler C2521 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2521
dev_langs:
- C++
helpviewer_keywords:
- C2521
ms.assetid: 6042821b-e345-4a54-a7e9-a2c9019ea016
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 24df0b75d45f9447b26cd8942ff6ca3e751c6a5d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047342"
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