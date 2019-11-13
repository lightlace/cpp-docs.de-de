---
title: Compilerwarnung (Stufe 1) C4526
ms.date: 11/04/2016
f1_keywords:
- C4526
helpviewer_keywords:
- C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
ms.openlocfilehash: 60ac01d6a118f37a22b39ab41fa60252866f3360
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966271"
---
# <a name="compiler-warning-level-1-c4526"></a>Compilerwarnung (Stufe 1) C4526

"Funktion": die statische Member-Funktion kann die virtuelle Funktion "virtuelle Funktion nicht überschreiben" ignoriert, die virtuelle Funktion wird ausgeblendet.

Die statische Member-Funktion erfüllt die Kriterien, um die virtuelle Funktion zu überschreiben, wodurch der Member sowohl virtuell als auch statisch wird.

Der folgende Code generiert C4526:

```cpp
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

Die folgenden Fehlerbehebungen sind möglich:

- Wenn die Funktion dazu gedacht war, die virtuelle Funktion der Basisklasse zu überschreiben, entfernen Sie den statischen Spezifizierer.

- Wenn die Funktion eine statische Element Funktion sein soll, benennen Sie Sie um, sodass Sie nicht mit der virtuellen Funktion der Basisklasse in Konflikt steht.