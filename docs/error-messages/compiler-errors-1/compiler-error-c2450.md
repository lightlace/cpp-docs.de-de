---
title: "Compilerfehler C2450 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2450"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2450"
ms.assetid: 929f1c06-8774-468b-be2a-f428757875a2
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2450
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

switch\-Ausdruck des Typs 'Typ' nicht erlaubt  
  
 Der `switch`\-Ausdruck ergibt einen ungültigen Typ.  Er muss einen Ganzzahltyp oder einen Klassentyp ergeben, der eine nicht mehrdeutige Konvertierung in einen Ganzzahltyp zulässt.  Wenn der Ausdruck einen benutzerdefinierten Typ ergibt, müssen Sie einen Konvertierungsoperator angeben.  
  
 Im folgenden Beispiel wird C2450 generiert:  
  
```  
// C2450.cpp  
class X {  
public:  
   int i;  
} x;  
  
class Y {  
public:  
   int i;  
   operator int() { return i; }   // conversion operator  
} y;  
  
int main() {  
   int j = 1;  
   switch ( x ) {   // C2450, x is not type int  
   // try the following line instead  
   // switch ( y ) {  
      default:  ;  
   }  
}  
```