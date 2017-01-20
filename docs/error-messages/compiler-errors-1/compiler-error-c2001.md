---
title: "Compilerfehler C2001"
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
  - "C2001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2001"
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zeilenvorschub in Konstante  
  
 Eine Zeichenfolge kann nur in einer zweiten Zeile fortgeführt werden, wenn Sie eine der folgenden Aktionen ausführen:  
  
-   Sie beenden die erste Zeile mit einem umgekehrten Schrägstrich.  
  
-   Sie schließen die Zeichenfolge in der ersten Zeile mit einem doppelten Anführungszeichen ab und beginnen die Zeichenfolge in der nächsten Zeile mit einem weiteren doppelten Anführungszeichen.  
  
 Es reicht nicht aus, die erste Zeile mit \\n zu beenden.  
  
## Beispiel  
 Im folgenden Beispiel wird C2001 generiert:  
  
```  
// C2001.cpp  
// C2001 expected  
#include <stdio.h>  
  
int main()  
{  
    printf_s("Hello,  
             world");  
    printf_s("Hello,\n  
             world");  
}  
```  
  
## Beispiel  
 Leerzeichen hinter einem Zeilenfortsetzungszeichen am Anfang der nächsten Zeile werden in die Zeichenfolgenkonstante eingeschlossen.  Durch keines der oben aufgeführten Beispiele wird eine Zeilenendemarke in die Zeichenfolgenkonstante eingebettet.  Zeilenendemarken können, wie nachfolgend dargestellt, eingebettet werden:  
  
```  
// C2001b.cpp  
#include <stdio.h>  
  
int main()  
{  
    printf_s("Hello,\n\  
             world");  
  
    printf_s("Hello,\  
             \nworld");  
  
    printf_s("Hello,\n"  
             "world");  
  
    printf_s("Hello,"  
             "\nworld");  
  
    printf_s("Hello,"  
             " world");  
  
    printf_s("Hello,\  
             world");  
}  
```