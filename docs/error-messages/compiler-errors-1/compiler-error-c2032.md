---
title: Compilerfehler C2032 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2032
dev_langs:
- C++
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ab02ca695ec94f25054e3490232b782a46a53a4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064008"
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