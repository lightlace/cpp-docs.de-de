---
title: Compilerfehler C3168
ms.date: 11/04/2016
f1_keywords:
- C3168
helpviewer_keywords:
- C3168
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
ms.openlocfilehash: 4f09c7e250b4c2b02ba2db582f92d54336bed673
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761789"
---
# <a name="compiler-error-c3168"></a>Compilerfehler C3168

"Typ": Ungültiger zugrunde liegender Typ für die Aufzählung.

Der zugrunde liegende Typ, den Sie für den `enum` Typ angegeben haben, war ungültig. Der zugrunde liegende Typ muss ein ganzzahliger C++ Typ oder ein entsprechender CLR-Typ sein.

Im folgenden Beispiel wird C3168 generiert:

```cpp
// C3168.cpp
// compile with: /clr /c
ref class G{};

enum class E : G { e };   // C3168
enum class F { f };   // OK
```
