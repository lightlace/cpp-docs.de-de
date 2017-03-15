---
title: "Compilerfehler C2736 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2736"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2736"
ms.assetid: 95a6bc28-c0cb-49dc-87e6-e993dbbba881
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2736
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schlüsselwort 'Schlüsselwort' ist in Typumwandlung nicht erlaubt  
  
 Das Schlüsselwort ist in einer Typumwandlung ungültig.  
  
 Im folgenden Beispiel wird C2736 generiert:  
  
```  
// C2736.cpp  
int main() {  
   return (virtual) 0;   // C2736  
   // try the following line instead  
   // return 0;  
}  
```