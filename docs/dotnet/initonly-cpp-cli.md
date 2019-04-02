---
title: initonly (C++/CLI)
ms.date: 11/04/2016
f1_keywords:
- initonly_cpp
- initonly
helpviewer_keywords:
- initonly attribute [C++]
ms.assetid: f745d7fa-dc08-46f1-9b97-0977be58a008
ms.openlocfilehash: cdfc278225ce4ab418dfaaf41fb413d088ad77df
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58766573"
---
# <a name="initonly-ccli"></a>initonly (C++/CLI)

**Initonly** ist ein kontextbezogenes Schlüsselwort ein, der angibt, die variablenzuweisung kann nur als Teil der Deklaration oder in einem statischen Konstruktor in derselben Klasse auftreten.

Das folgende Beispiel veranschaulicht die Verwendung von `initionly`:

```
// mcpp_initonly.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int staticConst1;

   initonly
   static int staticConst2 = 0;

   static Y1() {
      staticConst1 = 0;
   }
};
```

## <a name="see-also"></a>Siehe auch

[Klassen und Strukturen](../extensions/classes-and-structs-cpp-component-extensions.md)
