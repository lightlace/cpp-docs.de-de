---
title: "Definitionen und Deklarationen (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 56b809c0-e602-4f18-9ca5-cd7a8fbaaf30
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Definitionen und Deklarationen (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Die DLL\-Schnittstelle bezieht sich auf alle Elemente \(Funktionen und Daten\), von denen bekannt ist, dass sie von irgend einem Programm im System exportiert werden; das heißt, alle Elemente, die als **dllimport** oder `dllexport` deklariert werden.  Alle Deklarationen, die in der DLL\-Schnittstelle eingeschlossen sind, müssen das **dllimport**\- oder das `dllexport`\-Attribut angeben.  Allerdings muss die Definition nur das `dllexport`\-Attribut angeben.  Beispielsweise verursacht die folgende Funktionsdefinition einen Compilerfehler:  
  
```  
__declspec( dllimport ) int func() {   // Error; dllimport  
                                    // prohibited on definition.  
   return 1;  
}  
```  
  
 Dieser Code generiert außerdem einen Fehler:  
  
```  
#define DllImport   __declspec( dllimport )  
  
__declspec( dllimport ) int i = 10;  // Error; this is a  
                                     // definition.  
```  
  
 Dies ist jedoch die richtige Syntax:  
  
```  
__declspec( dllexport ) int i = 10;     // Okay--export definition  
```  
  
 Die Verwendung von `dllexport` setzt eine Definition voraus, während **dllimport** eine Deklaration impliziert.  Sie müssen das `extern`\-Schlüsselwort mit `dllexport` verwenden, um eine Deklaration zu erzwingen; andernfalls wird eine Definition impliziert.  Daher sind die folgenden Beispiele richtig:  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
extern DllImport int k; // These are both correct and imply a  
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
  
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)