---
title: Compilerfehler C2396
ms.date: 11/04/2016
f1_keywords:
- C2396
helpviewer_keywords:
- C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
ms.openlocfilehash: d320f78937fc60910bbed4a5b1b89841ea674fb7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303514"
---
# <a name="compiler-error-c2396"></a>Compilerfehler C2396

' your_type ': CLR- oder WinRT benutzerdefinierte Konvertierung Functionnot gültig. Muss die Konvertierung von oder in konvertieren: ' T ^', ' t ^ %', ' t ^ &', wobei T = 'Your_type'

Eine Konvertierungsfunktion in einem Windows-Runtime- oder verwalteten Typ wies nicht einmal einen Parameter auf, dessen Typ dem Typ entspricht, der die Konvertierungsfunktion aufweist.

Im folgenden Beispiel wird C2396 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
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