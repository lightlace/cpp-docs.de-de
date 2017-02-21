---
title: "Compilerwarnung (Stufe 2) C4308 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4308"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4308"
ms.assetid: d4e5c53c-71b2-4bbc-8a7c-3a2a3180d9d9
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 2) C4308
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Negative Ganzzahlkonstante in vorzeichenlosen Typ konvertiert  
  
 Eine negative Ganzzahlkonstante wurde durch einen Ausdruck in einen vorzeichenlosen Typ konvertiert.  Das Ergebnis des Ausdrucks ist möglicherweise ohne Bedeutung.  
  
## Beispiel  
  
```  
// C4308.cpp  
// compile with: /W2  
unsigned int u = (-5 + 3U);   // C4308  
  
int main()  
{  
}  
```