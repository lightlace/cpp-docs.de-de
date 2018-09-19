---
title: Compilerfehler C2216 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2216
dev_langs:
- C++
helpviewer_keywords:
- C2216
ms.assetid: 250f6bdc-a5e1-495f-a1e8-6e8e7021ad9d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01707c3276ddedab0c224e0f459634c508e0ac04
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070144"
---
# <a name="compiler-error-c2216"></a>Compilerfehler C2216

'Schlüsselwort1' kann nicht mit 'Schlüsselwort2' verwendet werden.

Zwei Schlüsselwörter, die sich gegenseitig ausschließen, wurden zusammen verwendet.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2216 generiert:

```
// C2216.cpp
// compile with: /clr /c
ref struct Y1 {
   literal
   static int staticConst2 = 10;   // C2216
};
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2216 generiert:

```
// C2216b.cpp
// compile with: /clr /c
public ref class X {
   extern property int i { int get(); }   // C2216 extern not allowed on property
   typedef property int i2;   // C2216 typedef not allowed on property
};
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2216 generiert:

```
// C2216c.cpp
// compile with: /clr /c
public interface struct I {
   double f();
   double g();
   double h();
};

public ref struct R : I {
   virtual double f() new override { return 0.0; }   // C2216
   virtual double g() new { return 0.0; }   // OK
   virtual double h() override { return 0.0; }   // OK
};
```