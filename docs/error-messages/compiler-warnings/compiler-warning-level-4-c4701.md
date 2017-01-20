---
title: "Compilerwarnung (Stufe 4) C4701"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4701"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4701"
ms.assetid: d7c76c66-1f3f-4d3c-abe4-5d94c84a5a1f
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4701
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vielleicht nicht initialisierte lokale Variable "Name" verwendet  
  
 Die lokale Variable *name* verwendet worden, ohne einen Wert zugewiesen werden.  Dies kann zu unvorhersehbaren Ergebnissen führen.  
  
## Beispiel  
 Der folgende Code generiert C4701 und C4703.  
  
```cpp  
#include <malloc.h>  
  
void func(int size)  
{  
    void* p;  
    if (size < 256) {  
        p = malloc(size);  
    }  
  
    if (p != nullptr) // C4701 and C4703  
        free(p);  
}  
  
void main()  
{  
    func(9);  
}  
```  
  
  **c:\\src\\test.cpp\(10\) : Warnung C4701: möglicherweise nicht initialisierte lokale Variable "p" verwendet**  
 **c:\\src\\test.cpp\(10\) : Warnung C4703: möglicherweise nicht initialisierte lokale Zeigervariable "p" verwendet** Um diese Warnung zu korrigieren, initialisieren Sie die Variable wie in diesem Beispiel dargestellt:  
  
```cpp  
#include <malloc.h>  
  
void func(int size)  
{  
    void* p = nullptr;  
    if (size < 256) {  
        p = malloc(size);  
    }  
  
    if (p != nullptr)  
        free(p);  
}  
  
void main()  
{  
    func(9);  
}  
```  
  
## Siehe auch  
 [Compilerwarnung \(Stufe 4\) C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)   
 [Warnungen, \/sdl und das Verbessern nicht initialisierter variable Erkennung](http://blogs.msdn.com/b/sdl/archive/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection.aspx)