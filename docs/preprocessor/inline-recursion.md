---
title: "inline_recursion"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "inline_recursion_CPP"
  - "vc-pragma.inline_recursion"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "inline_recursion-Pragma"
  - "Pragmas, inline_recursion"
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# inline_recursion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Steuert die Inlineerweiterung von direkten oder wechselseitig rekursiven Funktionsaufrufen.  
  
## Syntax  
  
```  
  
#pragma inline_recursion( [{on | off}] )  
```  
  
## Hinweise  
 Verwenden Sie dieses Pragma zum Steuern von Funktionen, die als [inline](../misc/inline-inline-forceinline.md) und [\_\_inline](../misc/inline-inline-forceinline.md) markiert sind, oder zum Steuern von Funktionen, die der Compiler automatisch unter der Option "\/Ob2" erweitert.  Die Verwendung dieses Pragmas erfordert eine [\/Ob](../build/reference/ob-inline-function-expansion.md)\-Compileroptionseinstellung von 1 oder 2.  Standardmäßig ist `inline_recursion` deaktiviert.  Dieses Pragma tritt mit dem ersten Funktionsaufruf in Kraft, nachdem das Pragma angezeigt wird, und hat keinen Einfluss auf die Definition der Funktion.  
  
 Das `inline_recursion`\-Pragma legt fest, wie rekursive Funktionen erweitert werden.  Wenn `inline_recursion` deaktiviert ist und eine Inlinefunktion sich selbst aufruft \(entweder direkt oder indirekt\), wird die Funktion nur einmal erweitert.  Wenn `inline_recursion` aktiviert ist, wird die Funktion mehrmals erweitert, bis entweder der Wert erreicht ist, der mit dem [inline\_depth](../preprocessor/inline-depth.md)\-Pragma festgelegt ist \(dem Standardwert für rekursive Funktionen, der durch das `inline_depth`\-Pragma definiert wird\), oder bis das Kapazitätslimit erreicht ist.  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline\_depth](../preprocessor/inline-depth.md)   
 [\/Ob \(Inlinefunktionserweiterung\)](../build/reference/ob-inline-function-expansion.md)