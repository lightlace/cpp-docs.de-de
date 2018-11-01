---
title: Compilerwarnung (Stufe 4) C4337
ms.date: 11/04/2016
f1_keywords:
- C4337
helpviewer_keywords:
- C4337
ms.assetid: 70bc72d9-aac5-45cd-abd3-ebe42a05897b
ms.openlocfilehash: 2bfa5f9b30fa0325df1c3655ded53ab0525449c3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479559"
---
# <a name="compiler-warning-level-4-c4337"></a>Compilerwarnung (Stufe 4) C4337

die übergreifende Typbibliothek 'Typbibliothek1' in 'Typbibliothek2' wird automatisch importiert

Das Auto_search-Attribut des [die #import-Direktive](../../preprocessor/hash-import-directive-cpp.md) wurde eine Typbibliothek implizit importiert werden.

Zwei Typbibliotheken auf dem Datenträger, die von den folgenden zwei Dateien (kompiliert mit midl.exe) erstellt:

```
// C4337a.idl
[
  uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12B)
]
library C4337aLib
{
   [uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12C)]
   enum E_C4337a
   {
      one = 0,
      two = 1,
      three = 2
    };
};
```

und klicken Sie dann die zweite IDL-Datei,

```
// C4337b.idl
[
   uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12D)
]

library C4337bLib
{
   importlib("c4337a.tlb");

   [uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12E)]
   struct S_C4337b
   {
      enum E_C4337a e;
   };
};
```

Im folgende Beispiel wird die C4337 generiert:

```
// C4337.cpp
// compile with: /W4 /LD
#import "c4337b.tlb" auto_search   // C4337
// explicitly #import all type libraries to resolve
// #import "C4337a.tlb"
// #import "C4337b.tlb"
```