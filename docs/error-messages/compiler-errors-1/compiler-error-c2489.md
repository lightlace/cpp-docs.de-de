---
title: Compilerfehler C2489
ms.date: 11/04/2016
f1_keywords:
- C2489
helpviewer_keywords:
- C2489
ms.assetid: 67d8cd98-db7e-4f7f-86b4-4af7bc89ec8b
ms.openlocfilehash: 1977e32cec9d88a51aa6ec450a09be7fc33eb408
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757097"
---
# <a name="compiler-error-c2489"></a>Compilerfehler C2489

"Identifier": initialisierte automatische oder Register Variable ist im Funktionsbereich in der "Naked"-Funktion nicht zulässig.

Weitere Informationen finden Sie unter [Naked](../../cpp/naked-cpp.md).

Im folgenden Beispiel wird C2489 generiert:

```cpp
// C2489.cpp
// processor: x86
__declspec( naked ) int func() {
   int i = 1;   // C2489
   register int j = 1;   // C2489
}
```
