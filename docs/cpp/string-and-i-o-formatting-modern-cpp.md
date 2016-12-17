---
title: "Formatieren von Zeichenfolgen und Ein-/Ausgaben (Modern C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Formatieren von Zeichenfolgen und Ein-/Ausgaben (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+\-[iostreams](../standard-library/iostream.md) sind zu formatierter Zeichenfolgenein\- und \-ausgabe fähig.  Im folgenden Code wird das Festlegen von "cout" zum Formatieren einer ganzen Zahl für eine Hexadezimalausgabe dargestellt. Erst wird der aktuelle Zustand gespeichert, danach erfolgt das Zurücksetzen, da die Methode nach Übergabe der Zustandsformatierung an "cout" in dem Zustand verbleibt, bis sie geändert wird und nicht nur für eine Codezeile.  
  
```fortran  
#include <iostream>  
#include <iomanip>  
  
using namespace std;  
  
int main()   
{  
    ios state(nullptr);  
  
    cout << "The answer in decimal is: " << 42 << endl;  
  
    state.copyfmt(cout); // save current formatting  
    cout << "In hex: 0x" // now load up a bunch of formatting modifiers  
        << hex   
        << uppercase   
        << setw(8)   
        << setfill('0')   
        << 42            // the actual value we wanted to print out  
        << endl;  
    cout.copyfmt(state); // restore previous formatting  
}  
  
```  
  
 Dies kann vielen Fällen außerordentlich lästig sein.  Alternativ können Sie "Boost.Format" aus den C\+\+\-Bibliotheken von Boost verwenden, obwohl das nicht dem Standard entspricht.  Sie können jede Auftriebsbibliothek von der Website [Boost](http://www.boost.org/) herunterladen.  
  
 Einige Vorteile von "Boost.Format" sind:  
  
-   Sicher: Typsicher und löst eine Ausnahme bei Fehlern aus, z. B. bei der Angabe von zu wenigen oder zu vielen Elementen  
  
-   Erweiterbar: Funktioniert für jeden Typ, der gestreamt werden kann  
  
-   Bequem: Standard\-Posix und ähnliche Formatzeichenfolgen  
  
 Obwohl "Boost.Format" auf C\+\+\-[iostreams](../standard-library/iostream-programming.md) erstellt wird, die zwar sicher und erweiterbar sind, werden sie aber nicht leistungsoptimiert.  Sofern Sie Leistungsoptimierung erfordern, sollten Sie C [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) und [sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) berücksichtigen, deren Verwendung schnell und einfach ist.  Allerdings sind sie nicht erweiterbar und können Sicherheitsrisiken bergen. \(Sichere Versionen sind vorhanden, doch verursachen diese geringfügige Leistungseinbußen.  Weitere Informationen finden Sie unter [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) und [sprintf\_s, \_sprintf\_s\_l, swprintf\_s, \_swprintf\_s\_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)\).  
  
 Im folgenden Code werden einige der Boost\-Formatierungsfunktionen verdeutlicht.  
  
```cpp  
    string s = str( format("%2% %2% %1%\n") % "world" % "hello" );  
    // s contains "hello hello world"    
  
    for( auto i = 0; i < names.size(); ++i )  
        cout << format("%1% %2% %|40t|%3%\n") % first[i] % last[i] % tel[i];  
    // Georges Benjamin Clemenceau             +33 (0) 123 456 789  
    // Jean de Lattre de Tassigny              +33 (0) 987 654 321  
  
```  
  
## Siehe auch  
 [Willkommen zurück bei C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [C\+\+\-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)   
 [\<iostream\>](../standard-library/iostream.md)   
 [\<limits\>](../standard-library/limits.md)   
 [\< Iomanip \>](../standard-library/iomanip.md)