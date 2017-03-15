---
title: "Compilerfehler C2661 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2661"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2661"
ms.assetid: 60021467-71cd-451b-9877-23840c69309f
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
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