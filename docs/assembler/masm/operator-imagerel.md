---
title: "operator IMAGEREL"
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
  - "operator IMAGEREL"
  - "IMAGEREL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator IMAGEREL"
  - "IMAGEREL operator"
ms.assetid: 5b5ea425-36f0-467c-9262-62c484b7fdb4
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# operator IMAGEREL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt den Offset von Bild im Hinblick `expression`zurück.  
  
## Syntax  
  
```  
IMAGEREL expression  
```  
  
## Hinweise  
 Der resultierende Wert wird häufig als eine RVA oder eine relative virtuelle Adresse.  
  
 IMAGEREL ist nur mit COFF\-Objektemission verfügbar.  
  
## Siehe auch  
 [Operators Reference](../../assembler/masm/operators-reference.md)