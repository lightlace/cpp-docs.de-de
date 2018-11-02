---
title: Compilerfehler C3288
ms.date: 11/04/2016
f1_keywords:
- C3288
helpviewer_keywords:
- C3288
ms.assetid: ed08a540-9751-46e1-9cbe-c51d6a49ffab
ms.openlocfilehash: 30a88d1047f8395fc8e3042cf2a1da88e6e5c2d3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50608415"
---
# <a name="compiler-error-c3288"></a>Compilerfehler C3288

"Type": unzulässige Dereferenzierung eines Handletyps.

Der Compiler hat eine ungültige Dereferenzierung eines Handletyps. Sie können Dereferenzierung ein Handletyps und weisen sie einen Verweis. Weitere Informationen finden Sie unter [Verweisoperator nachverfolgung](../../windows/tracking-reference-operator-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3288 generiert.

```
// C3288.cpp
// compile with: /clr
ref class R {};
int main() {
   *(System::Object^) nullptr;   // C3288

// OK
   (System::Object^) nullptr;   // OK
   R^ r;
   R% pr = *r;
}
```