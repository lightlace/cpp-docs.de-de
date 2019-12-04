---
title: Compilerfehler C2947
ms.date: 11/04/2016
f1_keywords:
- C2947
helpviewer_keywords:
- C2947
ms.assetid: 6c056f62-ec90-4883-8a67-aeeb6ec13546
ms.openlocfilehash: 7056c13edca534701ffe82f0169897ea804f40d7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755355"
---
# <a name="compiler-error-c2947"></a>Compilerfehler C2947

">" wird zum Beenden des Konstrukts erwartet, "Syntax" wurde gefunden.

Eine generische oder Vorlagen Argumentliste wurde möglicherweise nicht ordnungsgemäß beendet.

C2947 kann auch durch Syntax Fehler generiert werden.

Im folgenden Beispiel wird C2947 generiert:

```cpp
// C2947.cpp
// compile with: /c
template <typename T>=   // C2947
// try the following line instead
// template <typename T>
struct A {};
```
