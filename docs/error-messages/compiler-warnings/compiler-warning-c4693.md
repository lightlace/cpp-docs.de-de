---
title: Compilerwarnung C4693 | Microsoft Docs
ms.date: 10/25/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4693
dev_langs:
- C++
helpviewer_keywords:
- C4693
ms.assetid: 72d8db01-5e6f-4794-8731-76107e8f064a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f8230e60d65c80b4f839cc8a1c97ccc0c7b18086
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-c4693"></a>Compilerwarnung C4693

> "class": Eine versiegelte abstrakte Klasse kann keine Test-Instanzmember aufweisen

Wenn ein Typ gekennzeichnet ist [versiegelten](../../windows/sealed-cpp-component-extensions.md) und [abstrakte](../../windows/abstract-cpp-component-extensions.md), es kann nur statische Member aufweisen.

Diese Warnung wird automatisch zu einem Fehler heraufgestuft. Wenn Sie dieses Verhalten ändern möchten, verwenden Sie [#pragma Warning](../../preprocessor/warning.md).

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