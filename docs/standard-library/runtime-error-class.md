---
title: "runtime_error-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.runtime_error"
  - "runtime_error"
  - "stdexcept/std::runtime_error"
  - "std::runtime_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "runtime_error-Klasse"
ms.assetid: 4d0227bf-847b-45a2-a320-2351ebf98368
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# runtime_error-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Klasse fungiert als Basisklasse für alle Ausnahmen, die ausgelöst werden, um Fehler zu melden, die mutmaßlich nur erkennbar sind, wenn das Programm ausgeführt wird.  
  
## Syntax  
  
```  
class runtime_error : public exception {  
public:  
    explicit runtime_error(const string& message);  
    explicit runtime_error(const char *message);  
};  
```  
  
## Hinweise  
 Der Rückgabewert [exception\-Klasse](../standard-library/exception-class1.md) ist eine Kopie des **Nachricht**`.`[Daten](../Topic/basic_string::data.md).  
  
## Beispiel  
  
```  
// runtime_error.cpp  
// compile with: /EHsc /GR  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
// runtime_error  
   try   
   {  
      locale loc( "test" );  
   }  
   catch ( exception &e )   
   {  
      cerr << "Caught " << e.what( ) << endl;  
      cerr << "Type " << typeid( e ).name( ) << endl;  
   };  
}  
```  
  
 **Ungültiges Gebietsschema Name Typ Klasse std::runtime\_error abgefangen**   
## Anforderungen  
 **Header:** \< Stdexcept \>  
  
 **Namespace:** std  
  
## Siehe auch  
 [exception\-Klasse](../standard-library/exception-class1.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)