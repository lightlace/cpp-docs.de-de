---
title: "Compilerfehler C2156 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2156"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2156"
ms.assetid: 136f9c67-2c27-4f61-b7e6-ccd202eca697
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2156
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pragma muss außerhalb der Funktion liegen  
  
 Ein Pragma, das auf globaler Ebene \(außerhalb eines Funktionsrumpfs\) angegeben werden muss, befindet sich innerhalb einer Funktion.  
  
 Im folgenden Beispiel wird C2156 generiert:  
  
```  
// C2156.cpp #pragma optimize( "l", on )   // OK int main() { #pragma optimize( "l", on )   // C2156 }  
```