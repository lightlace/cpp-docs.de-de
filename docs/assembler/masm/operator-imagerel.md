---
title: "operator IMAGEREL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
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
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
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