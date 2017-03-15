---
title: "no_dual_interfaces | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "no_dual_interfaces"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "no_dual_interfaces-Attribut"
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# no_dual_interfaces
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Ändert die Art, mit der der Compiler Wrapperfunktionen für Methoden der dualen Schnittstelle generiert.  
  
## Syntax  
  
```  
no_dual_interfaces  
```  
  
## Hinweise  
 Normalerweise ruft der Wrapper die Methode über die virtuelle Funktionstabelle für die Schnittstelle auf.  Mit `no_dual_interfaces` ruft der Wrapper stattdessen **IDispatch::Invoke** auf, um die Methode aufzurufen.  
  
 **Ende C\+\+\-spezifisch**  
  
## Siehe auch  
 [\#import\-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import\-Direktive](../preprocessor/hash-import-directive-cpp.md)