---
title: Definitionen und Deklarationen (C++) | Microsoft Docs
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
ms.openlocfilehash: 742270c77d47c178d0254ca9b9882f73fe3b8293
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411766"
---
# <a name="definitions-and-declarations-c"></a>Definitionen und Deklarationen (C++)
## <a name="microsoft-specific"></a>Microsoft-spezifisch
 Die DLL-Schnittstelle bezieht sich auf alle Elemente (Funktionen und Daten), die bekanntermaßen von einem Programm im System exportiert werden soll. d. h., alle Elemente, die als deklariert werden `dllimport` oder `dllexport`. Alle Deklarationen, die in der DLL-Schnittstelle eingeschlossen müssen Geben Sie entweder die `dllimport` oder `dllexport` Attribut. Allerdings muss die Definition nur das `dllexport`-Attribut angeben. Beispielsweise verursacht die folgende Funktionsdefinition einen Compilerfehler:

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

 Die Verwendung von `dllexport` eine Definition impliziert während `dllimport` eine Deklaration impliziert. Sie müssen das `extern`-Schlüsselwort mit `dllexport` verwenden, um eine Deklaration zu erzwingen; andernfalls wird eine Definition impliziert. Daher sind die folgenden Beispiele richtig:

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
