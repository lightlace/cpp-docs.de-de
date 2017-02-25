---
title: "invalid_argument-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.invalid_argument"
  - "stdexcept/std::invalid_argument"
  - "invalid_argument"
  - "std::invalid_argument"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_argument-Klasse"
ms.assetid: af6c227d-ad7c-4e63-9dee-67af81d83506
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# invalid_argument-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Klasse fungiert als Basisklasse für alle Ausnahmen, die ausgelöst werden, um ein ungültiges Argument zu melden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class invalid_argument : public logic_error {  
public:  
    explicit invalid_argument(const string& message);

    explicit invalid_argument(const char *message);

};  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Rückgabewert von [Was](../standard-library/exception-class1.md) ist eine Kopie des **Nachricht**`.`[Daten](../standard-library/basic-string-class.md#basic_string__data).  
  
## <a name="example"></a>Beispiel  
  
```  
// invalid_arg.cpp  
// compile with: /EHsc /GR  
#include <bitset>  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   try   
   {  
      bitset< 32 > bitset( string( "11001010101100001b100101010110000") );  
   }  
   catch ( exception &e )   
   {  
      cerr << "Caught " << e.what( ) << endl;  
      cerr << "Type " << typeid( e ).name( ) << endl;  
   };  
}  
\* Output:   
Caught invalid bitset<N> char  
Type class std::invalid_argument  
*\  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \< Stdexcept>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Logic_error-Klasse](../standard-library/logic-error-class.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

