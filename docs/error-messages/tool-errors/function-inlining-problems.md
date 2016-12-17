---
title: "Probleme bei Inlinefunktionen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Ob1 (C++-Compileroption)"
  - "/Ob2 (C++-Compileroption)"
  - "Probleme bei Inlinefunktionen"
  - "Inlinefunktionen, Probleme"
  - "-Ob1 (C++-Compileroption)"
  - "-Ob2 (C++-Compileroption)"
ms.assetid: 65d59943-4b3c-4a43-aeb6-dccbf7686740
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Probleme bei Inlinefunktionen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bei der Verwendung von Inlinefunktionen sollte Folgendes beachtet werden:  
  
-   Inlinefunktionen müssen in der Headerdatei implementiert werden, die eingelesen wird.  
  
-   Die Verwendung von Inlinefunktionen muss in der Headerdatei aktiviert sein.  
  
```  
// LNK2019_function_inline.cpp  
// compile with: /c   
// post-build command: lib LNK2019_function_inline.obj  
#include <stdio.h>  
struct _load_config_used {  
   void Test();  
   void Test2() { printf("in Test2\n"); }  
};  
  
void _load_config_used::Test() { printf("in Test\n"); }  
```  
  
 und anschließend  
  
```  
// LNK2019_function_inline_2.cpp  
// compile with: LNK2019_function_inline.lib  
struct _load_config_used {  
   void Test();  
   void Test2();  
};  
  
int main() {  
   _load_config_used x;  
   x.Test();  
   x.Test2();   // LNK2019  
}  
```  
  
 Falls Sie die Compilerdirektive `#pragma inline_depth` verwenden, stellen Sie sicher, dass mindestens ein Wert von 2 festgelegt wurde.  Durch den Wert 0 wird die Unterstützung von Inlinefunktionen deaktiviert.  Achten Sie außerdem darauf, die Compileroption **\/Ob1** oder **\/Ob2** zu verwenden.  
  
 Das Kombinieren von Inline\- und Nicht\-Inlinecompileroptionen bei verschiedenen Modulen kann zeitweise zu Problemen führen.  Wenn eine C\+\+\-Bibliothek mit aktivierten Inlinefunktionen \([\/Ob1](../../build/reference/ob-inline-function-expansion.md) oder [\/Ob2](../../build/reference/ob-inline-function-expansion.md)\) erstellt wird, Inlinefunktionen in der zugehörigen Headerdatei mit den Funktionsbeschreibungen jedoch deaktiviert sind \(keine Option\), erhalten Sie den Fehler LNK2001.  Die Funktionen werden nicht "inline" im Code der Headerdatei deklariert. Da sie sich jedoch nicht in der Bibliotheksdatei befinden, existiert keine Adresse, um den Verweis aufzulösen.  
  
 Auch bei einem Projekt, das Inlinefunktionen verwendet und die Funktionen in einer CPP\-Datei und nicht in der Headerdatei definiert, tritt LNK2019 auf.  Zwar wird die Headerdatei an jeder geeigneten Stelle eingelesen, die Funktionen werden jedoch nur "inline" deklariert, wenn die CPP\-Datei vom Compiler verarbeitet wird. Daher werden diese Funktionen vom Linker als nicht aufgelöste externe Verweise angesehen, wenn sie in anderen Modulen verwendet werden.  
  
```  
// LNK2019_FIP.h  
struct testclass {  
   void PublicStatMemFunc1(void);  
};  
```  
  
 und anschließend  
  
```  
// LNK2019_FIP.cpp  
// compile with: /c  
#include "LNK2019_FIP.h"  
inline void testclass::PublicStatMemFunc1(void) {}  
```  
  
 und anschließend  
  
```  
// LNK2019_FIP_2.cpp  
// compile with: LNK2019_FIP.cpp  
// LNK2019 expected  
#include "LNK2019_FIP.h"  
int main() {  
   testclass testclsObject;  
  
   // module cannot see the implementation of PublicStatMemFunc1  
   testclsObject.PublicStatMemFunc1();  
}  
```  
  
## Siehe auch  
 [Linkertoolfehler LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)