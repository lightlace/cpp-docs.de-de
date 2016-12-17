---
title: "Ausdrucksauswertungsfehler CXX0064"
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
  - "CXX0064"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0064"
  - "CXX0064"
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Ausdrucksauswertungsfehler CXX0064
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Setzen von Haltepunkten auf gebundene virtuelle Memberfunktionen nicht möglich  
  
 Durch einen Zeiger auf ein Objekt wurde ein Haltepunkt auf eine virtuelle Memberfunktion festgelegt, z. B.:  
  
```  
pClass->vfunc( int );  
```  
  
 Ein Haltepunkt kann auf eine virtuelle Funktion festgelegt werden, indem die Klasse eingegeben wird, z. B.:  
  
```  
Class::vfunc( int );  
```  
  
 Dieser Fehler ist mit CAN0064 identisch.