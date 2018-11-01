---
title: Compilerfehler C3765
ms.date: 11/04/2016
f1_keywords:
- C3765
helpviewer_keywords:
- C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
ms.openlocfilehash: 86c043889c5342ed4f3edfc4d8a298bcbd345b3b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456393"
---
# <a name="compiler-error-c3765"></a>Compilerfehler C3765

'Ereignis': Definieren Sie ein Ereignis kann nicht in einer Klasse/Struktur "type" als ein Event_receiver gekennzeichnet

Wenn eine Klasse mit markiert ist die [Event_receiver](../../windows/event-receiver.md) -Attribut die Klasse darf keine enthalten eine [__event](../../cpp/event.md) Deklaration.

Im folgende Beispiel wird die C3765 generiert:

```
// C3765.cpp
[event_receiver(native)]
struct ER2 {
   __event void f();   // C3765
   __event void b(int);   // C3765
};
```