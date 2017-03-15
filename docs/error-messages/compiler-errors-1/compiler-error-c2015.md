---
title: "Compilerfehler C2015 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2015"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2015"
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C2015
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zu viele Zeichen in der Konstante  
  
 Eine Zeichenkonstante enthält mehr als zwei Zeichen.  Das Maximum entspricht einem Zeichen für Standardzeichenkonstanten und zwei Zeichen für lange Zeichenkonstanten.  
  
 Eine Escape\-Sequenz, z. B. \\t, wird in ein einzelnes Zeichen umgewandelt.  
  
## Beispiel  
 Im folgenden Beispiel wird C2015 generiert:  
  
```  
// C2015.cpp  
// compile with: /c  
  
char test1 = 'error';   // C2015  
char test2 = 'e';   // OK  
```  
  
## Beispiel  
 C2015 kann auch bei der Verwendung von Microsoft\-Erweiterungen zum Konvertieren von Zeichenkonstanten in ganzen Zahlen auftreten.  Im folgenden Beispiel wird C2015 generiert:  
  
```  
// C2015b.cpp  
#include <stdio.h>  
  
int main()   
{  
    int a = 'abcde';   // C2015  
  
    int b = 'a';   // 'a' = ascii 0x61  
    printf_s("%x\n", b);  
}  
```