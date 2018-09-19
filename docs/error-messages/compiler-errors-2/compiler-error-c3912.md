---
title: Compilerfehler C3912 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3912
dev_langs:
- C++
helpviewer_keywords:
- C3912
ms.assetid: 674e050c-11fb-4db1-8bdf-a3e95b41161d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 26ffa49a6b54769db5b24d91ffcaf72579a6e458
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115254"
---
# <a name="compiler-error-c3912"></a>Compilerfehler C3912

'Ereignis': Typ des Ereignisses muss ein Delegattyp sein

Ein Ereignis wurde deklariert, aber es hatte nicht den richtigen Typ.

Weitere Informationen finden Sie unter [Ereignis](../../windows/event-cpp-component-extensions.md).

Im folgende Beispiel wird die C3912 generiert:

```
// C3912.cpp
// compile with: /clr
delegate void H();
ref class X {
   event int Ev;   // C3912
   event H^ Ev2;   // OK
};
```