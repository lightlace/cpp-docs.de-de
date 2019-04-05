---
title: Compilerwarnung C4693
ms.date: 10/25/2017
f1_keywords:
- C4693
helpviewer_keywords:
- C4693
ms.assetid: 72d8db01-5e6f-4794-8731-76107e8f064a
ms.openlocfilehash: cac5918eb4a1689fd215e07272958eeca48247ad
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781899"
---
# <a name="compiler-warning-c4693"></a>Compilerwarnung C4693

> "class": Eine versiegelte abstrakte Klasse kann keine Test-Instanzmember aufweisen

Wenn ein Typ gekennzeichnet ist [versiegelten](../../extensions/sealed-cpp-component-extensions.md) und [abstrakte](../../extensions/abstract-cpp-component-extensions.md), es kann nur statische Member aufweisen.

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