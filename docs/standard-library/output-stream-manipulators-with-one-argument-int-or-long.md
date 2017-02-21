---
title: "Ausgabestreammanipulatoren mit einem Argument (int oder long) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ausgabestreams, Manipulatoren mit int- oder long-Argument"
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ausgabestreammanipulatoren mit einem Argument (int oder long)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die der iostream\-Headerdatei Klassenbibliothek stellt eine Reihe von Makros für das Erstellen von parametrisierten Manipulatoren bereit.  Manipulatoren mit einzelnen `int` oder einem `long`\-Argument sind ein Sonderfall.  Um einen Ausgabestreammanipulator Erstellen der einzelnen `int` akzeptiert oder Argument `long` \(wie `setw`\), müssen Sie das \_Smanip Makro verwenden, das im iomanip definiert \<wird\>.  In diesem Beispiel definiert einen `fillblank` an, der eine bestimmte Anzahl Leerzeichen in den Stream einfügt:  
  
## Beispiel  
  
```  
// output_stream_manip.cpp  
// compile with: /GR /EHsc  
#include <iostream>  
#include <iomanip>  
using namespace std;  
  
void fb( ios_base& os, int l )  
{  
   ostream *pos = dynamic_cast<ostream*>(&os);  
   if (pos)  
   {  
      for( int i=0; i < l; i++ )  
      (*pos) << ' ';  
   };  
}  
  
_Smanip<int>  
   __cdecl fillblank(int no)  
   {     
   return (_Smanip<int>(&fb, no));  
   }  
  
int main( )  
{  
   cout << "10 blanks follow" << fillblank( 10 ) << ".\n";  
}  
```  
  
## Siehe auch  
 [Benutzerdefinierte Manipulatoren mit Argumenten](../standard-library/custom-manipulators-with-arguments.md)