---
title: "ios_base-Klasse"
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
  - "ios_base"
  - "std.ios_base"
  - "std::ios_base"
  - "xiosbase/std::ios_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ios_base-Klasse"
ms.assetid: 0f9e0abc-f70f-49bc-aa1f-003859f56cfe
caps.latest.revision: 21
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# ios_base-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Klasse beschreibt die Speicher\- und Memberfunktionen, die Eingabe\- und Ausgabestreams gemeinsam sind, die nicht von den Vorlagenparametern abhängen.  \(Die Vorlagenklasse [basic\_ios](../standard-library/basic-ios-class.md) beschreibt, welche Funktionen gemeinsam und von Vorlagenparametern abhängig sind.\)  
  
 Ein Objekt der ios\_base\-Klasse speichert Formatierungsinformationen, die aus Folgendem bestehen:  
  
-   Formatflags in einem Objekt vom Typ [fmtflags](../Topic/ios_base::fmtflags.md).  
  
-   Eine Ausnahmemaske in einem Objekt vom Typ [iostate](../Topic/ios_base::iostate.md).  
  
-   Eine Feldbreite in einem Objekt vom Typ `int`*.*  
  
-   Eine Anzeigegenauigkeit in einem Objekt vom Typ `int`.  
  
-   Ein Gebietsschemaobjekt in einem Objekt vom Typ **locale**.  
  
-   Zwei erweiterbare Arrays mit Elementen vom Typ **long** und `void`\-Zeiger.  
  
 Ein Objekt der ios\_base\-Klasse speichert auch Zustandsinformationen für Streams in einem Objekt vom Typ [iostate](../Topic/ios_base::iostate.md) und einen Rückrufstapel.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[ios\_base](../Topic/ios_base::ios_base.md)|Erstellt `ios_base`\-Objekte.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[event\_callback](../Topic/ios_base::event_callback.md)|Beschreibt eine Funktion, die an [register\_call](../Topic/ios_base::register_callback.md) übergeben wird.|  
|[fmtflags](../Topic/ios_base::fmtflags.md)|Konstanten, mit denen das Aussehen der Ausgabe angegeben wird.|  
|[iostate](../Topic/ios_base::iostate.md)|Definiert Konstanten, die den Zustand eines Streams beschreiben.|  
|[openmode](../Topic/ios_base::openmode.md)|Beschreibt, wie mit einem Stream interagiert wird.|  
|[seekdir](../Topic/ios_base::seekdir.md)|Gibt den Startpunkt für Offsetvorgänge an.|  
  
### Enumerationen  
  
|||  
|-|-|  
|[Ereignis](../Topic/ios_base::event.md)|Gibt Ereignistypen an.|  
  
### Konstanten  
  
|||  
|-|-|  
|[adjustfield](../Topic/ios_base::fmtflags.md)|Eine Bitmaske, definiert als `internal` &#124; `left` &#124; `right`.|  
|[app](../Topic/ios_base::openmode.md)|Gibt an, dass vor jeder Einfügung das Ende eines Streams gesucht wird.|  
|[ate](../Topic/ios_base::openmode.md)|Gibt an, dass bei der anfänglichen Erstellung des steuernden Objekts das Ende eines Streams gesucht wird.|  
|[badbit](../Topic/ios_base::iostate.md)|Protokolliert einen Verlust der Integrität des Streampuffers.|  
|[basefield](../Topic/ios_base::fmtflags.md)|Eine Bitmaske, definiert als `dec` &#124; `hex` &#124; `oct`.|  
|[beg](../Topic/ios_base::seekdir.md)|Gibt an, dass relativ zum Anfang einer Sequenz gesucht werden soll.|  
|[Binär](../Topic/ios_base::openmode.md)|Gibt an, dass eine Datei als binärer Stream und nicht als Textstream gelesen werden soll.|  
|[boolalpha](../Topic/ios_base::fmtflags.md)|Gibt an, dass Objekte vom Typ `bool` als Namen \(wie `true` und `false`\) statt als numerische Werte eingefügt oder extrahiert werden sollen.|  
|[cur](../Topic/ios_base::seekdir.md)|Gibt an, dass in einer Sequenz relativ zur aktuellen Position gesucht werden soll.|  
|[dec](../Topic/ios_base::fmtflags.md)|Gibt an, dass ganzzahlige Werte im Dezimalformat eingefügt oder extrahiert werden sollen.|  
|[end](../Topic/ios_base::seekdir.md)|Gibt an, dass relativ zum Ende einer Sequenz gesucht werden soll.|  
|[eofbit](../Topic/ios_base::iostate.md)|Protokolliert beim Extrahieren aus einem Stream das Dateiende.|  
|[failbit](../Topic/ios_base::iostate.md)|Protokolliert einen Fehler beim Extrahieren eines gültigen Felds aus einem Stream.|  
|[Fest](../Topic/ios_base::fmtflags.md)|Gibt an, dass Gleitkommawerte im Festkommaformat \(ohne Exponentenfeld\) eingefügt werden sollen.|  
|[floatfield](../Topic/ios_base::fmtflags.md)|Eine Bitmaske, definiert als `fixed` &#124; `scientific`|  
|[goodbit](../Topic/ios_base::iostate.md)|Kein Zustandsbit ist gesetzt.|  
|[hex](../Topic/ios_base::fmtflags.md)|Gibt an, dass ganzzahlige Werte im Hexadezimalformat eingefügt oder extrahiert werden sollen.|  
|[in](../Topic/ios_base::openmode.md)|Gibt die Extraktion aus einem Stream an.|  
|[internal](../Topic/ios_base::fmtflags.md)|Füllt bis zu einer Feldbreite auf, indem Füllzeichen an einem Punkt eingefügt werden, der sich intern in einem generierten numerischen Feld befindet.|  
|[links](../Topic/ios_base::fmtflags.md)|Gibt linksbündige Ausrichtung an.|  
|[oct](../Topic/ios_base::fmtflags.md)|Gibt an, dass ganzzahlige Werte im Oktalformat eingefügt oder extrahiert werden sollen.|  
|[out](../Topic/ios_base::openmode.md)|Gibt die Einfügung in einen Stream an.|  
|[rechts](../Topic/ios_base::fmtflags.md)|Gibt rechtsbündige Ausrichtung an.|  
|[Wissenschaftliche](../Topic/ios_base::fmtflags.md)|Gibt an, dass Gleitkommawerte im wissenschaftlichen Format \(mit Exponentenfeld\) eingefügt werden sollen.|  
|[showbase](../Topic/ios_base::fmtflags.md)|Gibt die Einfügung eines Präfixes an, das die Basis eines generierten ganzzahigen Felds angibt.|  
|[showpoint](../Topic/ios_base::fmtflags.md)|Gibt die unbedingte Einfügung eines Dezimaltrennzeichens in einem generierten Gleitkommafeld an.|  
|[showpos](../Topic/ios_base::fmtflags.md)|Gibt die Einfügung eines Pluszeichens \(\+\) in einem nicht negativen generierten numerischen Feld an.|  
|[skipws](../Topic/ios_base::fmtflags.md)|Gibt an, dass führende Leerzeichen vor bestimmten Extraktionen übersprungen werden sollen.|  
|[trunc](../Topic/ios_base::openmode.md)|Gibt an, dass der Inhalt einer vorhandenen Datei gelöscht werden soll, wenn deren steuerndes Objekt erstellt wird.|  
|[unitbuf](../Topic/ios_base::fmtflags.md)|Bewirkt, dass die Ausgabe nach jeder Einfügung geleert wird.|  
|[Großbuchstaben](../Topic/ios_base::fmtflags.md)|Gibt an, dass bei bestimmten Einfügevorgängen die Großbuchstaben eingefügt werden, die den Kleinbuchstaben entsprechen.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[Fehler](../Topic/ios_base::failure.md)|Die Memberklasse dient als Basisklasse für alle Ausnahmen, die von der Memberfunktion [clear](../Topic/basic_ios::clear.md) in der Vorlagenklasse [basic\_ios](../standard-library/basic-ios-class.md) ausgelöst werden.|  
|[Flags](../Topic/ios_base::flags.md)|Legt die aktuellen Flageinstellungen fest oder gibt sie zurück.|  
|[getloc](../Topic/ios_base::getloc.md)|Gibt das gespeicherte Gebietsschemaobjekt zurück.|  
|[imbue](../Topic/ios_base::imbue.md)|Ändert das Gebietsschema.|  
|[Init](../Topic/ios_base::Init.md)|Erstellt bei der Konstruktion die iostream\-Standardobjekte.|  
|[iword](../Topic/ios_base::iword.md)|Weist einen als `iword` zu speichernden Wert zu.|  
|[Präzision](../Topic/ios_base::precision.md)|Gibt die Anzahl der anzuzeigenden Ziffern in einer Gleitkommazahl an.|  
|[pword](../Topic/ios_base::pword.md)|Weist einen als `pword` zu speichernden Wert zu.|  
|[register\_callback](../Topic/ios_base::register_callback.md)|Gibt eine Rückruffunktion an.|  
|[setf](../Topic/ios_base::setf.md)|Legt die angegebenen Flags fest.|  
|[sync\_with\_stdio](../Topic/ios_base::sync_with_stdio.md)|Stellt sicher, dass iostream\-Vorgänge und Vorgänge der C\-Laufzeitbibliothek in der Reihenfolge ausgeführt werden, in der sie im Quellcode stehen.|  
|[unsetf](../Topic/ios_base::unsetf.md)|Bewirkt, dass die angegebenen Flags deaktiviert werden.|  
|[Breite](../Topic/ios_base::width.md)|Legt die Länge des Ausgabestreams fest.|  
|[xalloc](../Topic/ios_base::xalloc.md)|Gibt an, dass eine Variable Teil des Streams sein soll.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator \=](../Topic/ios_base::operator=.md)|Der Zuweisungsoperator für `ios_base`\-Objekte.|  
  
## Anforderungen  
 **Header:** \<ios\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)