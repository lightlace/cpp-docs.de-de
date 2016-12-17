---
title: "inline_depth"
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
  - "inline_depth_CPP"
  - "vc-pragma.inline_depth"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "inline_depth-Pragma"
  - "Pragmas, inline_depth"
ms.assetid: 2bba60fe-43ea-4d09-90f7-aafaba3bad07
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# inline_depth
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt die heuristische Inlinesuchtiefe an, sodass keine Funktion "inline" ist, wenn die Tiefe im Aufrufdiagramm größer als `n` ist.  
  
## Syntax  
  
```  
  
#pragma inline_depth( [n] )  
```  
  
## Hinweise  
 Dieses Pragma steuert das Inlining von Funktionen, die als [inline](../misc/inline-inline-forceinline.md) und [\_\_inline](../misc/inline-inline-forceinline.md) markiert wurden, oder für die das Inlining automatisch unter der \/Ob2\-Option stattfindet.  
  
 `n` kann ein Wert zwischen 0 und 255 sein, wobei 255 unendliche Tiefe im Aufrufdiagramm bedeutet, und NULL die Inlineerweiterung unterdrückt.  Wenn `n` nicht angegeben ist, wird der Standardwert \(254\) verwendet.  
  
 Das Pragma **inline\_depth** steuert, wie oft eine Serie von Funktionsaufrufen erweitert werden kann.  Wenn die Inlinetiefe z. B. vier ist und A B aufruft und B dann C, werden alle drei Aufrufe inline erweitert.  Wenn jedoch die nächste Inlineerweiterung zwei ist, werden nur A und B erweitert, und C bleibt als Funktionsaufruf bestehen.  
  
 Um dieses Pragma verwenden zu können, müssen Sie die \/Ob\-Compilerfunktion auf 1 oder 2 festlegen.  Die bei der Verwendung dieses Pragma festgelegte Tiefe ist beim ersten Funktionsaufruf nach dem Pragma wirksam.  
  
 Die Inlinetiefe kann während der Erweiterung verringert, aber nicht erhöht werden.  Wenn die Inlinetiefe sechs ist und der Präprozessor während der Erweiterung ein **inline\_depth**\-Pragma mit einem Wert von acht antrifft, bleibt die Tiefe sechs.  
  
 Das Pragma **inline\_depth** wirkt sich nicht auf Funktionen aus, die mit `__forceinline` markiert sind.  
  
> [!NOTE]
>  Rekursive Funktionen können inline in einer maximalen Tiefe von 16 Aufrufen ersetzt werden.  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline\_recursion](../preprocessor/inline-recursion.md)