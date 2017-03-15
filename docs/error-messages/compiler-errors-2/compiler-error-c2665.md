---
title: "Compilerfehler C2665 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2665"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2665"
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C2665
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Keine der Nummer1\-Überladungen kann Parameter Nummer2 von Typ 'Typ' konvertieren  
  
 Ein Parameter der überladenen Funktion kann nicht in den erforderlichen Typ konvertiert werden.  Mögliche Lösungen:  
  
-   Geben Sie einen Konvertierungsoperator an.  
  
-   Verwenden Sie eine explizite Konvertierung.  
  
## Beispiel  
 Im folgenden Beispiel wird C2665 generiert.  
  
```  
// C2665.cpp  
void func(short, char*){}  
void func(char*, char*){}  
  
int main() {  
   func(0, 1);   // C2665  
   func((short)0, (char*)1);   // OK  
}  
```