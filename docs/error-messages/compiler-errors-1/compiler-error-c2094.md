---
title: "Compilerfehler C2094"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C2094"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2094"
ms.assetid: 9e4f8f88-f189-46e7-91c9-481bacc7af87
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2094
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bezeichnung "identifier" nicht definiert  
  
 Die von einer [goto](../Topic/goto%20\(C%23%20Reference\).md)\-Anweisung verwendete Bezeichnung ist in der Funktion nicht vorhanden.  
  
 Im folgenden Beispiel wird C2094 generiert:  
  
```  
// C2094.c int main() { goto test; }   // C2094  
```  
  
 Mögliche Lösung:  
  
```  
// C2094b.c int main() { goto test; test: { } }  
```