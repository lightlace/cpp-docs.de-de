---
title: "4.4 OMP_NESTED"
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
ms.assetid: fd17b6f4-84e8-44c0-a96a-3a9e5ba33688
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# 4.4 OMP_NESTED
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `OMP_NESTED` Umgebungsvariablen aktiviert oder deaktiviert geschachtelten Parallelität, es sei denn, geschachtelter Parallelität aktiviert oder deaktiviert werden, indem Sie die routine Bibliothek `o`**mp\_set\_nested** aufruft.  Wenn auf true festgelegt ist, geschachtelter Parallelität aktiviert. falls er zu **FALSE**festgelegt ist, wird geschachtelter Parallelität deaktiviert.  Der Standardwert ist **FALSE**.  
  
 Beispiel:  
  
```  
setenv OMP_NESTED TRUE  
```  
  
## Querverweis:  
  
-   `omp_set_nested`\-Funktion finden [3.1.9 Abschnitt](../../parallel/openmp/3-1-9-omp-set-nested-function.md) auf Seite 40.