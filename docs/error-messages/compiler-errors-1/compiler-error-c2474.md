---
title: Compilerfehler C2474 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2474
dev_langs:
- C++
helpviewer_keywords:
- C2474
ms.assetid: 64e6c61e-6e77-480e-bcf0-b30a2fc482ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd33c74a0f5fe179b0dfdd5754d15f24bf0026ff
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092569"
---
# <a name="compiler-error-c2474"></a>Compilerfehler C2474

"Schlüsselwort": Es fehlt ein angrenzendes Semikolon, kann entweder ein Schlüsselwort oder ein Bezeichner sein.

Der Compiler hat ein Semikolon erwartet und konnte Ihre Absicht nicht ermitteln. Fügen Sie das Semikolon hinzu, um diesen Fehler zu beheben.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2474 generiert.

```
// C2474.cpp
// compile with: /clr /c

ref class A {
   ref class B {}
   property int i;   // C2474 error
};

// OK
ref class B {
   ref class D {};
   property int i;
};

ref class E {
   ref class F {} property;
   int i;
};
```