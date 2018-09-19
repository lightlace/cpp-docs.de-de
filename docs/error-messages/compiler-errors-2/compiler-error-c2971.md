---
title: Compilerfehler C2971 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2971
dev_langs:
- C++
helpviewer_keywords:
- C2971
ms.assetid: fdb5467b-9a41-41ef-ac20-2e9428d5a4fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a311e6cd25ab275b7aa38325e45d26fd733d8b68
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107534"
---
# <a name="compiler-error-c2971"></a>Compilerfehler C2971

'Klasse': Vorlagenparameter 'Param': 'Arg': eine lokale Variable kann nicht als Nichttyp Argument verwendet werden

Sie können nicht den Namen oder die Adresse einer lokalen Variablen als Vorlagenargument verwenden.

Im folgende Beispiel wird die C2971 generiert:

```
// C2971.cpp
template <int *pi>
class Y {};

int global_var = 0;

int main() {
   int local_var = 0;
   Y<&local_var> aY;   // C2971
   // try the following line instead
   // Y<&global_var> aY;
}
```