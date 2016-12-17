---
title: "basic_ifstream-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "basic_ifstream"
  - "fstream/std::basic_ifstream"
  - "std::basic_ifstream"
  - "std.basic_ifstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_ifstream-Klasse"
ms.assetid: 366cd9a7-efc4-4b7f-ba10-c8271e47ffcf
caps.latest.revision: 23
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# basic_ifstream-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein Objekt, das das Extrahieren von Elementen und codierten Objekten aus einem Streampuffer der Klasse [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\> mit Elementen des Typs `Elem` steuert, dessen Zeichenmerkmale von der Klasse `Tr` bestimmt werden.  
  
## Syntax  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_ifstream : public basic_istream<Elem, Tr>  
```  
  
#### Parameter  
 `Elem`  
 Das grundlegende Element des Dateipuffers.  
  
 `Tr`  
 Die Merkmale des grundlegenden Elements des Dateipuffers \(in der Regel `char_traits`\<`Elem`\>\).  
  
## Hinweise  
 Das Objekt speichert ein Objekt der Klasse `basic_filebuf`\<`Elem`, `Tr`\>.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Text aus einer Datei gelesen wird.  
  
```  
// basic_ifstream_class.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    ifstream ifs("basic_ifstream_class.txt");  
    if (!ifs.bad())  
    {  
        // Dump the contents of the file to cout.  
        cout << ifs.rdbuf();  
        ifs.close();  
    }  
}  
```  
  
## Eingabe: basic\_ifstream\_class.txt  
  
```  
This is the contents of basic_ifstream_class.txt.  
```  
  
## Ausgabe  
  
```  
This is the contents of basic_ifstream_class.txt.  
```  
  
### Konstruktoren  
  
|||  
|-|-|  
|[basic\_ifstream](../Topic/basic_ifstream::basic_ifstream.md)|Initialisiert eine neue Instanz eines `basic_ifstream`\-Objekts.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[schließen](../Topic/basic_ifstream::close.md)|Schließt eine Datei.|  
|[is\_open](../Topic/basic_ifstream::is_open.md)|Ermittelt, ob eine Datei geöffnet ist.|  
|[open](../Topic/basic_ifstream::open.md)|Öffnet eine Datei.|  
|[rdbuf](../Topic/basic_ifstream::rdbuf.md)|Gibt die Adresse des gespeicherten Streampuffers zurück.|  
|[swap](../Topic/basic_ifstream::swap.md)|Tauscht den Inhalt dieses `basic_ifstream`\-Objekts mit dem Inhalt des bereitgestellten `basic_ifstream`\-Objekts aus.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator \=](../Topic/basic_ifstream::operator=.md)|Weist den Inhalt dieses Streamobjekts zu.  Dies ist eine Verschiebezuweisung über einen `rvalue`, die keine Kopie hinterlässt.|  
  
## Anforderungen  
 **Header:** \<fstream\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)