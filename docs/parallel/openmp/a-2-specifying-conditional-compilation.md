---
title: "A.2   Specifying Conditional Compilation"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: de4a21b9-f987-4738-9f13-c4795f6f2dff
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# A.2   Specifying Conditional Compilation
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die folgenden Beispiele veranschaulichen die Verwendung bedingter Kompilierung mit OpenMPs Makro\- `_OPENMP` \([Abschnitt 2.2](../../parallel/openmp/2-2-conditional-compilation.md) auf Seite 8\).  Mit OpenMP\-Kompilierung wird das `_OPENMP` Makro definiert.  
  
```  
# ifdef _OPENMP   
    printf_s("Compiled by an OpenMP-compliant implementation.\n");  
# endif  
```  
  
 Der definierte Präprozessor operator können mehrere in einzelnen Direktiven Makro getestet werden soll.  
  
```  
# if defined(_OPENMP) && defined(VERBOSE)  
    printf_s("Compiled by an OpenMP-compliant implementation.\n");  
# endif  
```