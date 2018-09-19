---
title: Compilerfehler C2671 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2671
dev_langs:
- C++
helpviewer_keywords:
- C2671
ms.assetid: fc0ee40f-c8f3-408f-b89d-745d149c4169
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b37d9dc1e50da921bdbe758e73257100853517eb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026154"
---
# <a name="compiler-error-c2671"></a>Compilerfehler C2671

'Funktion': statische Memberfunktionen keinen this-Zeiger

Ein `static` Memberfunktion versucht, den Zugriff auf `this`.

Im folgende Beispiel wird die C2671 generiert:

```
// C2671.cpp
struct S {
   static S* const func() { return this; }  // C2671
};
```