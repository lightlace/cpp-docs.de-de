---
title: "Compilerfehler C2348"
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
  - "C2348"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2348"
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2348
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typname': Ist kein Aggregat im C\-Format und kann nicht in eingebetteter IDL exportiert werden  
  
 Damit der Typ `struct` in einer IDL\-Datei abgelegt werden kann, die über das [export](../../windows/export.md)\-Attribut verfügt, darf `struct` nur Daten enthalten.  
  
 Im folgenden Beispiel wird C2348 generiert:  
  
```  
// C2348.cpp  
// C2348 error expected  
[ module(name="SimpleMidlTest") ];  
  
[export]  
struct Point {  
   // Delete the following two lines to resolve.  
   Point() : m_i(0), m_j(0) {}  
   Point(int i, int j) : m_i(i), m_j(j) {}  
  
   int m_i;  
   int m_j;  
};  
```