---
title: "&lt;ios&gt;"
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
  - "std.<ios>"
  - "std::<ios>"
  - "<ios>"
  - "ios/std::<ios>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ios-Header"
ms.assetid: d3d4c161-2f37-4f04-93cc-0a2a89984a9c
caps.latest.revision: 20
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# &lt;ios&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert verschiedene Typen und Funktionen, die grundlegend für den Umgang mit iostreams sind.  Dieser Header wird in der Regel von einem anderen iostream\-Header eingeschlossen. Sie müssen ihn nur selten direkt einschließen.  
  
## Syntax  
  
```  
  
#include <ios>  
  
```  
  
## Hinweise  
 Eine große Gruppe von Funktionen sind Manipulatoren.  Ein in \<ios\> deklarierter Manipulator ändert die Werte, die im Argumentobjekt der Klasse [ios\_base](../standard-library/ios-base-class.md) gespeichert sind.  Andere Manipulatoren führen Aktionen für Streams aus, die von Objekten eines Typs gesteuert werden, der von dieser Klasse abgeleitet wurde, z. B. eine Spezialisierung einer der Vorlagenklassen [basic\_istream](../standard-library/basic-istream-class.md) oder [basic\_ostream](../standard-library/basic-ostream-class.md).  [noskipws](../Topic/noskipws.md)\(**str**\) beispielsweise löscht das Format\-Flag `ios_base::skipws` im Objekt **str**, das von einem dieser Typen sein kann.  
  
 Aufgrund von speziellen Einfüge\- und Extraktionsvorgängen für die aus `ios_base` abgeleiteten Klassen können Sie einen Manipulator auch aufrufen, indem Sie ihn in einen Ausgabestream einfügen oder ihn aus einem Eingabestream extrahieren.  Zum Beispiel:  
  
```  
istr >> noskipws;  
```  
  
 Ruft [noskipws](../Topic/noskipws.md)\(**istr**\) auf.  
  
### TypeDefs  
  
|||  
|-|-|  
|[ios](../Topic/ios.md)|Unterstützt die ios\-Klasse aus der alten iostream\-Bibliothek.|  
|[streamoff](../Topic/streamoff.md)|Unterstützt interne Vorgänge.|  
|[streampos](../Topic/streampos.md)|Enthält die aktuelle Position des Pufferzeigers oder Dateizeigers.|  
|[streamsize](../Topic/streamsize.md)|Gibt die Größe des Streams an.|  
|[wios](../Topic/wios.md)|Unterstützt die wios\-Klasse aus der alten iostream\-Bibliothek.|  
|[wstreampos](../Topic/wstreampos.md)|Enthält die aktuelle Position des Pufferzeigers oder Dateizeigers.|  
  
### Manipulatoren  
  
|||  
|-|-|  
|[boolalpha](../Topic/boolalpha.md)|Gibt an, dass Variablen des Typs [bool](../cpp/bool-cpp.md) im Stream als **true** oder **false** angezeigt werden.|  
|[dec](../Topic/dec.md)|Gibt an, dass ganzzahlige Variablen in Basis\-10\-Schreibweise angezeigt werden.|  
|[defaultfloat](../Topic/%3Cios%3E%20defaultfloat.md)|Konfiguriert die Flags eines `ios_base`\-Objekts, sodass ein Standard\-Anzeigeformat für Floatwerte verwendet wird.|  
|[Fest](../Topic/fixed.md)|Gibt an, dass eine Gleitkommazahl in fester Dezimalschreibweise angezeigt wird.|  
|[hex](../Topic/hex.md)|Gibt an, dass ganzzahlige Variablen in Basis\-16\-Schreibweise angezeigt werden.|  
|[internal](../Topic/internal%20\(Standard%20C++%20Library\).md)|Bewirkt, dass ein Nummernzeichen linksbündig und die Zahl rechtsbündig ausgerichtet wird.|  
|[links](../Topic/left.md)|Bewirkt, dass Text, der nicht so breit ist wie die Ausgabebreite, im Stream linksbündig angezeigt wird.|  
|[noboolalpha](../Topic/noboolalpha.md)|Gibt an, dass Variablen des Typs [bool](../cpp/bool-cpp.md) im Stream als 1 oder 0 angezeigt werden.|  
|[noshowbase](../Topic/noshowbase.md)|Deaktiviert die Angabe der Schreibweisenbasis, mit der eine Zahl angezeigt wird.|  
|[noshowpoint](../Topic/noshowpoint.md)|Zeigt nur den ganzzahligen Teil von Gleitkommazahlen an, dessen Bruchteil null ist.|  
|[noshowpos](../Topic/noshowpos.md)|Bewirkt, dass positive Zahlen nicht explizit signiert werden.|  
|[noskipws](../Topic/noskipws.md)|Bewirkt, dass Leerzeichen vom Eingabestream gelesen werden.|  
|[nounitbuf](../Topic/nounitbuf.md)|Bewirkt, dass die Ausgabe gepuffert und verarbeitet wird, wenn der Puffer voll ist.|  
|[nouppercase](../Topic/nouppercase.md)|Gibt an, dass hexadezimale Ziffern und der Exponent in wissenschaftlicher Schreibweise in Kleinbuchstaben angezeigt werden.|  
|[oct](../Topic/oct%20\(%3Cios%3E\).md)|Gibt an, dass ganzzahlige Variablen in Basis\-8\-Schreibweise angezeigt werden.|  
|[rechts](../Topic/right.md)|Bewirkt, dass Text, der nicht so breit ist wie die Ausgabebreite, im Stream rechtsbündig angezeigt wird.|  
|[Wissenschaftliche](../Topic/scientific.md)|Bewirkt, dass Gleitkommazahlen in wissenschaftlicher Schreibweise angezeigt werden.|  
|[showbase](../Topic/showbase.md)|Gibt die Schreibweisenbasis an, mit der eine Zahl angezeigt wird.|  
|[showpoint](../Topic/showpoint.md)|Zeigt den ganzzahligen Teil einer Gleitkommazahl und Ziffern rechts vom Dezimaltrennzeichen an, selbst wenn der Bruchteil null ist.|  
|[showpos](../Topic/showpos.md)|Bewirkt, dass positive Zahlen explizit signiert werden.|  
|[skipws](../Topic/skipws.md)|Bewirkt, dass Leerzeichen nicht vom Eingabestream gelesen werden.|  
|[unitbuf](../Topic/unitbuf.md)|Bewirkt, dass die Ausgabe verarbeitet wird, wenn der Puffer nicht leer ist.|  
|[Großbuchstaben](../Topic/uppercase.md)|Gibt an, dass hexadezimale Ziffern und der Exponent in wissenschaftlicher Schreibweise in Großbuchstaben angezeigt werden.|  
  
### Klassen  
  
|||  
|-|-|  
|[basic\_ios](../standard-library/basic-ios-class.md)|Die Vorlagenklasse beschreibt die Speicher\- und Memberfunktionen, die Eingabestreams \(der Vorlagenklasse [basic\_istream](../standard-library/basic-istream-class.md)\) und Ausgabestreams \(der Vorlagenklasse [basic\_ostream](../standard-library/basic-ostream-class.md)\) gemeinsam sind, die von den Vorlagenparametern abhängen.|  
|[fpos](../standard-library/fpos-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das alle Informationen, die zum Wiederherstellen eines beliebigen Dateipositionsindikators innerhalb eines Streams erforderlich sind, speichern kann.|  
|[ios\_base](../standard-library/ios-base-class.md)|Die Klasse beschreibt die Speicher\- und Memberfunktionen, die Eingabe\- und Ausgabestreams gemeinsam sind, die nicht von den Vorlagenparametern abhängen.|  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)