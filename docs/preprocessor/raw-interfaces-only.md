---
title: "raw_interfaces_only | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "raw_interfaces_only"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "raw_interfaces_only-Attribut"
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# raw_interfaces_only
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Unterdrückt die Generierung von Fehlerbehandlungs\-Wrapperfunktionen und [Eigenschaft](../cpp/property-cpp.md)\-Deklarationen, die diese Wrapperfunktionen verwenden.  
  
## Syntax  
  
```  
raw_interfaces_only  
```  
  
## Hinweise  
 Das `raw_interfaces_only`\-Attribut bewirkt auch die Entfernung des Standardpräfixes, das beim Benennen der Funktionen, die keine Eigenschaften sind, verwendet wird.  Normalerweise ist das Präfix **raw\_**.  Wenn dieses Attribut festgelegt wird, stammen die Funktionsnamen direkt aus der Typbibliothek.  
  
 Dieses Attribut ermöglicht, dass Sie nur die Inhalte auf niedriger Ebene aus der Typbibliothek verfügbar machen.  
  
 **Ende C\+\+\-spezifisch**  
  
## Siehe auch  
 [\#import\-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import\-Direktive](../preprocessor/hash-import-directive-cpp.md)