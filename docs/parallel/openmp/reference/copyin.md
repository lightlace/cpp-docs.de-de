---
title: "copyin | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "copyin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "copyin OpenMP clause"
ms.assetid: 369efa88-613c-4cb1-9e11-7b9ee08a4b25
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# copyin
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht Threads, um den Wert des Masterthreads, für eine [threadprivate](../../../parallel/openmp/reference/threadprivate.md)\-Variable zuzugreifen.  
  
## Syntax  
  
```  
copyin(var)  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `var`  
 Die `threadprivate`\-Variable, die dem Wert der Variablen im Masterthread initialisiert wird, wie er vor dem parallelen Konstrukt vorhanden ist.  
  
## Hinweise  
 `copyin` gilt für die folgenden Direktiven an:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Weitere Informationen finden Sie unter [2.7.2.7 copyin](../../../parallel/openmp/2-7-2-7-copyin.md).  
  
## Beispiel  
 Weitere Informationen finden Sie unter [threadprivate](../../../parallel/openmp/reference/threadprivate.md) als ein Beispiel für die Verwendung von `copyin`.  
  
## Siehe auch  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)