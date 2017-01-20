---
title: "Schwerwiegender Fehler C1104"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C1104"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1104"
ms.assetid: 45bd85c4-77d3-4d3c-b167-49c563aefb4d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1104
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schwerwiegender Fehler beim Importieren der LibID: "Meldung"  
  
 Der Compiler hat beim Importieren einer Typbibliothek ein Problem erkannt.  Sie können beispielsweise keine Typbibliothek mit LibID und gleichzeitig `no_registry` angeben.  
  
 Weitere Informationen finden Sie unter [\#import\-Direktive](../../preprocessor/hash-import-directive-cpp.md).  
  
 Im folgenden Beispiel wird C1104 generiert.  
  
```  
// C1104.cpp #import "libid:11111111.1111.1111.1111.111111111111" version("4.0") lcid("9") no_registry auto_search   // C1104  
```