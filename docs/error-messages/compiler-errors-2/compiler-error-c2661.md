---
title: "Compilerfehler C2661"
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
  - "C2661"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2661"
ms.assetid: 60021467-71cd-451b-9877-23840c69309f
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2661
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Keine überladene Funktion akzeptiert Anzahl Parameter  
  
 Mögliche Ursachen:  
  
1.  Falsche übergebene Parameter in Funktionsaufruf.  
  
2.  Fehlende Funktionsdeklaration.  
  
 Im folgenden Beispiel wird C2661 generiert:  
  
```  
// C2661.cpp  
void func( int ){}  
void func( int, int ){}  
int main() {  
   func( );   // C2661 func( void ) was not declared  
   func( 1 );   // OK func( int ) was declared  
}  
```