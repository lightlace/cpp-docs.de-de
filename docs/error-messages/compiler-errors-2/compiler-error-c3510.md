---
title: "Compilerfehler C3510 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3510"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3510"
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C3510
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die abhängige Typbibliothek 'Typbib' wurde nicht gefunden.  
  
 [no\_registry](../../preprocessor/no-registry.md) und [auto\_search](../../preprocessor/auto-search.md) sind an `#import` weitergegeben worden, der Compiler ist jedoch nicht in der Lage, eine referenzierte Typbibliothek zu finden.  
  
 Um diesen Fehler zu beheben, stellen Sie sicher, dass alle Typbibliotheken und referenzierten Typbibliotheken für den Compiler verfügbar sind.  
  
 Im folgenden Beispiel wird C3510 generiert:  
  
 Angenommen, es wurden die folgenden zwei Typbibliotheken erstellt, und C3510a.tlb ist gelöscht worden oder befindet sich nicht im Pfad.  
  
```  
// C3510a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library C3510aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]  
   enum E_C3510  
   {  
      one, two, three  
   };  
};  
```  
  
 Der Quellcode für die zweite Typbibliothek lautet wie folgt:  
  
```  
// C3510b.idl  
// post-build command: del /f C3510a.tlb  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
library C3510bLib  
{  
   importlib ("C3510a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
   struct S_C3510 {  
      enum E_C3510 e;  
   };  
};  
```  
  
 Schließlich lautet der Clientcode wie folgt:  
  
```  
// C3510.cpp  
#import "c3510b.tlb" no_registry auto_search   // C3510  
int main() {  
   C3510aLib::S_C4336 ccc;  
}  
```