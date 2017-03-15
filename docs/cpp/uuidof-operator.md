---
title: "__uuidof-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__LIBID_"
  - "__LIBID_cpp"
  - "__uuidof"
  - "__uuidof_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__LIBID_-Schlüsselwort [C++]"
  - "__uuidof-Schlüsselwort [C++]"
ms.assetid: badfe709-809b-4b66-ad48-ee35039d25c6
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# __uuidof-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ruft die GUID ab, die dem Ausdruck angefügt ist.  
  
## Syntax  
  
```  
  
      __uuidof (  
   expression   
)  
```  
  
## Hinweise  
 Der *Ausdruck* kann ein Typname, ein Zeiger, ein Verweis oder ein Array dieses Typs, eine Vorlage, die auf diese Typen spezialisiert ist, oder eine Variable dieser Typen sein.  Das Argument ist gültig, solange der Compiler es verwenden kann, um das angefügte GUID zu suchen.  
  
 Ein Sonderfall dieser systeminternen Funktion liegt vor, wenn entweder **0** oder **NULL** als Argument angegeben wird.  In diesem Fall gibt `__uuidof` eine GUID zurück, die aus Nullen besteht.  
  
 Verwenden Sie dieses Schlüsselwort, um die an folgende Elemente angefügte GUID zu extrahieren:  
  
-   Ein Objekt durch das erweiterte [uuid](../cpp/uuid-cpp.md)\-Attribut.  
  
-   Ein Bibliotheksblock, der mit dem [module](../windows/module-cpp.md)\-Attribut erstellt wird.  
  
> [!NOTE]
>  In einem Debugbuild initialisiert `__uuidof` ein Objekt immer dynamisch \(zur Laufzeit\).  In einem Releasebuild kann `__uuidof` ein Objekt statistisch initialisieren \(zur Kompilierzeit\).  
  
## Beispiel  
 Mit dem folgenden Code \(kompiliert mit "ole32.lib"\) wird das "uuid" eines Bibliotheksblocks angezeigt, der mit dem Modulattribut erstellt wird:  
  
```  
// expre_uuidof.cpp  
// compile with: ole32.lib  
#include "stdio.h"  
#include "windows.h"  
  
[emitidl];  
[module(name="MyLib")];  
[export]  
struct stuff {  
   int i;  
};  
  
int main() {  
   LPOLESTR lpolestr;  
   StringFromCLSID(__uuidof(MyLib), &lpolestr);  
   wprintf_s(L"%s", lpolestr);  
   CoTaskMemFree(lpolestr);  
}  
```  
  
## Kommentare  
 In Fällen, in denen sich der Bibliotheksname nicht mehr im Gültigkeitsbereich befindet, können Sie \_\_LIBID\_ anstelle von `__uuidof` verwenden.  Beispiel:  
  
```  
StringFromCLSID(__LIBID_, &lpolestr);  
```  
  
 **Ende Microsoft\-spezifisch**  
  
## Siehe auch  
 [Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)