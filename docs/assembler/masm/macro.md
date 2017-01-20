---
title: "MACRO"
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
  - "MACRO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MACRO directive"
ms.assetid: 89434f7c-bc2c-4e91-8940-fe2db8785233
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# MACRO
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Markiert ein Makro mit Datenbindungsausdrücken dem *Namen* aufgerufen wird und richtet Parameterplatzhalter für die übergebenen Argumente ein, wenn das Makro aufgerufen wird.  
  
## Syntax  
  
```  
  
   name MACRO [[parameter [[:REQ | :=default | :VARARG]]]]...  
statements  
ENDM [[value]]  
```  
  
## Hinweise  
 Eine Makrofunktion *Wert* gibt an die aufrufende Anweisung zurückgegeben.  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)