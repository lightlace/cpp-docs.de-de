---
title: Compilerfehler C3288
ms.date: 11/04/2016
f1_keywords:
- C3288
helpviewer_keywords:
- C3288
ms.assetid: ed08a540-9751-46e1-9cbe-c51d6a49ffab
ms.openlocfilehash: d076dabe0df91cefb90be5ec9e90f371331a51f1
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776768"
---
# <a name="compiler-error-c3288"></a>Compilerfehler C3288

"Type": unzulässige Dereferenzierung eines Handletyps.

Der Compiler hat eine ungültige Dereferenzierung eines Handletyps. Sie können Dereferenzierung ein Handletyps und weisen sie einen Verweis. Weitere Informationen finden Sie unter [Verweisoperator nachverfolgung](../../extensions/tracking-reference-operator-cpp-component-extensions.md).

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