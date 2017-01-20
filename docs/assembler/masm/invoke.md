---
title: "INVOKE"
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
  - "Invoke"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "INVOKE directive"
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# INVOKE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nennt die Prozedur an der Adresse angegeben durch *den Ausdruck*, wobei die Argumente auf dem Stapel oder in Registern gemäß den Standardwert aufrufkonventionen Sprachen des Typs.  
  
## Syntax  
  
```  
  
INVOKE   
expression [[, arguments]]  
```  
  
## Hinweise  
 Jedes Argument, das an die Prozedur übergeben wird, ist ein Ausdruck, ein Register Adressausdruck oder ein paar vorangestellt ein Ausdruck \(von `ADDR`\).  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)