---
title: "Compilerwarnung (Stufe 1) C4003 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4003"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4003"
ms.assetid: 0ed1c285-4428-4c90-8131-86897e31f115
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4003
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht genügend übergebene Parameter für das Makro 'Bezeichner'  
  
 Die Anzahl der formalen Parameter in der Makrodefinition überschreitet die Anzahl der tatsächlich im Makro enthaltenen Parameter.  Bei der Makroerweiterung werden fehlende Parameter durch leere Textzeilen ersetzt.  
  
 Im folgenden Beispiel wird C4003 generiert:  
  
```  
// C4003.cpp  
// compile with: /WX  
#define test(a,b) (a+b)  
  
int main()  
{  
   int a = 1;  
   int b = 2;  
   a = test(b);   // C4003  
   // try..  
   a = test(a,b);  
}  
```