---
title: Compilerfehler C2571 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2571
dev_langs:
- C++
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30cc078251d0511da77e08690db275a788973ffb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067934"
---
# <a name="compiler-error-c2571"></a>Compilerfehler C2571

"Function": virtuelle Funktion darf sich nicht in Union "Union"

Eine Union ist mit einer virtuellen Funktion deklariert. Sie können eine virtuelle Funktion nur in einer Klasse oder Struktur deklarieren.  Mögliche Lösungen:

1. Ändern Sie die Union in einer Klasse oder Struktur an.

1. Stellen Sie die Funktion nicht virtuell.

Im folgende Beispiel wird die C2571 generiert:

```
// C2571.cpp
// compile with: /c
union A {
   virtual void func1();   // C2571
   void func2();   // OK
};
```