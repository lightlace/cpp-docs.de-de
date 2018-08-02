---
title: Definitionen und Deklarationen (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 56b809c0-e602-4f18-9ca5-cd7a8fbaaf30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5d192234a2b3cd3d72bef15e11678ebc41ccede0
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462887"
---
# <a name="definitions-and-declarations-c"></a>Definitionen und Deklarationen (C++)
**Microsoft Specific** die DLL-Schnittstelle bezieht sich auf alle Elemente (Funktionen und Daten), von denen bekannt, die durch ein Programm im System exportiert werden, d. h., alle Elemente, die als deklariert sind **Dllimport** oder **Dllexport** . Alle Deklarationen, die in der DLL-Schnittstelle eingeschlossen geben die **Dllimport** oder **Dllexport** Attribut. Die Definition muss jedoch angeben, nur die **Dllexport** Attribut. Beispielsweise verursacht die folgende Funktionsdefinition einen Compilerfehler:

```
__declspec( dllimport ) int func() {   // Error; dllimport
                                       // prohibited on definition.
   return 1;  
}
```

 Dieser Code generiert außerdem einen Fehler:

```
__declspec( dllimport ) int i = 10;  // Error; this is a definition.
```

 Dies ist jedoch die richtige Syntax:

```
__declspec( dllexport ) int i = 10;  // Okay--export definition
```

 Die Verwendung von **Dllexport** impliziert eine Definition, während **Dllimport** eine Deklaration impliziert. Verwenden Sie die **"extern"** Schlüsselwort mit **Dllexport** auf eine Deklaration zu erzwingen; andernfalls wird eine Definition impliziert. Daher sind die folgenden Beispiele richtig:

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

extern DllExport int k; // These are both correct and imply a
DllImport int j;        // declaration.
```

 Das vorherige Beispiel wird anhand der folgenden Beispiele verdeutlicht:

```
static __declspec( dllimport ) int l; // Error; not declared extern.

void func() {
    static __declspec( dllimport ) int s;  // Error; not declared
                                           // extern.
    __declspec( dllimport ) int m;         // Okay; this is a
                                           // declaration.
    __declspec( dllexport ) int n;         // Error; implies external
                                           // definition in local scope.
    extern __declspec( dllimport ) int i;  // Okay; this is a
                                           // declaration.
    extern __declspec( dllexport ) int k;  // Okay; extern implies
                                           // declaration.
    __declspec( dllexport ) int x = 5;     // Error; implies external
                                           // definition in local scope.
}
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)