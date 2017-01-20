---
title: "restrict"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "restrict"
  - "restrict_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec-Schlüsselwort [C++], restrict"
  - "restrict __declspec-Schlüsselwort"
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# restrict
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Angewendet auf eine Funktionsdeklaration oder eine Definition, die einen Zeigertyp zurückgibt und dem Compiler mitgeteilt, dass die Funktion ein Objekt zurückgibt, das keinen Alias mit anderen Zeigern besitzt.  
  
## Syntax  
  
```  
__declspec(restrict) return_type f();  
```  
  
## Hinweise  
 Der Compiler gibt `__declspec(restrict)` weiter.  Beispielsweise wird die CRT\-Funktion `malloc` mit `__declspec(restrict)` ausgestattet. Daher wird auch impliziert, dass initialisierte Zeiger auf Speicheradressen `malloc` nicht mit einem Alias versehen werden.  
  
 Der Compiler überprüft nicht, ob der Zeiger tatsächlich keinen Alias besitzt.  Es liegt in der Verantwortung des Entwicklers, sicherzustellen, dass das Programm einem Zeiger, der mit dem `restrict __declspec`\-Modifizierer markiert ist, keinen Alias zuweist.  
  
 Eine ähnliche Semantik für Variablen finden Sie unter [\_\_restrict](../cpp/extension-restrict.md).  
  
## Beispiel  
 Ein Beispiel für die Verwendung von `restrict` finden Sie unter [noalias](../cpp/noalias.md).  
  
 Informationen zum restrict\-Schlüsselwort, das Bestandteil von C\+\+ AMP ist, finden Sie unter [restrict \(C\+\+ AMP\)](../cpp/restrict-cpp-amp.md).  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)