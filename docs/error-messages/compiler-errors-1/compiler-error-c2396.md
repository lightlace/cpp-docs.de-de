---
title: Compilerfehler C2396
ms.date: 11/04/2016
f1_keywords:
- C2396
helpviewer_keywords:
- C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
ms.openlocfilehash: 5020732ce5186ee1c6e9d2ea13f452fe9988bdfa
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744835"
---
# <a name="compiler-error-c2396"></a>Compilerfehler C2396

' your_type:: operator' Type ' ': die CLR-oder WinRT-benutzerdefinierte Konvertierung ist ungültig. Muss entweder aus konvertieren oder in: 't ^ ', 't ^% ', 't ^ & ' konvertiert werden, wobei T = ' your_type ' ist.

Eine Konvertierungsfunktion in einem Windows-Runtime- oder verwalteten Typ wies nicht einmal einen Parameter auf, dessen Typ dem Typ entspricht, der die Konvertierungsfunktion aufweist.

Im folgenden Beispiel wird C2396 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C2396.cpp
// compile with: /clr /c

ref struct Y {
   static operator int(char c);   // C2396

   // OK
   static operator int(Y^ hY);
   // or
   static operator Y^(char c);
};
```
