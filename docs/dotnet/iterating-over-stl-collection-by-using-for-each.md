---
title: "Durchlaufen von C++-Standard-Bibliothekssammlung für jede mit | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords: DTL collections, iterating over
ms.assetid: 9358ca29-b982-4a19-bbfd-bef50fe66c9a
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1a4ce2de13380895f1f313559abeb87e4cd65db2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="iterating-over-c-standard-library-collection-by-using-for-each"></a>C++-Standard-Bibliothekssammlung durchlaufen für jede mit
Die `for each` -Schlüsselwort kann verwendet werden, um eine C++-Standardbibliothek Auflistung zu durchlaufen.  
  
## <a name="all-platforms"></a>Alle Plattformen  
 **Hinweise**  
  
 Eine Auflistung von C++-Standardbibliothek ist auch bekannt als ein *Container*. Weitere Informationen finden Sie unter [C++-Standardbibliothekcontainer](../standard-library/stl-containers.md).  
  
## <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird mit `for each` zum Durchlaufen einer [ \<Zuordnung >](../standard-library/map.md).  
  
```  
// for_each_stl.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
#include <string>  
using namespace std;  
  
int main() {  
   int retval  = 0;  
   map<string, int> months;  
  
   months["january"] = 31;  
   months["february"] = 28;  
   months["march"] = 31;  
   months["april"] = 30;  
   months["may"] = 31;  
   months["june"] = 30;  
   months["july"] = 31;  
   months["august"] = 31;  
   months["september"] = 30;  
   months["october"] = 31;  
   months["november"] = 30;  
   months["december"] = 31;  
  
   map<string, int> months_30;  
  
   for each( pair<string, int> c in months )  
      if ( c.second == 30 )  
         months_30[c.first] = c.second;  
  
   for each( pair<string, int> c in months_30 )  
      retval++;  
  
   cout << "Months with 30 days = " << retval << endl;  
}  
```  
  
 **Ausgabe**  
  
```Output  
Months with 30 days = 4  
```  
  
 **Beispiel**  
  
 Das folgende Codebeispiel verwendet ein const-verweist (`const&`) für eine Iterationsvariable mit C++-Standardbibliothek-Containern. Sie können einen Verweis (`&`) als eine Iterationsvariable auf einer beliebigen Datensammlung ein Typ, der als deklariert werden, kann eine *T*`&`.  
  
```  
// for_each_stl_2.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
using namespace std;  
  
int main() {  
   int retval = 0;  
  
   vector<int> col(3);  
   col[0] = 10;  
   col[1] = 20;  
   col[2] = 30;  
  
   for each( const int& c in col )  
      retval += c;  
  
   cout << "retval: " << retval << endl;  
}  
```  
  
 **Ausgabe**  
  
```Output  
retval: 60  
```  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 **Hinweise**  
  
 Es gibt keine plattformspezifischen Hinweise zu dieser Funktion.  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
 **Hinweise**  
  
 Es gibt keine plattformspezifischen Hinweise zu dieser Funktion.  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
## <a name="see-also"></a>Siehe auch  
 [für jedes in](../dotnet/for-each-in.md)   
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)