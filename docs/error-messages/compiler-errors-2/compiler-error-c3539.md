---
title: "Compilerfehler C3539 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3539"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3539"
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3539
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Typ": ein Vorlagenargument kann kein Typ sein, der "Auto" enthält  
  
 Der angegebene Vorlagenargumenttyp kann keine Verwendung des `auto`\-Schlüsselworts enthalten.  
  
### So beheben Sie diesen Fehler  
  
1.  Geben Sie das Vorlagenargument nicht mit dem `auto`\-Schlüsselwort an.  
  
## Beispiel  
 Das folgende Beispiel ergibt C3539.  
  
```  
// C3539.cpp  
// Compile with /Zc:auto  
template<class T> class C{};  
int main()  
{  
   C<auto> c;   // C3539  
   return 0;  
}  
```  
  
## Siehe auch  
 [Auto\-Schlüsselwort](../../cpp/auto-keyword.md)