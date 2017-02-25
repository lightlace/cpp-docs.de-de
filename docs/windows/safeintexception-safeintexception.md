---
title: "SafeIntException::SafeIntException | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeIntException"
  - "SafeIntException.SafeIntException"
  - "SafeIntException::SafeIntException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeIntException, Konstruktor"
ms.assetid: 8e5a0c24-a56b-4c80-9ee8-876604b1e7dc
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# SafeIntException::SafeIntException
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt ein `SafeIntException`\-Objekt.  
  
## Syntax  
  
```  
SafeIntException();  
  
SafeIntException(  
   SafeIntError code  
);  
```  
  
#### Parameter  
 \[in\] `code`  
 Ein Datenwert aufgelisteter, der den Fehler beschreibt, der aufgetreten ist.  
  
## Hinweise  
 Die möglichen Werte für `code` werden in der Datei Safeint.h definiert.  Zur Vereinfachung werden die möglichen Werte auch hier aufgeführt.  
  
-   `SafeIntNoError`  
  
-   `SafeIntArithmeticOverflow`  
  
-   `SafeIntDivideByZero`  
  
## Anforderungen  
 **Header:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## Siehe auch  
 [SafeInt\-Bibliothek](../windows/safeint-library.md)   
 [SafeIntException\-Klasse](../windows/safeintexception-class.md)   
 [SafeInt\-Klasse](../windows/safeint-class.md)