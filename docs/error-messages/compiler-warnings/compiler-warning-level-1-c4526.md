---
title: Compilerwarnung (Stufe 1) C4526
ms.date: 11/04/2016
f1_keywords:
- C4526
helpviewer_keywords:
- C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
ms.openlocfilehash: 892e6c37e54a868be48ced35354a1096aa7bf9d3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536715"
---
# <a name="compiler-warning-level-1-c4526"></a>Compilerwarnung (Stufe 1) C4526

'Funktion': statische Memberfunktion kann nicht virtuelle Funktion überschreiben ' virtuelle function'override ignoriert, virtuelle Funktion ausgeblendet

Die statische Memberfunktion erfüllt die Kriterien, um die virtuelle Funktion, außer Kraft setzen, wodurch die Member-Funktion sowohl virtuelle als auch statische.

Der folgende Code generiert C4526:

```
// C4526.cpp
// compile with: /W1 /c
// C4526 expected
struct myStruct1 {
   virtual void __stdcall func( int ) = 0;
};

struct myStruct2: public myStruct1 {
   static void __stdcall func( int );
};
```

Im folgenden sind mögliche Lösungen:

- Wenn die Funktion vorgesehen war, um eine virtuelle Funktion der Basisklasse zu überschreiben, entfernen Sie den static-Spezifizierer.

- Wenn die Funktion eine statische Memberfunktion sein sollte, benennen Sie sie nicht in Konflikt mit der virtuellen Basisklasse-Funktion.