---
title: Compilerfehler C2277 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2277
dev_langs:
- C++
helpviewer_keywords:
- C2277
ms.assetid: 15a83b07-8731-4524-810b-267f65a7844f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 212ae84917e664116c83df3135577e00cda19446
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101937"
---
# <a name="compiler-error-c2277"></a>Compilerfehler C2277

'Bezeichner': Adresse von dieser Memberfunktion nicht übernehmen

Die Adresse einer Memberfunktion ist nicht möglich.

Im folgende Beispiel wird die C2277 generiert:

```
// C2277.cpp
class A {
public:
   A();
};
(*pctor)() = &A::A;   // C2277
```