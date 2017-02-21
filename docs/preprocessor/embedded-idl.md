---
title: "embedded_idl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "embedded_idl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "embedded_idl-Attribut"
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# embedded_idl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Gibt an, dass die Typbibliothek in die TLH\-Datei geschrieben wird und der vom Attribut generierte Code beibehalten wird.  
  
## Syntax  
  
```  
embedded_idl[("param")]  
```  
  
#### Parameter  
 `param`  
 Kann einer von zwei Werten sein:  
  
-   emitidl: Typinformationen, die von typelib importiert werden, sind in der IDL\-Datei vorhanden, die für das attributierte Projekt generiert wird.  Dies ist die Standardeinstellung, die aktiv ist, wenn Sie keinen Parameter für `embedded_idl` angeben.  
  
-   no\_emitidl: Typinformationen, die von typelib importiert werden, sind nicht in der IDL\-Datei vorhanden, die für das attributierte Projekt generiert wird.  
  
## Beispiel  
  
```  
// import_embedded_idl.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib2")];  
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")  
```  
  
## Hinweise  
 **Ende C\+\+\-spezifisch**  
  
## Siehe auch  
 [\#import\-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import\-Direktive](../preprocessor/hash-import-directive-cpp.md)