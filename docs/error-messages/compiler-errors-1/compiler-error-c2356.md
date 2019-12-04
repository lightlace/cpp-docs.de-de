---
title: Compilerfehler C2356
ms.date: 11/04/2016
f1_keywords:
- C2356
helpviewer_keywords:
- C2356
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
ms.openlocfilehash: e306c5a8f9175bc3c7902b20263aa2e451944182
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759931"
---
# <a name="compiler-error-c2356"></a>Compilerfehler C2356

das Initialisierungs Segment darf während der Übersetzungseinheit nicht geändert werden.

Mögliche Ursachen:

- `#pragma init_seg` vorangestelltem Initialisierungs Code des Segments

- `#pragma init_seg` einem anderen `#pragma init_seg` vorangestellt

Um dies aufzulösen, verschieben Sie den Initialisierungs Code des Segments an den Anfang des Moduls. Wenn mehrere Bereiche initialisiert werden müssen, verschieben Sie Sie in separate Module.

Im folgenden Beispiel wird C2356 generiert:

```cpp
// C2356.cpp
#pragma warning(disable : 4075)

int __cdecl myexit(void (__cdecl *)());
int __cdecl myexit2(void (__cdecl *)());

#pragma init_seg(".mine$m",myexit)
#pragma init_seg(".mine$m",myexit2)   // C2356
```
