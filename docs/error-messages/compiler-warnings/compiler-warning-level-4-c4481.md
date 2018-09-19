---
title: Compilerwarnung (Stufe 4) C4481 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4481
dev_langs:
- C++
helpviewer_keywords:
- C4481
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 48ed2ba08423f7540f4e0a855aacbcab993d41aa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063761"
---
# <a name="compiler-warning-level-4-c4481"></a>Compilerwarnung (Stufe 4) C4481

nicht dem Standard entsprechende Erweiterung: Überschreibungsspezifizierer 'Schlüsselwort'

Ein Schlüsselwort wurde verwendet, die nicht in der C++-standard, z. B. einer der Bezeichner außer Kraft setzen, die auch unter "/ CLR" funktioniert.  Weitere Informationen finden Sie unter

- [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Überschreibungsspezifizierer](../../windows/override-specifiers-cpp-component-extensions.md)

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