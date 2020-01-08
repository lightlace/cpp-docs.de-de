---
title: Compilerfehler C2032
ms.date: 11/04/2016
f1_keywords:
- C2032
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
ms.openlocfilehash: d20bc61df2d0bab9115768b3bc0589f11a9bcdb9
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302093"
---
# <a name="compiler-error-c2032"></a>Compilerfehler C2032

' Identifier ': die Funktion kann nicht Mitglied der Struktur/Union ' structorunion ' sein.

Die Struktur oder Union verfügt über eine Member-Funktion, die in C++ zulässig ist, aber nicht in C. Um den Fehler zu beheben, kompilieren Sie entweder C++ als Programm, oder entfernen Sie die Member-Funktion.

Im folgenden Beispiel wird C2032 generiert:

```c
// C2032.c
struct z {
   int i;
   void func();   // C2032
};
```

Mögliche Lösung:

```c
// C2032b.c
// compile with: /c
struct z {
   int i;
};
```
