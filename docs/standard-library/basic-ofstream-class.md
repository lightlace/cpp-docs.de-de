---
title: "basic_ofstream-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::basic_ofstream"
  - "basic_ofstream"
  - "std.basic_ofstream"
  - "fstream/std::basic_ofstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_ofstream-Klasse"
ms.assetid: 3bcc9c51-6dfc-4844-8fcc-22ef57c9dff1
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# basic_ofstream-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein Objekt, das das Einfügen von Elementen und codierten Objekten in einen Streampuffer der Klasse [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\> mit Elementen des Typs `Elem` steuert, dessen Zeichenmerkmale von der Klasse `Tr` bestimmt werden.  
  
## Syntax  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_ofstream : public basic_ostream<Elem, Tr>  
```  
  
#### Parameter  
 `Elem`  
 Das grundlegende Element des Dateipuffers.  
  
 `Tr`  
 Die Merkmale des grundlegenden Elements des Dateipuffers \(in der Regel `char_traits`\<`Elem`\>\).  
  
## Hinweise  
 Wenn die `wchar_t`\-Spezialisierung von `basic_ofstream` in die Datei schreibt und wenn die Datei im Textmodus geöffnet ist, wird eine MBCS\-Sequenz geschrieben.  Die interne Darstellung verwendet einen Puffer mit `wchar_t`\-Zeichen.  
  
 Das Objekt speichert ein Objekt der Klasse `basic_filebuf`\<`Elem`, `Tr`\>.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein `basic_ofstream`\-Objekt erstellt und Text in dieses Objekt geschrieben wird.  
  
```  
// basic_ofstream_class.cpp  
// compile with: /EHsc  
#include <fstream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    ofstream ofs("ofstream.txt");  
    if (!ofs.bad())  
    {  
        ofs << "Writing to a basic_ofstream object..." << endl;  
        ofs.close();  
    }  
}  
```  
  
### Konstruktoren  
  
|||  
|-|-|  
|[basic\_ofstream](../Topic/basic_ofstream::basic_ofstream.md)|Erstellt ein Objekt des Typs `basic_ofstream`.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[schließen](../Topic/basic_ofstream::close.md)|Schließt eine Datei.|  
|[is\_open](../Topic/basic_ofstream::is_open.md)|Ermittelt, ob eine Datei geöffnet ist.|  
|[open](../Topic/basic_ofstream::open.md)|Öffnet eine Datei.|  
|[rdbuf](../Topic/basic_ofstream::rdbuf.md)|Gibt die Adresse des gespeicherten Streampuffers zurück.|  
|[swap](../Topic/basic_ofstream::swap.md)|Tauscht den Inhalt dieses `basic_ofstream`\-Objekts gegen den Inhalt des bereitgestellten `basic_ofstream`\-Objekts aus.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator \=](../Topic/basic_ofstream::operator=.md)|Weist den Inhalt dieses Streamobjekts zu.  Dies ist eine Verschiebezuweisung mit einem `rvalue reference`, die keine Kopie hinterlässt.|  
  
## Anforderungen  
 **Header:** \<fstream\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [basic\_ostream\-Klasse](../standard-library/basic-ostream-class.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)