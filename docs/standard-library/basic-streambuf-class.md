---
title: "basic_streambuf-Klasse"
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
  - "basic_streambuf"
  - "streambuf/std::basic_streambuf"
  - "std.basic_streambuf"
  - "std::basic_streambuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_streambuf-Klasse"
ms.assetid: 136af6c3-13bf-4501-9288-b93da26efac7
caps.latest.revision: 27
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# basic_streambuf-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt eine abstrakte Basisklasse für das Ableiten eines Streampuffers, die die Übertragung von Elementen an eine bestimmte und von einer bestimmten Darstellung eines Streams steuert.  
  
## Syntax  
  
```  
template<class Elem, class Tr = char_traits<Elem> >  
   class basic_streambuf;  
```  
  
#### Parameter  
 `Elem`  
 Ein [char\_type](../Topic/basic_streambuf::char_type.md).  
  
 `Tr`  
 Der [traits\_type](../Topic/basic_streambuf::traits_type.md) der Zeichen.  
  
## Hinweise  
 Die Vorlagenklasse beschreibt eine abstrakte Basisklasse für die Ableitung eines Streampuffers, der die Übertragung von Elementen in eine und aus einer bestimmten Darstellung eines Streams steuert.  Ein Objekt der Klasse `basic_streambuf` dient zur Steuerung eines Streams mit Elementen vom Typ `Tr`, auch als [char\_type](../Topic/basic_streambuf::char_type.md) bezeichnet, dessen Zeichenmerkmale durch die Klasse [char\_traits](../standard-library/char-traits-struct.md), auch als [traits\_type](../Topic/basic_streambuf::traits_type.md) bezeichnet, bestimmt werden.  
  
 Jeder Streampuffer steuert konzeptuell zwei unabhängige Streams: einen für Extraktionen \(Eingabe\) und einen für Einfügungen \(Ausgabe\).  Eine bestimmte Darstellung kann jedoch den Zugriff auf einen oder beide Streams unmöglich machen.  In der Regel besteht eine bestimmte Beziehung zwischen den beiden Streams.  Was Sie in den Ausgabestream eines [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<`Elem`, `Tr`\>\-Objekts einfügen, extrahieren Sie beispielsweise später aus dem Eingabestream.  Wenn Sie einen Stream eines [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\>\-Objekts positionieren, positionieren Sie den anderen entsprechend.  
  
 Die öffentliche Schnittstelle zur Vorlagenklasse `basic_streambuf` stellt die Vorgänge bereit, die für alle Streampuffer gemeinsam sind, jedoch spezialisiert.  Die geschützte Schnittstelle stellt die Vorgänge bereit, die für die Verwendung einer bestimmten Darstellung eines Streams benötigt werden.  Über die geschützten virtuellen Memberfunktionen können Sie das Verhalten eines abgeleiteten Streampuffers für eine bestimmte Darstellung eines Streams anpassen.  Jeder abgeleitete Streampuffer in dieser Bibliothek beschreibt, wie er das Verhalten seiner geschützten virtuellen Memberfunktionen spezialisiert.  Das Standardverhalten für die Basisklasse, das häufig darin besteht, nichts zu tun, wird in diesem Thema beschrieben.  
  
 Die verbleibenden geschützten Memberfunktionen steuern das Kopieren in und aus Speicher, der zum Puffern von Übertragungen in und aus Streams bereitgestellt wird.  Ein Eingabepuffer ist z. B. durch folgende Merkmale charakterisiert:  
  
-   [eback](../Topic/basic_streambuf::eback.md), einen Zeiger auf den Anfang des Puffers.  
  
-   [gptr](../Topic/basic_streambuf::gptr.md), einen Zeiger auf das nächste zu lesende Element.  
  
-   [egptr](../Topic/basic_streambuf::egptr.md), einen Zeiger hinter das Ende des Puffers.  
  
 Entsprechend ist ein Ausgabepuffer gekennzeichnet durch:  
  
-   [pbase](../Topic/basic_streambuf::pbase.md), einen Zeiger auf den Anfang des Puffers.  
  
-   [pptr](../Topic/basic_streambuf::pptr.md), einen Zeiger auf das nächste zu schreibende Element.  
  
-   [epptr](../Topic/basic_streambuf::epptr.md), einen Zeiger hinter das Ende des Puffers.  
  
 Für alle Puffer wird das folgende Protokoll verwendet:  
  
-   Wenn der Zeiger für das nächste Element NULL ist, ist kein Puffer vorhanden.  Ansonsten zeigen alle drei Zeiger in dieselbe Sequenz.  Sie können problemlos in Bezug auf die Reihenfolge verglichen werden.  
  
-   Wenn bei einem Ausgabepuffer der Zeiger für das nächste Element kleiner als der Endzeiger ist, können Sie ein Element an der vom Zeiger für das nächste Element bezeichneten Schreibposition speichern.  
  
-   Wenn bei einem Eingabepuffer der Zeiger für das nächste Element kleiner als der Endzeiger ist, können Sie ein Element an der vom Zeiger für das nächste Element bezeichneten Leseposition lesen.  
  
-   Wenn bei einem Eingabepuffer der Startzeiger kleiner als der Zeiger für das nächste Element ist, können Sie ein Element an der vom verminderten Zeiger für das nächste Element bezeichneten Position wiederherstellen.  
  
 Jede geschützte virtuelle Memberfunktion, die Sie für eine von `basic_streambuf`\<`Elem`, `Tr`\> abgeleitete Klasse schreiben, muss zur Erfüllung dieses Protokolls beitragen.  
  
 Ein Objekt der Klasse `basic_streambuf`\<`Elem`, `Tr`\> speichert die zuvor beschriebenen sechs Zeiger.  Außerdem speichert es ein Gebietsschemaobjekt in einem Objekt vom Typ [locale](../standard-library/locale-class.md) für die mögliche Verwendung durch einen abgeleiteten Streampuffer.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[basic\_streambuf](../Topic/basic_streambuf::basic_streambuf.md)|Konstruiert ein Objekt vom Typ `basic_streambuf`.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[char\_type](../Topic/basic_streambuf::char_type.md)|Verknüpft einen Typnamen mit dem `Elem`\-Vorlagenparameter.|  
|[int\_type](../Topic/basic_streambuf::int_type.md)|Verknüpft einen Typnamen im Geltungsbereich von `basic_streambuf` mit dem `Elem`\-Vorlagenparameter.|  
|[off\_type](../Topic/basic_streambuf::off_type.md)|Verknüpft einen Typnamen im Geltungsbereich von `basic_streambuf` mit dem `Elem`\-Vorlagenparameter.|  
|[pos\_type](../Topic/basic_streambuf::pos_type.md)|Verknüpft einen Typnamen im Geltungsbereich von `basic_streambuf` mit dem `Elem`\-Vorlagenparameter.|  
|[traits\_type](../Topic/basic_streambuf::traits_type.md)|Verknüpft einen Typnamen mit dem `Tr`\-Vorlagenparameter.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[eback](../Topic/basic_streambuf::eback.md)|Eine geschützte Funktion, die einen Zeiger auf den Anfang des Eingabepuffers zurückgibt.|  
|[egptr](../Topic/basic_streambuf::egptr.md)|Eine geschützte Funktion, die einen Zeiger direkt hinter das Ende des Eingabepuffers zurückgibt.|  
|[epptr](../Topic/basic_streambuf::epptr.md)|Eine geschützte Funktion, die einen Zeiger direkt hinter das Ende des Ausgabepuffers zurückgibt.|  
|[gbump](../Topic/basic_streambuf::gbump.md)|Eine geschützte Funktion, die dem nächsten Zeiger für den Eingabepuffer `_Count` hinzufügt.|  
|[getloc](../Topic/basic_streambuf::getloc.md)|Ruft das Gebietsschema des `basic_streambuf`\-Objekts ab.|  
|[gptr](../Topic/basic_streambuf::gptr.md)|Eine geschützte Funktion, die einen Zeiger auf das nächste Element des Eingabepuffers zurückgibt.|  
|[imbue](../Topic/basic_streambuf::imbue.md)|Eine geschützte virtuelle Funktion, die von [pubimbue](../Topic/basic_streambuf::pubimbue.md) aufgerufen wird.|  
|[in\_avail](../Topic/basic_streambuf::in_avail.md)|Gibt die Anzahl von Elementen zurück, die aus dem Puffer gelesen werden können.|  
|[Überlauf](../Topic/basic_streambuf::overflow.md)|Eine geschützte virtuelle Funktion, die aufgerufen werden kann, wenn ein neues Zeichen in einen vollen Puffer eingefügt wird.|  
|[pbackfail](../Topic/basic_streambuf::pbackfail.md)|Eine geschützte virtuelle Memberfunktion, die versucht, ein Element zurück in den Eingabestream zu versetzen und es dann zum aktuellen Element zu ernennen \(es wird mit dem Zeiger für das nächste Element darauf gezeigt\).|  
|[pbase](../Topic/basic_streambuf::pbase.md)|Eine geschützte Funktion, die einen Zeiger auf den Anfang des Ausgabepuffers zurückgibt.|  
|[pbump](../Topic/basic_streambuf::pbump.md)|Eine geschützte Funktion, die dem nächsten Zeiger für den Ausgabepuffer `count` hinzufügt.|  
|[pptr](../Topic/basic_streambuf::pptr.md)|Eine geschützte Funktion, die einen Zeiger auf das nächste Element des Ausgabepuffers zurückgibt.|  
|[pubimbue](../Topic/basic_streambuf::pubimbue.md)|Legt das Gebietsschema des `basic_streambuf`\-Objekts fest.|  
|[pubseekoff](../Topic/basic_streambuf::pubseekoff.md)|Ruft [seekoff](../Topic/basic_streambuf::seekoff.md) auf, eine geschützte virtuelle Funktion, die in einer abgeleiteten Klasse überschrieben wird.|  
|[pubseekpos](../Topic/basic_streambuf::pubseekpos.md)|Ruft [seekpos](../Topic/basic_streambuf::seekpos.md) auf, eine geschützte virtuelle Funktion, die in einer abgeleiteten Klasse überschrieben wird, und setzt die aktuelle Zeigerposition zurück.|  
|[pubsetbuf](../Topic/basic_streambuf::pubsetbuf.md)|Ruft [setbuf](../Topic/basic_streambuf::setbuf.md) auf, eine geschützte virtuelle Funktion, die in einer abgeleiteten Klasse überschrieben wird.|  
|[pubsync](../Topic/basic_streambuf::pubsync.md)|Ruft [sync](../Topic/basic_streambuf::sync.md) auf, eine geschützte virtuelle Funktion, die in einer abgeleiteten Klasse überschrieben wird, und aktualisiert den externen Stream für diesen Puffer.|  
|[sbumpc](../Topic/basic_streambuf::sbumpc.md)|Liest das aktuelle Element, gibt es zurück und bewegt den Streamzeiger.|  
|[seekoff](../Topic/basic_streambuf::seekoff.md)|Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.|  
|[seekpos](../Topic/basic_streambuf::seekpos.md)|Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.|  
|[setbuf](../Topic/basic_streambuf::setbuf.md)|Die geschützte virtuelle Memberfunktion führt einen für jeden abgeleiteten Streampuffer bestimmten Vorgang aus.|  
|[setg](../Topic/basic_streambuf::setg.md)|Eine geschützte Funktion, die `_Gbeg` im Startzeiger, `_Gnext` im nächssten Zeiger und `_Gend` im Endzeiger für den Eingabepuffer speichert.|  
|[setp](../Topic/basic_streambuf::setp.md)|Eine geschützte Funktion, die `_Pbeg` im Startzeiger und `_Pend` im Endzeiger für den Ausgabepuffer speichert.|  
|[sgetc](../Topic/basic_streambuf::sgetc.md)|Gibt das aktuelle Element ohne Änderung der Position im Stream zurück.|  
|[sgetn](../Topic/basic_streambuf::sgetn.md)|Gibt die Anzahl der gelesenen Elemente zurück.|  
|[showmanyc](../Topic/basic_streambuf::showmanyc.md)|Eine geschützte virtuelle Memberfunktion, die die Anzahl von Zeichen zurückgibt, die aus dem Eingabestream extrahiert werden können, und stellt sicher, dass das Programm keiner unbegrenzten Wartezeit unterliegt.|  
|[snextc](../Topic/basic_streambuf::snextc.md)|Liest das aktuelle Element und gibt das folgende Element zurück.|  
|[sputbackc](../Topic/basic_streambuf::sputbackc.md)|Schreibt einen `char_type` in den Stream.|  
|[sputc](../Topic/basic_streambuf::sputc.md)|Setzt ein Zeichen in den Stream.|  
|[sputn](../Topic/basic_streambuf::sputn.md)|Setzt eine Zeichenfolge in den Stream.|  
|[stossc](../Topic/basic_streambuf::stossc.md)|Verschiebt den Zeiger hinter das aktuelle Element im Stream.|  
|[sungetc](../Topic/basic_streambuf::sungetc.md)|Ruft ein Zeichen aus dem Stream ab.|  
|[swap](../Topic/basic_streambuf::swap.md)|Tauscht die Werte in diesem Objekt mit den Werten im bereitgestellten `basic_streambuf`\-Objektparameter.|  
|[sync](../Topic/basic_streambuf::sync.md)|Eine geschützte virtuelle Funktion, die versucht, die gesteuerten Streams mit zugehörigen externen Streams zu synchronisieren.|  
|[uflow](../Topic/basic_streambuf::uflow.md)|Eine geschützte virtuelle Funktion, die das aktuelle Element aus dem Eingabestream extrahiert.|  
|[underflow](../Topic/basic_streambuf::underflow.md)|Eine geschützte virtuelle Funktion, die das aktuelle Element aus dem Eingabestream extrahiert.|  
|[xsgetn](../Topic/basic_streambuf::xsgetn.md)|Eine geschützte virtuelle Funktion, die Elemente aus dem Eingabestream extrahiert.|  
|[xsputn](../Topic/basic_streambuf::xsputn.md)|Eine geschützte virtuelle Funktion, die Elemente in den Ausgabestream einfügt.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator \=](../Topic/basic_streambuf::operator=.md)|Weist den Werten dieses Objekts Werte aus einem anderen `basic_streambuf`\-Objekt zu.|  
  
## Anforderungen  
 **Header:** \<streambuf\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)