---
title: Compilerfehler C2458
ms.date: 11/04/2016
f1_keywords:
- C2458
helpviewer_keywords:
- C2458
ms.assetid: ed21901f-1067-42f5-b275-19b480decf5c
ms.openlocfilehash: 93e0159ca680b37aed2031c6e2ec41463e7e389d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744003"
---
# <a name="compiler-error-c2458"></a>Compilerfehler C2458

"Bezeichner": Neudefinition innerhalb der Definition

Eine Klasse, Struktur, Union oder Enumeration wird in ihrer eigenen Deklaration neu definiert.

Im folgenden Beispiel wird C2458 generiert:

```cpp
// C2458.cpp
class C {
   enum i { C };   // C2458
};
```
