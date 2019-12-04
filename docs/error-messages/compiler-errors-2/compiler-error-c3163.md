---
title: Compilerfehler C3163
ms.date: 11/04/2016
f1_keywords:
- C3163
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
ms.openlocfilehash: 436fb112758dfdec9997ff7e6dd7ef8f9dcdc66e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761776"
---
# <a name="compiler-error-c3163"></a>Compilerfehler C3163

' construct ': Attribute sind mit vorheriger Deklaration inkonsistent.

Die auf eine Definition angewendeten Attribute verursachen einen Konflikt mit den Attributen, die auf eine Deklaration angewendet werden.

Eine Möglichkeit zum Auflösen von C3163 besteht darin, Attribute in der vorwärts Deklaration auszuschließen. Alle Attribute in einer vorwärts Deklaration sollten kleiner als die Attribute in der Definition oder höchstens gleich sein.

Eine mögliche Ursache für den C3163-Fehler ist die Microsoft Source Code Anmerkung Language (SAL). Die SAL-Makros werden nicht erweitert, es sei denn, Sie kompilieren das Projekt mit dem **/analyze** -Flag. Ein Programm, das ordnungsgemäß ohne/analyze kompiliert, löst möglicherweise C3163 aus, wenn Sie versuchen, es mit der/analyze-Option erneut zu kompilieren. Weitere Informationen zu SAL finden Sie unter [SAL](../../c-runtime-library/sal-annotations.md)-Anmerkungen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3163 generiert.

```cpp
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
