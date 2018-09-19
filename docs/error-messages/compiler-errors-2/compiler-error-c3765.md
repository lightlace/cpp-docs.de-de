---
title: Compilerfehler C3765 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3765
dev_langs:
- C++
helpviewer_keywords:
- C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cac3930e4f5ec42587a9f557adc7a82d750b3819
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042129"
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