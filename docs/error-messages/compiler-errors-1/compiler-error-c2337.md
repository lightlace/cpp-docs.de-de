---
title: Compilerfehler C2337
ms.date: 09/19/2019
f1_keywords:
- C2337
helpviewer_keywords:
- C2337
ms.assetid: eccc9178-a15e-42cd-bbd0-3cea7cf2d55b
ms.openlocfilehash: bf9b3e782804add13aeaef0e6672d2dd66d193be
ms.sourcegitcommit: f907b15f50a6b945d0b87c03af0050946157d701
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "71158773"
---
# <a name="compiler-error-c2337"></a>Compilerfehler C2337

> '*Attribute-Name*': das Attribut wurde nicht gefunden.

Im Code wird ein Attribut verwendet, das in diesem Kontext nicht unterstützt wird. Oder das-Attribut ist in dieser Version des Compilers nicht verfügbar. Um dieses Problem zu beheben, entfernen Sie das nicht unterstützte Attribut.

Im folgenden Beispiel wird C2337 generiert:

```cpp
// C2337.cpp
// compile with: /c
[emitidl];
[module(name="x")];
[grasshopper]   // C2337, not a supported attribute
class a{};
```
