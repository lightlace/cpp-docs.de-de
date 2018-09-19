---
title: Compilerfehler C3163 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3163
dev_langs:
- C++
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e712a70bdd443d9a6c640853b958f29dac78dbd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061967"
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