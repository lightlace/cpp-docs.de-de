---
title: Compilerwarnung (Stufe 1) C4526 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4526
dev_langs:
- C++
helpviewer_keywords:
- C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ed6f2da3252c27b7a84b4d5b73f7e8ba52823dd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118504"
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