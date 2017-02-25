---
title: "Compilerfehler C2499 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2499"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2499"
ms.assetid: b323ff4d-b3c1-4bfd-b052-ae7292d53222
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2499
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': Eine Klasse kann nicht ihre eigene Basisklasse sein  
  
 Es wurde versucht, die Klasse anzugeben, die als Basisklasse definiert wird.  
  
 Im folgenden Beispiel wird C2499 generiert:  
  
```  
// C2499.cpp  
// compile with: /c  
class CMyClass : public CMyClass {};   // C2499  
class CMyClass{};   // OK  
```