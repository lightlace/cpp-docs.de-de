---
title: Compilerwarnung C4694 | Microsoft Docs
ms.date: 10/25/2017
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- C4694
dev_langs:
- C++
helpviewer_keywords:
- C4694
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f635aad0039812b50bd48a36f307ab5f60cba10
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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