---
title: Compilerfehler C2032
ms.date: 11/04/2016
f1_keywords:
- C2032
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
ms.openlocfilehash: 5743aba880f23d7706940936fc4a3a1973a84ca1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558248"
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