---
title: initonly (C++/CLI)
ms.date: 11/04/2016
f1_keywords:
- initonly_cpp
- initonly
helpviewer_keywords:
- initonly attribute [C++]
ms.assetid: f745d7fa-dc08-46f1-9b97-0977be58a008
ms.openlocfilehash: 85a127398997872a20a2360f1a852ebaaf17e33b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651281"
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

[Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)