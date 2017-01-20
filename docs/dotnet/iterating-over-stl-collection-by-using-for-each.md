---
title: "Eine STL-Auflistung mit der for-each-Klausel durchlaufen"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DTL-Auflistungen, Iteration über"
ms.assetid: 9358ca29-b982-4a19-bbfd-bef50fe66c9a
caps.latest.revision: 14
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Eine STL-Auflistung mit der for-each-Klausel durchlaufen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das `for each`\-Schlüsselwort kann verwendet werden, um zu einer Collection der C\+\+\-Standardbibliothek \(STL\) durchlaufen.  
  
## Alle Plattformen  
 **Hinweise**  
  
 Eine STL\-Auflistung wird auch als *Container*.  Weitere Informationen finden Sie unter [STL Containers](../standard-library/stl-containers.md).  
  
## Beispiele  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird `for each` verwendet, um zur [\< Zuordnung \>](../standard-library/map.md) zu durchlaufen.  
  
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
  
  **Monaten mit 30 verbleibenden Tagen \= 4** **Beispiel**  
  
 Im folgenden Codebeispiel wird einen \- \(`const&`\) für eine Iterationsvariable mit STL\-Containern.  Sie können einen Verweis \(`&`\) als Iterationsvariable auf jede Auflistung eines Typs verwenden, der als *T*`&` deklariert werden kann.  
  
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
  
  **retval: 60**   
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Hinweise**  
  
 Es gibt keine Hinweise plattformspezifischen über diese Funktion.  
  
### Voraussetzungen  
 Compileroption: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Hinweise**  
  
 Es gibt keine Hinweise plattformspezifischen über diese Funktion.  
  
### Voraussetzungen  
 Compileroption: **\/clr**  
  
## Siehe auch  
 [for each, in](../dotnet/for-each-in.md)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)