---
title: Compilerfehler C3230 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3230
dev_langs:
- C++
helpviewer_keywords:
- C3230
ms.assetid: 5ec53f25-59f6-4801-81e7-7b68bf04994d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f74e17b1dec3aba78a38d993da81995d00c93784
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065597"
---
# <a name="compiler-error-c3230"></a>Compilerfehler C3230

'Funktion': Das Vorlagentypargument für 'Vorlage' kann keinen generischen Typparameter enthalten: 'param'

Vorlagen werden zur Kompilierzeit, aber Generika zur Laufzeit instanziiert. Daher ist es nicht möglich, generischen Code zu generieren, der die Vorlage aufrufen kann, da die Vorlage nicht zur Laufzeit instanziiert werden kann, wenn der generische Typ schließlich bekannt ist.

Im folgenden Beispiel wird C3230 generiert:

```
// C3230.cpp
// compile with: /clr /LD
template <class S>
void f(S t);

generic <class U>
ref class C {
   void f1(U x) {
      f(x);   // C3230
   }
};
```