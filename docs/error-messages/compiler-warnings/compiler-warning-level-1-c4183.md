---
title: Compilerwarnung (Stufe 1) C4183 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4183
dev_langs:
- C++
helpviewer_keywords:
- C4183
ms.assetid: dc48312c-4b34-44dd-80ff-eb5f11d5ca47
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2753b8fc47de3363c38ed6ee4dedeaf8d085c485
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022435"
---
# <a name="compiler-warning-level-1-c4183"></a>Compilerwarnung (Stufe 1) C4183

"Bezeichner": Rückgabetyp fehlt; davon ausgegangen, dass eine Memberfunktion, die "Int" zurückgibt

Die Inlinedefinition einer Memberfunktion in einer Klasse oder Struktur muss einen Rückgabetyp nicht. Diese Memberfunktion wird als ein Standardwert, der Rückgabetyp ist `int`.

Im folgende Beispiel wird die C4183 generiert:

```
// C4183.cpp
// compile with: /W1 /c
#pragma warning(disable : 4430)
class MyClass1;
class MyClass2 {
   MyClass1() {};   // C4183
};
```