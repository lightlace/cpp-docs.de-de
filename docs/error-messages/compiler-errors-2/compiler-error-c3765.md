---
title: Compilerfehler C3765
ms.date: 11/04/2016
f1_keywords:
- C3765
helpviewer_keywords:
- C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
ms.openlocfilehash: 8a12bdfaf0931fb0a94dafc289f9ae39aef61f23
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757233"
---
# <a name="compiler-error-c3765"></a>Compilerfehler C3765

"Ereignis": ein Ereignis in einer Klasse/Struktur "Type", die als Event_receiver gekennzeichnet ist, kann nicht definiert werden.

Wenn eine Klasse mit dem [event_receiver](../../windows/event-receiver.md) -Attribut markiert ist, kann die Klasse keine [__event](../../cpp/event.md) Deklaration enthalten.

Im folgenden Beispiel wird C3765 generiert:

```cpp
// C3765.cpp
[event_receiver(native)]
struct ER2 {
   __event void f();   // C3765
   __event void b(int);   // C3765
};
```
