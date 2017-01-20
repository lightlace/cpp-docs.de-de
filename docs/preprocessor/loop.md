---
title: "Schleife"
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
  - "loop_CPP"
  - "vc-pragma.loop"
dev_langs: 
  - "C++"
ms.assetid: 6d5bb428-cead-47e7-941d-7513bbb162c7
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Schleife
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Steuert, wie Schleifencode durch die automatische Parallelisierung berücksichtigt werden soll und\/oder schließt eine Schleife von der Berücksichtigung durch die automatische Vektorisierung aus.  
  
## Syntax  
  
```  
  
#pragma loop( hint_parallel(n) )  
```  
  
```  
  
#pragma loop( no_vector )  
```  
  
```  
  
#pragma loop( ivdep )  
```  
  
#### Parameter  
 `hint_parallel(` `n` `)`  
 Weist den Compiler darauf hin, dass diese Schleife über `n` Threads parallelisiert werden soll, wobei `n` ein positives Ganzzahlliteral oder null ist.  Wenn `n` null ist, wird die maximale Anzahl von Threads zur Laufzeit verwendet.  Dies ist ein Hinweis für den Compiler, kein Befehl, und es gibt keine Garantie dafür, dass die Schleife parallelisiert wird.  Wenn die Schleife Datenabhängigkeiten oder strukturelle Probleme aufweist, z. B. in der Schleife in einen über den Schleifentext hinaus verwendeten Skalar gespeichert wird, dann wird die Schleife nicht parallelisiert.  
  
 Der Compiler ignoriert diese Option, es sei denn, der [\/Qpar](../build/reference/qpar-auto-parallelizer.md)\-Compilerschalter wird angegeben.  
  
 `no_vector`  
 Standardmäßig ist die automatische Vektorisierung aktiviert und versucht, alle Schleifen zu vektorisieren, für die dies als nützlich bewertet wird.  Geben Sie dieses Pragma an, um die automatische Vektorisierung für die darauf folgende Schleife zu deaktivieren.  
  
 `ivdep`  
 Weist den Compiler darauf hin, Vektorabhängigkeiten für diese Schleife zu ignorieren.  Verwenden Sie diesen Parameter in Verbindung mit `hint_parallel`.  
  
## Hinweise  
 Um das `loop`\-Pragma zu verwenden, platzieren Sie es direkt vor eine Schleifendefinition, nicht in dieser.  Das Pragma gilt für den Gültigkeitsbereich der Schleife, die darauf folgt.  Sie können mehrere Pragmas in beliebiger Reihenfolge auf eine Schleife anwenden, aber Sie müssen jedes in einer separaten Pragmaanweisung angeben.  
  
## Siehe auch  
 [Automatische Parallelisierung und automatische Vektorisierung](../parallel/auto-parallelization-and-auto-vectorization.md)   
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)