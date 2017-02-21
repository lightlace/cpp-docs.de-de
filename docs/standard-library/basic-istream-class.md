---
title: "basic_istream-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "basic_istream"
  - "istream/std::basic_istream"
  - "std::basic_istream"
  - "std.basic_istream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_istream-Klasse"
ms.assetid: c7c27111-de6d-42b4-95a3-a7e65259bf17
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# basic_istream-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein Objekt, das das Extrahieren von Elementen und codierten Objekten aus einem Streampuffer mit Elementen des Typs `Elem` steuert, der auch als [char\_type](../Topic/basic_ios::char_type.md) bekannt ist, und dessen Zeichenmerkmale durch die Klasse *Tr* bestimmt werden, die auch als [traits\_type](../Topic/basic_ios::traits_type.md) bekannt ist.  
  
## Syntax  
  
```  
  
     template <class   
     Elem  
     , class   
     Tr  
      = char  
     _  
     traits<  
     Elem  
     > >  
class basic_istream  
   : virtual public basic_ios<Elem, Tr>  
```  
  
## Hinweise  
 Die meisten der Memberfunktionen, die [operator\>\>](../Topic/basic_istream::operator%3E%3E.md) überladen, sind Funktionen für formatierte Eingabe.  Sie entsprechen dem folgenden Muster:  
  
```  
iostate state = goodbit;  
const sentry ok(*this);  
if (ok)  
    {try  
        {<extract elements and convert  
        accumulate flags in state  
        store a successful conversion> }  
    catch (...)  
        {try  
            {setstate(badbit); }  
        catch (...)  
            {}  
        if ((exceptions( ) & badbit) != 0)  
            throw; }}  
setstate(state);  
return (*this);  
```  
  
 Viele weitere Memberfunktionen sind Funktionen für unformatierte Eingabe.  Sie entsprechen dem folgenden Muster:  
  
```  
iostate state = goodbit;  
count = 0;    // the value returned by gcount  
const sentry ok(*this, true);  
if (ok)  
    {try  
        {<extract elements and deliver  
        count extracted elements in count  
        accumulate flags in state> }  
    catch (...)  
        {try  
            {setstate(badbit); }  
        catch (...)  
            {}  
        if ((exceptions( ) & badbit) != 0)  
            throw; }}  
setstate(state);  
```  
  
 Beide Gruppen von Funktionen rufen [setstate](../Topic/basic_ios::setstate.md)**\(eofbit\)** auf, wenn sie beim Extrahieren von Elementen das Dateiende feststellen.  
  
 Ein aus der Klasse `basic_istream`\<`Elem`, *Tr*\> abgeleitetes Objekt speichert Folgendes:  
  
-   Ein virtuelles öffentliches Basisobjekt von der Klasse [basic\_ios](../standard-library/basic-ios-class.md)\<`Elem`, *Tr*\>`.`  
  
-   Eine Extraktionsanzahl für den letzten Vorgang unformatierter Eingabe \(im obigen Code als **count** bezeichnet\).  
  
## Beispiel  
 Weitere Informationen zu Eingabestreams finden Sie im Beispiel für die [basic\_ifstream\-Klasse](../standard-library/basic-ifstream-class.md).  
  
### Konstruktoren  
  
|||  
|-|-|  
|[basic\_istream](../Topic/basic_istream::basic_istream.md)|Konstruiert ein Objekt vom Typ `basic_istream`.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[gcount](../Topic/basic_istream::gcount.md)|Gibt die Anzahl von Zeichen zurück, die bei der letzten unformatierten Eingabe gelesen wurden.|  
|[get](../Topic/basic_istream::get.md)|Liest mindestens ein Zeichen aus dem Eingabestream.|  
|[getline](../Topic/basic_istream::getline.md)|Liest eine Zeile aus dem Eingabestream.|  
|[Ignorieren](../Topic/basic_istream::ignore.md)|Bewirkt, dass eine Anzahl von Elementen ab der aktuellen Leseposition übersprungen werden.|  
|[peek](../Topic/basic_istream::peek.md)|Gibt das nächste zu lesende Zeichen zurück.|  
|[putback](../Topic/basic_istream::putback.md)|Schreibt ein angegebenes Zeichen in den Stream.|  
|[read](../Topic/basic_istream::read.md)|Liest eine angegebene Anzahl von Zeichen aus dem Stream und speichert diese in einem Array.|  
|[readsome](../Topic/basic_istream::readsome.md)|Liest nur aus dem Puffer.|  
|[seekg](../Topic/basic_istream::seekg.md)|Verschiebt die Leseposition in einem Stream.|  
|[sentry](../Topic/basic_istream::sentry.md)|Die geschachtelte Klasse beschreibt ein Objekt, dessen Deklaration die Funktionen für formatierte Eingabe und für unformatierte Eingabe strukturiert.|  
|[swap](../Topic/basic_istream::swap.md)|Tauscht dieses `basic_istream`\-Objekt gegen den bereitgestellten `basic_istream`\-Objektparameter aus.|  
|[sync](../Topic/basic_istream::sync.md)|Synchronisiert das Eingabegerät, das dem Stream zugeordnet ist, mit dem Puffer des Streams.|  
|[tellg](../Topic/basic_istream::tellg.md)|Meldet die aktuelle Leseposition im Stream.|  
|[unget](../Topic/basic_istream::unget.md)|Schreibt das zuletzt gelesene Zeichen zurück in den Stream.|  
  
### Operatoren  
  
|||  
|-|-|  
|[Operator \>\>](../Topic/basic_istream::operator%3E%3E.md)|Ruft eine Funktion für den Eingabestream auf oder liest formatierte Daten aus dem Eingabestream.|  
|[operator \=](../Topic/basic_istream::operator=.md)|Weist den `basic_istream` auf der rechten Seite des Operators diesem Objekt zu.  Dies ist eine Verschiebezuweisung mit einem `rvalue`\-Verweis, der keine Kopie hinterlässt.|  
  
## Anforderungen  
 **Header:** \<istream\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)