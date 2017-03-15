---
title: "basic_filebuf-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.basic_filebuf"
  - "fstream/std::basic_filebuf"
  - "std::basic_filebuf"
  - "basic_filebuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_filebuf-Klasse"
ms.assetid: 3196ba5c-bf38-41bd-9a95-70323ddfca1a
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# basic_filebuf-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt einen die Übertragung zu und aus einer Sequenz von in einer externen Datei gespeicherten Elementen von Elementen des Typs `Elem` steuernden Streampuffer, dessen Zeichenmerkmale durch die Klasse `Tr` ermittelt werden.  
  
## Syntax  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_filebuf : public basic_streambuf<Elem, Tr>  
```  
  
#### Parameter  
 `Elem`  
 Das grundlegende Element des Dateipuffers.  
  
 `Tr`  
 Die Merkmale des grundlegenden Elements des Dateipuffers \(in der Regel `char_traits`\<`Elem`\>\).  
  
## Hinweise  
 Die Vorlagenklasse beschreibt einen die Übertragung zu und aus einer Sequenz von in einer externen Datei gespeicherten Elementen von Elementen des Typs `Elem` steuernden Streampuffer, dessen Zeichenmerkmale durch die Klasse `Tr` ermittelt werden.  
  
> [!NOTE]
>  Objekte des Typs `basic_filebuf` werden mit einem internen Puffer des Typs `char *` erstellt, unabhängig vom durch den Typparameter `Elem` angegebenen `char_type`.  Eine Unicode\-Zeichenfolge \(die `wchar_t`\-Zeichen enthält\) wird demnach in eine ANSI\-Zeichenfolge \(die `char`\-Zeichen enthält\) umgewandelt, bevor sie in den internen Puffer geschrieben wird.  Erstellen Sie zum Speichern von Unicode\-Zeichenfolgen im Puffer einen neuen Puffer des Typs `wchar_t`, und legen Sie ihn mithilfe der Methode [basic\_streambuf::pubsetbuf](../Topic/basic_streambuf::pubsetbuf.md)`()` fest.  Ein Beispiel, in dem dieses Verhalten veranschaulicht wird, finden Sie im Folgenden.  
  
 Ein Objekt der Klasse `basic_filebuf`\<`Elem`, `Tr`\> speichert einen Dateizeiger, der das `FILE`\-Objekt angibt, welches den mit einer geöffneten Datei verknüpften Stream steuert.  Es speichert zudem Zeiger zu zwei Dateikonvertierungs\-Facets für die Verwendung durch die geschützten Memberfunktionen [overflow](../Topic/basic_filebuf::overflow.md) und [underflow](../Topic/basic_filebuf::underflow.md).  Weitere Informationen finden Sie unter [basic\_filebuf::open](../Topic/basic_filebuf::open.md).  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie ein Objekt des Typs `basic_filebuf<wchar_t>` gezwungen wird, Unicode\-Zeichen in seinem internen Puffer durch den Aufruf der `pubsetbuf()`\-Methode zu speichern.  
  
```  
// unicode_basic_filebuf.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string>  
#include <fstream>  
#include <iomanip>  
#include <memory.h>  
#include <string.h>  
  
#define IBUFSIZE 16  
  
using namespace std;  
  
void hexdump(const string& filename);  
  
int main()  
{  
    wchar_t* wszHello = L"Hello World";  
    wchar_t wBuffer[128];  
  
    basic_filebuf<wchar_t> wOutFile;  
  
    // Open a file, wcHello.txt, then write to it, then dump the  
    // file's contents in hex  
    wOutFile.open("wcHello.txt",  
        ios_base::out | ios_base::trunc | ios_base::binary);  
    if(!wOutFile.is_open())  
    {  
        cout << "Error Opening wcHello.txt\n";  
        return -1;  
    }  
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));  
    wOutFile.close();  
    cout << "Hex Dump of wcHello.txt - note that output is ANSI chars:\n";  
    hexdump(string("wcHello.txt"));  
  
    // Open a file, wwHello.txt, then set the internal buffer of  
    // the basic_filebuf object to be of type wchar_t, then write  
    // to the file and dump the file's contents in hex  
    wOutFile.open("wwHello.txt",  
        ios_base::out | ios_base::trunc | ios_base::binary);  
    if(!wOutFile.is_open())  
    {  
        cout << "Error Opening wwHello.txt\n";  
        return -1;  
    }  
    wOutFile.pubsetbuf(wBuffer, (streamsize)128);  
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));  
    wOutFile.close();  
    cout << "\nHex Dump of wwHello.txt - note that output is wchar_t chars:\n";  
    hexdump(string("wwHello.txt"));  
  
    return 0;  
}  
  
// dump contents of filename to stdout in hex  
void hexdump(const string& filename)  
{  
    fstream ifile(filename.c_str(),  
        ios_base::in | ios_base::binary);  
    char *ibuff = new char[IBUFSIZE];  
    char *obuff = new char[(IBUFSIZE*2)+1];  
    int i;  
  
    if(!ifile.is_open())  
    {  
        cout << "Cannot Open " << filename.c_str()  
             << " for reading\n";  
        return;  
    }  
    if(!ibuff || !obuff)  
    {  
        cout << "Cannot Allocate buffers\n";  
        ifile.close();  
        return;  
    }  
  
    while(!ifile.eof())  
    {  
        memset(obuff,0,(IBUFSIZE*2)+1);  
        memset(ibuff,0,IBUFSIZE);  
        ifile.read(ibuff,IBUFSIZE);  
  
        // corner case where file is exactly a multiple of  
        // 16 bytes in length  
        if(ibuff[0] == 0 && ifile.eof())  
            break;  
  
        for(i = 0; i < IBUFSIZE; i++)  
        {  
            if(ibuff[i] >= ' ')  
                obuff[i] = ibuff[i];  
            else  
                obuff[i] = '.';  
  
            cout << setfill('0') << setw(2) << hex  
                 << (int)ibuff[i] << ' ';  
        }  
        cout << "  " << obuff << endl;  
    }  
    ifile.close();  
}  
```  
  
  **Hexadezimales Speicherabbild von „wcHello.txt“, beachten Sie, dass diese Ausgabe ANSI\-Zeichen aufweist:**  
**48 65 6c 6c 6f 20 57 6f 72 6c 64 00 00 00 00 00   Hello World.....  Hexadezimales Speicherabbild von „wcHello.txt“, beachten Sie, dass diese Ausgabe wchar\_t\-Zeichen aufweist:**  
**48 00 65 00 6c 00 6c 00 6f 00 20 00 57 00 6f 00   H.e.l.l.o.  .W.o.  72 00 6c 00 64 00 00 00 00 00 00 00 00 00 00 00   r.l.d...........**    
### Konstruktoren  
  
|||  
|-|-|  
|[basic\_filebuf](../Topic/basic_filebuf::basic_filebuf.md)|Konstruiert ein Objekt vom Typ `basic_filebuf`.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[char\_type](../Topic/basic_filebuf::char_type.md)|Verknüpft einen Typnamen mit dem `Elem`\-Vorlagenparameter.|  
|[int\_type](../Topic/basic_filebuf::int_type.md)|Stellt den Typ im Bereich von `basic_filebuf` dem Typ desselben Namens im Bereich `Tr` gleich.|  
|[off\_type](../Topic/basic_filebuf::off_type.md)|Stellt den Typ im Bereich von `basic_filebuf` dem Typ desselben Namens im Bereich `Tr` gleich.|  
|[pos\_type](../Topic/basic_filebuf::pos_type.md)|Stellt den Typ im Bereich von `basic_filebuf` dem Typ desselben Namens im Bereich `Tr` gleich.|  
|[traits\_type](../Topic/basic_filebuf::traits_type.md)|Verknüpft einen Typnamen mit dem `Tr`\-Vorlagenparameter.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[schließen](../Topic/basic_filebuf::close.md)|Schließt eine Datei.|  
|[is\_open](../Topic/basic_filebuf::is_open.md)|Gibt an, ob eine Datei geöffnet ist.|  
|[open](../Topic/basic_filebuf::open.md)|Öffnet eine Datei.|  
|[Überlauf](../Topic/basic_filebuf::overflow.md)|Eine geschützte virtuelle Funktion, die aufgerufen werden kann, wenn ein neues Zeichen in einen vollen Puffer eingefügt wird.|  
|[pbackfail](../Topic/basic_filebuf::pbackfail.md)|Die geschützte virtuelle Memberfunktion versucht, ein Element zurück in den Eingabestream zu versetzen und es dann zum aktuellen Element zu ernennen \(wird mit dem nächsten Zeiger darauf gezeigt\).|  
|[seekoff](../Topic/basic_filebuf::seekoff.md)|Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.|  
|[seekpos](../Topic/basic_filebuf::seekpos.md)|Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.|  
|[setbuf](../Topic/basic_filebuf::setbuf.md)|Die geschützte virtuelle Memberfunktion führt einen für jeden abgeleiteten Streampuffer bestimmten Vorgang aus.|  
|[Swap](../Topic/basic_filebuf::swap.md)|Tauscht den `basic_filebuf`\-Inhalt mit dem Inhalt des angegebenen `basic_filebuf`\-Parameters.|  
|[sync](../Topic/basic_filebuf::sync.md)|Die geschützte virtuelle Funktion versucht, die gesteuerten Streams mit zugehörigen externen Streams zu synchronisieren.|  
|[uflow](../Topic/basic_streambuf::uflow.md)|Die geschützte virtuelle Funktion versucht, das aktuelle Element aus dem Eingabestream zu extrahieren.|  
|[underflow](../Topic/basic_filebuf::underflow.md)|Die geschützte virtuelle Funktion versucht, das aktuelle Element aus dem Eingabestream zu extrahieren.|  
  
## Anforderungen  
 **Header:** \<fstream\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<fstream\>](../standard-library/fstream.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)