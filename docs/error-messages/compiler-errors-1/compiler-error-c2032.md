---
title: Compilerfehler C2032
ms.date: 11/04/2016
f1_keywords:
- C2032
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
ms.openlocfilehash: 5743aba880f23d7706940936fc4a3a1973a84ca1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400512"
---
# <a name="compiler-error-c2032"></a>Compilerfehler C2032

'Bezeichner': Funktion kann kein Member von 'StrukturOderUnion' Struct/Union sein

Die Struktur oder Union verfügt über eine Memberfunktion, die in C++, aber nicht in C. zulässig ist Um den Fehler zu beheben, können Sie entweder als ein C++-Programm kompilieren Sie oder entfernen Sie die Member-Funktion.

Im folgende Beispiel wird die C2032 generiert:

```
// C2032.c
struct z {
   int i;
   void func();   // C2032
};
```

Mögliche Lösung:

```
// C2032b.c
// compile with: /c
struct z {
   int i;
};
```