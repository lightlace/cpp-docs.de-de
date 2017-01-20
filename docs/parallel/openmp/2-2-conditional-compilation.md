---
title: "2.2 Conditional Compilation"
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
ms.assetid: 8f9c914d-736c-48cf-899d-c8029dbe1e32
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# 2.2 Conditional Compilation
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der \_**OPENMP** Makro wird durch den Namen OpenMP\-kompatible Implementierungen als dezimale Konstante *yyyymm*definiert, das das Jahr und den Monat der erkannten Spezifikation ist.  Dieses Makro darf nicht den Betreff der **\#define** oder **\#undef** vorverarbeitend Direktive sein.  
  
```  
#ifdef _OPENMP  
iam = omp_get_thread_num() + index;  
#endif  
```  
  
 Wenn Anbieter Erweiterungen zu OpenMP definieren, geben möglicherweise zusätzliche vordefinierte Makros an.