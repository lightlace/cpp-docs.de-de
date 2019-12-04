---
title: Compilerfehler C2341
ms.date: 11/04/2016
f1_keywords:
- C2341
helpviewer_keywords:
- C2341
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
ms.openlocfilehash: 6147ce954c6d21d86f76d1fd8ec6b8a1a5070a12
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760048"
---
# <a name="compiler-error-c2341"></a>Compilerfehler C2341

"Abschnitts Name": das Segment muss mithilfe #Pragma data_seg, code_seg oder Abschnitts definiert werden, bevor es verwendet werden kann.

Eine [Zuordnungs Anweisung verweist](../../cpp/allocate.md) auf ein Segment, das noch nicht durch [code_seg](../../preprocessor/code-seg.md)-, [data_seg](../../preprocessor/data-seg.md)-oder [section](../../preprocessor/section.md) -Pragmas definiert wurde.

Im folgenden Beispiel wird C2341 generiert:

```cpp
// C2341.cpp
// compile with: /c
__declspec(allocate(".test"))   // C2341
int j = 1;
```

Mögliche Lösung:

```cpp
// C2341b.cpp
// compile with: /c
#pragma data_seg(".test")
__declspec(allocate(".test"))
int j = 1;
```
