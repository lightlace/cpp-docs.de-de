---
title: "Compilerfehler C3738"
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
  - "C3738"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3738"
ms.assetid: dd3ee011-e204-4264-bf3a-da32c4ef7038
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3738
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Aufrufkonvention': Die Aufrufkonvention der expliziten Instanziierung muss mit der der instanziierten Vorlage übereinstimmen  
  
 Es wird empfohlen, dass Sie für eine explizite Instanziierung keine Aufrufkonvention angeben.  Wenn dies jedoch nötig ist, müssen die Aufrufkonventionen übereinstimmen.  
  
## Beispiel  
 Im folgenden Beispiel wird C3738 generiert.  
  
```  
// C3738.cpp  
// compile with: /clr  
// processor: x86  
#include <stdio.h>  
template< class T >  
void f ( T arg ) {   // by default calling convention is __cdecl  
   printf ( "f: %s\n", __FUNCSIG__ );  
}  
  
template   
void __stdcall f< int > ( int arg );   // C3738  
// try the following line instead  
// void f< int > ( int arg );  
  
int main () {  
   f(1);  
   f< int > ( 1 );  
}  
```