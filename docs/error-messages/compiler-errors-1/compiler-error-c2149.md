---
title: Compilerfehler C2149
ms.date: 11/04/2016
f1_keywords:
- C2149
helpviewer_keywords:
- C2149
ms.assetid: 7a106dab-d79f-41b9-85be-f36e86e4d2ab
ms.openlocfilehash: 62eca9730b28f83cea39d5c6606d4bb94ce885dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175203"
---
# <a name="compiler-error-c2149"></a>Compilerfehler C2149

"Bezeichner": Die Breite des benannten Bitfelds muss größer als null (0) sein.

Nur nicht benannte Bitfelder können eine Breite von null (0) aufweisen.

Im folgenden Beispiel wird C2149 generiert:

```
// C2149.cpp
// compile with: /c
struct C {
   int i : 0;   // C2149
   int j : 2;   // OK
};
```