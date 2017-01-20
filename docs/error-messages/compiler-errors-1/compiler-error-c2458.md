---
title: "Compilerfehler C2458"
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
  - "C2458"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2458"
ms.assetid: ed21901f-1067-42f5-b275-19b480decf5c
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2458
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Neudefinition in einer Definition  
  
 Eine Klasse, Struktur, Union oder Enumeration wurde in ihrer eigenen Deklaration neu definiert.  
  
 Im folgenden Beispiel wird C2458 generiert:  
  
```  
// C2458.cpp  
class C {  
   enum i { C };   // C2458  
};  
```