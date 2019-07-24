---
title: Compilerwarnung C4694
ms.date: 10/25/2017
f1_keywords:
- C4694
helpviewer_keywords:
- C4694
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
ms.openlocfilehash: 6164fd2e19e35233ba67feb84d117f1e4e01f20d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311047"
---
# <a name="compiler-warning-c4694"></a>Compilerwarnung C4694

> "*Klasse*': eine versiegelte abstrakte Klasse einer Basisklasse sind keine*Base_class*"

Eine abstrakte und versiegelte Klasse kann nicht von einem Referenztyp erben; eine versiegelte und abstrakte Klasse kann weder die Basisklassenfunktionen implementieren noch ihre eigene Verwendung als Basisklasse zulassen.

Weitere Informationen finden Sie unter [abstrakte](../../extensions/abstract-cpp-component-extensions.md), [versiegelten](../../extensions/sealed-cpp-component-extensions.md), und [Klassen und Strukturen](../../extensions/classes-and-structs-cpp-component-extensions.md).

Diese Warnung wird automatisch zu einem Fehler heraufgestuft. Wenn Sie dieses Verhalten ändern möchten, verwenden Sie [#pragma-Warnung](../../preprocessor/warning.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4694 generiert:

```cpp
// C4694.cpp
// compile with: /c /clr
ref struct A {};
ref struct B sealed abstract : A {};   // C4694
```