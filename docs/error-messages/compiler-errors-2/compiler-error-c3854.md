---
title: "Compilerfehler C3854"
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
  - "C3854"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3854"
ms.assetid: 32a9ead0-c6c7-485a-8802-c7b1fe921d3a
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3854
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Auswertung des Ausdruck links von '\=' ergibt eine Funktion.Zuweisung zu einer Funktion nicht möglich \(eine Funktion ist kein l\-Wert\)  
  
 Ein Verweis kann nicht erneut initialisiert werden.  Das Dereferenzieren eines Funktionsverweises ergibt eine Funktion, die einem R\-Wert entspricht, der keine Zuweisungen unterstützt.  Daher werden keine Zuweisungen unterstützt, die über einen Verweis auf eine Funktion vorgenommen werden.  
  
 Im folgenden Beispiel wird C3854 generiert:  
  
```  
// C3854.cpp  
int afunc(int i)  
{  
   return i;  
}  
  
typedef int (& rFunc_t)(int);  
typedef int (* pFunc_t)(int);  
  
int main()  
{  
   rFunc_t rf = afunc;   // OK binding a reference to function  
   pFunc_t pf = &afunc;   // OK initializing a pointer to function  
  
   *pf = &afunc;   // C3854  
   // try the following line instead  
   // pf = &afunc;  
   *rf = &afunc;   // C3854  
}  
```