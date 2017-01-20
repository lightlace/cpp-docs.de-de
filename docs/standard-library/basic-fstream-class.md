---
title: "basic_fstream-Klasse"
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
  - "std::basic_fstream"
  - "basic_fstream"
  - "fstream/std::basic_fstream"
  - "std.basic_fstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_fstream-Klasse"
ms.assetid: 8473817e-42a4-430b-82b8-b476c86bcf8a
caps.latest.revision: 24
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# basic_fstream-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein Objekt, das das Einfügen und Extrahieren von Elementen und codierten Objekten über einen Streampuffer der Klasse [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\> mit Elementen des Typs `Elem` steuert, dessen Zeichenmerkmale von der Klasse `Tr` bestimmt werden.  
  
## Syntax  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_fstream : public basic_iostream<Elem, Tr>  
```  
  
#### Parameter  
 `Elem`  
 Das grundlegende Element des Dateipuffers.  
  
 `Tr`  
 Die Merkmale des grundlegenden Elements des Dateipuffers \(in der Regel `char_traits`\<`Elem`\>\).  
  
## Hinweise  
 Das Objekt speichert ein Objekt der Klasse `basic_filebuf`\<`Elem`, `Tr`\>.  
  
> [!NOTE]
>  Der Lesezeiger \(get\-Zeiger\) und der Schreibzeiger \(put\-Zeiger\) eines fstream\-Objekts sind **NICHT** unabhängig voneinander.  Wenn der get\-Zeiger verschoben wird, wird auch der put\-Zeiger verschoben.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht, wie ein `basic_fstream`\-Objekt erstellt wird, aus dem gelesen und in das geschrieben werden kann.  
  
```  
// basic_fstream_class.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    fstream fs("fstream.txt", ios::in | ios::out | ios::trunc);  
    if (!fs.bad())  
    {  
        // Write to the file.  
        fs << "Writing to a basic_fstream object..." << endl;  
        fs.close();  
  
        // Dump the contents of the file to cout.  
        fs.open("fstream.txt", ios::in);  
        cout << fs.rdbuf();  
        fs.close();  
    }  
}  
```  
  
  **Writing to a basic\_fstream object...**   
### Konstruktoren  
  
|||  
|-|-|  
|[basic\_fstream](../Topic/basic_fstream::basic_fstream.md)|Konstruiert ein Objekt vom Typ `basic_fstream`.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[schließen](../Topic/basic_fstream::close.md)|Schließt eine Datei.|  
|[is\_open](../Topic/basic_fstream::is_open.md)|Ermittelt, ob eine Datei geöffnet ist.|  
|[open](../Topic/basic_fstream::open.md)|Öffnet eine Datei.|  
|[rdbuf](../Topic/basic_fstream::rdbuf.md)|Gibt die Adresse des gespeicherten Streampuffers zurück, die ein Zeiger auf [basic\_stringbuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\> ist.|  
|[swap](../Topic/basic_fstream::swap.md)|Tauscht den Inhalt dieses Objekts gegen den Inhalt eines anderen `basic_fstream`\-Objekts.|  
  
## Anforderungen  
 **Header:** \<fstream\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)