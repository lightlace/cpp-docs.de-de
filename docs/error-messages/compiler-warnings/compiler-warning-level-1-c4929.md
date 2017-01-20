---
title: "Compilerwarnung (Stufe 1) C4929"
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
  - "C4929"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4929"
ms.assetid: 95f8ab4f-4468-4caa-acd5-8f4592f03b3c
caps.latest.revision: 17
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4929
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Datei': Die Typbibliothek enthält eine Union. Der 'embedded\_idl'\-Qualifizierer wird ignoriert.  
  
 Das embedded\_idl\-Attribut von [\#import](../../preprocessor/hash-import-directive-cpp.md) konnte nicht auf die Typbibliothek angewendet werden, da sich in ihr eine Union befindet.  Verwenden Sie embedded\_idl nicht, um diese Warnung zu umgehen.  
  
## Beispiel  
 Das folgende Beispiel legt eine Komponente fest.  
  
```  
// C4929a.cpp  
// compile with: /LD /link /TLBOUT:C4929a.tlb  
#include <objbase.h>  
[module(name="Test")];  
[public, switch_type(short)] typedef union _TD_UNION_TYPE   {  
   [case(24)]  
      float fM;  
   [case(25)]  
      double dMN;  
   [default]  
      int x;  
} TD_UNION_TYPE;  
  
[export, public] typedef struct _TDW_TYPE {  
   [switch_is(sU)] TD_UNION_TYPE w;  
      short sU;  
} TD_TYPE;  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface I {  
   HRESULT f(TD_TYPE*);  
};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000002")]  
struct C : I {  
   HRESULT f(TD_TYPE*) { return 0; }  
};  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C4929 generiert.  
  
```  
// C4929b.cpp  
// compile with: /c /W1  
#import "C4929a.tlb" embedded_idl   // C4929  
```