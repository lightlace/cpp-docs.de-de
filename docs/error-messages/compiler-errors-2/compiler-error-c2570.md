---
title: Compilerfehler C2570
ms.date: 11/04/2016
f1_keywords:
- C2570
helpviewer_keywords:
- C2570
ms.assetid: d65d0b32-2fac-464a-bcdf-0ebcedf3bf32
ms.openlocfilehash: 6b9f94b1b17aad85aab37659565e6e0827b5a824
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755511"
---
# <a name="compiler-error-c2570"></a>Compilerfehler C2570

"Bezeichner": Union kann keine Basisklassen aufweisen.

Eine Union wird von einer Klasse, Struktur oder Union abgeleitet. Dieser Vorgang ist nicht zulässig. Deklarieren Sie den abgeleiteten Typ stattdessen als Klasse oder Struktur.

Im folgenden Beispiel wird C2570 generiert:

```cpp
// C2570.cpp
// compile with: /c
class base {};
union hasPubBase : public base {};   // C2570
union hasNoBase {};   // OK
```
