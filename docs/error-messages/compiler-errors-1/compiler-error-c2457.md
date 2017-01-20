---
title: "Compilerfehler C2457"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2457"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2457"
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2457
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Makro': Ein vordefiniertes Makro kann nicht außerhalb eines Funktionstextes stehen  
  
 Es wurde versucht, ein vordefiniertes Makro, z. B. [\_\_FUNCTION\_\_](../../preprocessor/predefined-macros.md), in einem globalen Namensbereich zu verwenden.  
  
## Beispiel  
 Im folgenden Beispiel wird C2457 generiert:  
  
```  
// C2457.cpp  
#include <stdio.h>  
  
__FUNCTION__;   // C2457, cannot be global  
  
int main()   
{  
    printf_s("\n%s",__FUNCTION__);   // OK  
}  
```