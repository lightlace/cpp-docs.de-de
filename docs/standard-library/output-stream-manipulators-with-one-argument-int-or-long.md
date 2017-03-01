---
title: Ausgabestreammanipulatoren mit einem Argument (int oder long) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- output streams, int or long argument manipulators
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 84cbc5d016f6796a1cab208a1d77b51ea2ac6ecb
ms.lasthandoff: 02/24/2017

---
# <a name="output-stream-manipulators-with-one-argument-int-or-long"></a>Ausgabestreammanipulatoren mit einem Argument (int oder long)
Die iostream-Klassenbibliothek enthält eine Reihe von Makros zum Erstellen von parametrisierter Manipulatoren. Manipulatoren mit einem einzigen `int`- oder `long`-Argument sind ein Sonderfall. Um einen Ausgabestreammanipulator zu erstellen, der ein einzelnes `int`- oder `long`-Argument akzeptiert (z.B. `setw`), müssen Sie das Makro _Smanip verwenden, das in \<iomanip> definiert ist. Dieses Beispiel definiert einen `fillblank`-Manipulator, der eine angegebene Anzahl von Leerzeichen in den Datenstrom eingefügt:  
  
## <a name="example"></a>Beispiel  
  
```cpp  
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
  
## <a name="see-also"></a>Siehe auch  
 [Benutzerdefinierte Manipulatoren mit Argumenten](../standard-library/custom-manipulators-with-arguments.md)


