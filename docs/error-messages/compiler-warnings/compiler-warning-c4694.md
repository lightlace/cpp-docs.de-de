---
title: Compilerwarnung C4694 | Microsoft Docs
ms.date: 10/25/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4694
dev_langs:
- C++
helpviewer_keywords:
- C4694
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33852b76f23e007625f86969119a22ee81305187
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33271454"
---
# <a name="compiler-warning-c4694"></a>Compilerwarnung C4694

> "*Klasse*': eine versiegelte abstrakte Klasse keine Basisklasse sind keine*basis_klasse*"

Eine abstrakte und versiegelte Klasse kann nicht von einem Referenztyp erben; eine versiegelte und abstrakte Klasse kann weder die Basisklassenfunktionen implementieren noch ihre eigene Verwendung als Basisklasse zulassen.

Weitere Informationen finden Sie unter [abstrakte](../../windows/abstract-cpp-component-extensions.md), [versiegelten](../../windows/sealed-cpp-component-extensions.md), und [Klassen und Strukturen](../../windows/classes-and-structs-cpp-component-extensions.md).

Diese Warnung wird automatisch zu einem Fehler heraufgestuft. Wenn Sie dieses Verhalten ändern möchten, verwenden Sie [#pragma Warning](../../preprocessor/warning.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4694 generiert:

```cpp
// C4694.cpp
// compile with: /c /clr
ref struct A {};
ref struct B sealed abstract : A {};   // C4694
```