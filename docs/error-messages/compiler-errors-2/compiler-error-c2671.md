---
title: Compilerfehler C2671
ms.date: 11/04/2016
f1_keywords:
- C2671
helpviewer_keywords:
- C2671
ms.assetid: fc0ee40f-c8f3-408f-b89d-745d149c4169
ms.openlocfilehash: 92ed646b0e4c5d2bbc6556c2a7b1ef66d8192ec1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165072"
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