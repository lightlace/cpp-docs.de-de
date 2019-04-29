---
title: Compilerfehler C2791
ms.date: 11/04/2016
f1_keywords:
- C2791
helpviewer_keywords:
- C2791
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
ms.openlocfilehash: 66a111ea6fe2ca5acfbc473d19da62d9de67372a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360163"
---
# <a name="compiler-error-c2791"></a>Compilerfehler C2791

Unzulässige Verwendung von "Super": "Klasse" besitzt keine Basisklassen

Das Schlüsselwort [super](../../cpp/super.md) im Kontext einer Memberfunktion einer Klasse, die keine Basisklassen verwendet wurde.

Im folgende Beispiel wird die C2791 generiert:

```
// C2791.cpp
struct D {
   void mf() {
      __super::mf();   // C2791
   }
};
```