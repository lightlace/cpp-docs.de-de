---
title: Definitionen und Deklarationen (C++)
ms.date: 11/04/2016
ms.assetid: 56b809c0-e602-4f18-9ca5-cd7a8fbaaf30
ms.openlocfilehash: 987e27bdf35eba7d9380fc546c15b93b3179333b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392244"
---
# <a name="definitions-and-declarations-c"></a>Definitionen und Deklarationen (C++)

**Microsoft-spezifisch**

Die DLL-Schnittstelle bezieht sich auf alle Elemente (Funktionen und Daten), die bekanntermaßen von einem Programm im System exportiert werden. d. h. alle Elemente, die als deklariert sind **Dllimport** oder **Dllexport**. Alle Deklarationen, die in der DLL-Schnittstelle eingeschlossen geben die **Dllimport** oder **Dllexport** Attribut. Die Definition muss jedoch angeben, nur die **Dllexport** Attribut. Beispielsweise verursacht die folgende Funktionsdefinition einen Compilerfehler:

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