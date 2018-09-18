---
title: Compilerfehler C2507 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2507
dev_langs:
- C++
helpviewer_keywords:
- C2507
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16cc9c5f21618f3b681fbefbfadfd66b0219d5ac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022720"
---
# <a name="compiler-error-c2507"></a>Compilerfehler C2507

'Bezeichner': zu viele virtuelle Modifizierer für Basisklasse

Eine Klasse oder Struktur wird als deklariert `virtual` mehr als einmal. Nur ein `virtual` Modifizierer kann für jede Klasse in einer Liste der Basisklassen verwendet werden.

Im folgende Beispiel wird die C2507 generiert:

```
// C2507.cpp
// compile with: /c
class A {};
class B : virtual virtual public A {};   // C2507
class C : virtual public A {};   // OK
```