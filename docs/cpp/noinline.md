---
title: "noinline | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "noinline"
  - "noinline_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec-Schlüsselwort [C++], noinline"
  - "noinline __declspec-Schlüsselwort"
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# noinline
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 **\_\_declspec\(noinline\)** weist den Compiler an, eine Memberfunktion nie mit einer bestimmten Funktion in einer Klasse inline zu setzen.  
  
 Es lohnt sich möglicherweise, eine Funktion nicht inline auszuführen, wenn die Funktion klein und für die Leistung des Codes nicht wichtig ist.  Das ist der Fall, wenn die Funktion klein ist und wahrscheinlich nicht häufig aufgerufen wird, z. B. eine Funktion, die eine Fehlerbedingung behandelt.  
  
 Beachten Sie Folgendes: Wenn eine Funktion als `noinline` markiert ist, ist die aufrufende Funktion kleiner und somit selbst ein Kandidat für Compiler\-Inlining.  
  
```  
class X {  
   __declspec(noinline) int mbrfunc() {  
      return 0;   
   }   // will not inline  
};  
```  
  
## END Microsoft\-spezifisch  
  
## Siehe auch  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [inline, \_\_inline, \_\_forceinline](../misc/inline-inline-forceinline.md)