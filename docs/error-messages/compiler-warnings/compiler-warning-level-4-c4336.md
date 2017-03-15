---
title: "Compilerwarnung (Stufe 4) C4336 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4336"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4336"
ms.assetid: 93f199dd-d6dd-42c0-82d8-c12d101a7235
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerwarnung (Stufe 4) C4336
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Importieren Sie zuerst die übergreifende Typbibliothek "Typbibliothek1", bevor Sie "Typbibliothek2" importieren  
  
 Auf eine Typbibliothek wurde mit der [\#import](../../preprocessor/hash-import-directive-cpp.md)\-Direktive verwiesen.  Die Typbibliothek enthielt jedoch einen Verweis auf eine andere Typbibliothek, auf die nicht mit `#import` verwiesen wurde.  Diese andere TLB\-Datei wurde vom Compiler gefunden.  
  
 Angenommen, Sie verfügen über zwei auf einem Datenträger gespeicherte Typbibliotheken, die aus den folgenden beiden \(mit midl.exe kompilierten\) Dateien erstellt wurden:  
  
```  
// c4336a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library c4336aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]  
   enum E_C4336  
   {  
      one, two, three  
   };  
};  
```  
  
 Die zweite Typbibliothek:  
  
```  
// c4336b.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
library C4336bLib  
{  
   importlib ("c4336a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
   struct S_C4336  
   {  
      enum E_C4336 e;  
   };  
};  
```  
  
 Im folgenden Beispiel wird C4336 generiert:  
  
```  
// C4336.cpp  
// compile with: /W4 /LD  
// #import "C4336a.tlb"  
#import "C4336b.tlb"   // C4336, uncomment previous line to resolve  
```