---
title: Compilerfehler C3168
ms.date: 11/04/2016
f1_keywords:
- C3168
helpviewer_keywords:
- C3168
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
ms.openlocfilehash: f39160cc09825c6d87d56ff5ba80d21a35f41e12
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676563"
---
# <a name="compiler-error-c3168"></a>Compilerfehler C3168

'Typ': Ungültiger zugrunde liegender Typ für Enumeration

Die zugrunde liegende Geben Sie bei der `enum` Typ war ungültig. Der zugrunde liegende Typ muss es sich um einen ganzzahligen C++-Typ oder einen entsprechenden CLR-Typ sein.

Im folgende Beispiel wird die C3168 generiert:

```
// C3168.cpp
// compile with: /clr /c
ref class G{};

enum class E : G { e };   // C3168
enum class F { f };   // OK
```
