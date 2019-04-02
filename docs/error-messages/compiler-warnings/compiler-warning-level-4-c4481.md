---
title: Compilerwarnung (Stufe 4) C4481
ms.date: 11/04/2016
f1_keywords:
- C4481
helpviewer_keywords:
- C4481
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
ms.openlocfilehash: fe96ff50f4081e3c9dbe3c7eb68da156a69c96ab
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58776361"
---
# <a name="compiler-warning-level-4-c4481"></a>Compilerwarnung (Stufe 4) C4481

nicht dem Standard entsprechende Erweiterung: Überschreibungsspezifizierer 'Schlüsselwort'

Ein Schlüsselwort wurde verwendet, die nicht in der C++-standard, z. B. einer der Bezeichner außer Kraft setzen, die auch unter "/ CLR" funktioniert.  Weitere Informationen finden Sie unter

- [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Überschreibungsspezifizierer](../../extensions/override-specifiers-cpp-component-extensions.md)

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4481 generiert.

```
// C4481.cpp
// compile with: /W4 /c
class B {
   virtual void f(unsigned);
};

class C : B {
   void f(unsigned) override;   // C4481
   void f2(unsigned);
};
```