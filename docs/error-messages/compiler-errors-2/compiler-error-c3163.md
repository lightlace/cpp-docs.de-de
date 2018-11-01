---
title: Compilerfehler C3163
ms.date: 11/04/2016
f1_keywords:
- C3163
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
ms.openlocfilehash: b5c689842f59a9cf999de08f10926efce0ade5ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490206"
---
# <a name="compiler-error-c3163"></a>Compilerfehler C3163

'construct': Attribute, die mit der vorherigen Deklaration inkonsistent.

Die Attribute, die zu einem Konflikt Definition mit die Attribute angewendet werden, die auf eine Deklaration angewendet werden.

Eine Möglichkeit zum Beheben von C3163 werden Attribute in der Vorwärtsdeklaration zu vermeiden. Alle Attribute in einer Vorwärtsdeklaration sollte niedriger sein als die Attribute in der Definition oder höchstens gleich an Sie.

Eine mögliche Ursache des Fehlers C3163 umfasst die Microsoft Source Code Annotation Language (SAL). Die SAL-Makros nicht erweitern, wenn das Projekt kompilieren mit der **/ analyze** Flag. Ein Programm, das problemlos kompilieren ohne / analyze kann C3163 auslösen, wenn Sie versuchen, kompilieren sie mit dem / analyze-Option. Weitere Informationen zu SAL, finden Sie unter [SAL-Anmerkungen](../../c-runtime-library/sal-annotations.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3163 generiert.

```
// C3163.cpp
// compile with: /clr /c
using namespace System;

[CLSCompliant(true)] void f();
[CLSCompliant(false)] void f() {}   // C3163
// try the following line instead
// [CLSCompliant(true)] void f() {}
```

## <a name="see-also"></a>Siehe auch

[SAL-Anmerkungen](../../c-runtime-library/sal-annotations.md)