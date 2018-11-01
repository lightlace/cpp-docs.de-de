---
title: Compilerwarnung C4693
ms.date: 10/25/2017
f1_keywords:
- C4693
helpviewer_keywords:
- C4693
ms.assetid: 72d8db01-5e6f-4794-8731-76107e8f064a
ms.openlocfilehash: 49d101ea56cd868e18489b6c74724a2d106c9265
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536655"
---
# <a name="compiler-warning-c4693"></a>Compilerwarnung C4693

> "class": Eine versiegelte abstrakte Klasse kann keine Test-Instanzmember aufweisen

Wenn ein Typ gekennzeichnet ist [versiegelten](../../windows/sealed-cpp-component-extensions.md) und [abstrakte](../../windows/abstract-cpp-component-extensions.md), es kann nur statische Member aufweisen.

Diese Warnung wird automatisch zu einem Fehler heraufgestuft. Wenn Sie dieses Verhalten ändern möchten, verwenden Sie [#pragma-Warnung](../../preprocessor/warning.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4693 generiert:

```cpp
// C4693.cpp
// compile with: /clr /c
public ref class Public_Ref_Class sealed abstract {
public:
   void Test() {}   // C4693
   static void Test2() {}   // OK
};
```