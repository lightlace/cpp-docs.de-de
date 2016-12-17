---
title: "no_implementation"
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
  - "no_implementation"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "no_implementation-Attribut"
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# no_implementation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Unterdrückt die Generierung des TLI\-Headers, der die Implementierungen der Wrappermemberfunktionen enthält.  
  
## Syntax  
  
```  
no_implementation  
```  
  
## Hinweise  
 Wenn dieses Attribut festgelegt ist, wird der TLH\-Header mit den Deklarationen zur Bereitstellung von Typbibliothekselementen ohne eine `#include`\-Anweisung zur Einbindung der TLI\-Headerdatei generiert.  
  
 Dieses Attribut wird in Verbindung mit [implementation\_only](../preprocessor/implementation-only.md) verwendet.  
  
 **Ende C\+\+\-spezifisch**  
  
## Siehe auch  
 [\#import\-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import\-Direktive](../preprocessor/hash-import-directive-cpp.md)