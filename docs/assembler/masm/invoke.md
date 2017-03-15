---
title: "INVOKE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Invoke"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "INVOKE directive"
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
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