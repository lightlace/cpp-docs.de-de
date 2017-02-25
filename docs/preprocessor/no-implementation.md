---
title: "no_implementation | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "no_implementation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "no_implementation-Attribut"
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
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