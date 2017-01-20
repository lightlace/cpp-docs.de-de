---
title: "setvbuf-Konstanten"
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
  - "_IOFBF"
  - "_IONBF"
  - "_IOLBF"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_IOFBF-Konstante"
  - "_IOLBF-Konstante"
  - "_IONBF-Konstante"
  - "IOFBF-Konstante"
  - "IOLBF-Konstante"
  - "IONBF-Konstante"
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# setvbuf-Konstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
#include <stdio.h>  
  
```  
  
## Hinweise  
 Diese Konstanten stellen den Typ des Puffers für `setvbuf` dar.  
  
 Die möglichen Werte werden durch die folgenden Konstanten Manifest angegeben:  
  
|Konstante|Bedeutung|  
|---------------|---------------|  
|`_IOFBF`|Vollständige Pufferung: Der Puffer, der im Aufruf von `setvbuf` angegeben ist, wird und seine Größe ist, wie in `setvbuf` Aufruf angegeben.  Wenn Pufferzeiger **NULL**, wird automatisch zugeordneter Puffer des angegebenen Größe verwendet.|  
|`_IOLBF`|Dieselbe Bedeutung wie `_IOFBF`.|  
|`_IONBF`|Kein Puffer wird, unabhängig davon Argumente im Aufruf von `setvbuf` verwendet.|  
  
## Siehe auch  
 [setbuf](../c-runtime-library/reference/setbuf.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)