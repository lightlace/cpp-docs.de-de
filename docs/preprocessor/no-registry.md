---
title: "no_registry"
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
  - "no_registry"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "no_registry-Attribut"
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# no_registry
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`no_registry` weist den Compiler an, nicht die Registrierung für Typbibliotheken zu suchen, die mit `#import` importiert werden.  
  
## Syntax  
  
```  
  
#import filename no_registry  
```  
  
#### Parameter  
 *filename*  
 Eine Typbibliothek.  
  
## Hinweise  
 Wenn keine referenzierte Typbibliothek in den Includeverzeichnissen gefunden wird, schlägt die Kompilierung fehl, selbst wenn die Typbibliothek in der Registrierung enthalten ist. `no_registry` überträgt auf andere Typbibliotheken, die implizit mit `auto_search` importiert werden.  
  
 Der Compiler durchsucht niemals die Registrierung nach Typbibliotheken, die mit Dateinamen angegeben und direkt an `#import` übergeben werden.  
  
 Wenn `auto_search` angegeben wird, werden die zusätzlichen `#import`s mit der `no_registry`\-Einstellung des ursprünglichen `#import` generiert \(wenn die ursprüngliche `#import`\-Direktive `no_registry` war, ist ein mit `auto_search` generiertes `#import` ebenfalls `no_registry`\).  
  
 `no_registry` ist hilfreich, wenn Sie Typbibliotheken mit Querverweis importieren möchten, ohne das Risiko einzugehen, dass der Compiler eine ältere Version der Datei in der Registrierung findet. `no_registry` ist auch nützlich, wenn die Typbibliothek nicht registriert wird.  
  
## Siehe auch  
 [\#import\-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import\-Direktive](../preprocessor/hash-import-directive-cpp.md)