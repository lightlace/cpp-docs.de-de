---
title: "basic_ios-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.basic_ios"
  - "ios/std::basic_ios"
  - "basic_ios"
  - "std::basic_ios"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_ios-Klasse"
ms.assetid: 4fdcd8e1-62d2-4611-8a70-1e4f58434007
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# basic_ios-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt die Speicher\- und Memberfunktionen, die Eingabestreams \(der Vorlagenklasse [basic\_istream](../standard-library/basic-istream-class.md)\) und Ausgabestreams \(der Vorlagenklasse [basic\_ostream](../standard-library/basic-ostream-class.md)\) gemeinsam sind, die von den Vorlagenparametern abhängen.  \(Die Klasse [ios\_base](../standard-library/ios-base-class.md) beschreibt, welche Funktionen gemeinsam und nicht von Vorlagenparametern abhängig sind.\) Ein aus der Klasse **basic\_ios\<class Elem, class Traits\>** abgeleitetes Objekt steuert einen Stream mit Elementen des Typs **Elem**, dessen Zeichenmerkmale durch die **Traits**\-Klasse bestimmt werden.  
  
## Syntax  
  
```  
  
     template <class   
     Elem  
     , class   
     Traits  
     >  
class basic_ios : public ios_base  
```  
  
#### Parameter  
 `Elem`  
 Ein Typ.  
  
 `Traits`  
 Eine Variable des Typs `char_traits`.  
  
## Hinweise  
 Ein aus der Klasse **basic\_ios\<class Elem, class Traits\>** abgeleitetes Objekt speichert Folgendes:  
  
-   Einen tie\-Zeiger auf ein Objekt des Typs [basic\_istream](../standard-library/basic-istream-class.md)**\<Elem, Traits\>**.  
  
-   Einen Streampufferzeiger auf ein Objekt des Typs [basic\_streambuf](../standard-library/basic-streambuf-class.md)**\<Elem, Traits\>**.  
  
-   [Formatierungsinformationen](../standard-library/ios-base-class.md)  
  
-   [Streamzustandsinformationen](../standard-library/ios-base-class.md) in einem Basisobjekt des Typs [ios\_base](../standard-library/ios-base-class.md).  
  
-   Ein Füllzeichen in einem Objekt des Typs `char_type`.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[basic\_ios](../Topic/basic_ios::basic_ios.md)|Erstellt die `basic_ios`\-Klasse.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[char\_type](../Topic/basic_ios::char_type.md)|Ein Synonym für den Vorlagenparameter `Elem`.|  
|[int\_type](../Topic/basic_ios::int_type.md)|Ein Synonym für `Traits::int_type`.|  
|[off\_type](../Topic/basic_ios::off_type.md)|Ein Synonym für `Traits::off_type`.|  
|[pos\_type](../Topic/basic_ios::pos_type.md)|Ein Synonym für `Traits::pos_type`.|  
|[traits\_type](../Topic/basic_ios::traits_type.md)|Ein Synonym für den Vorlagenparameter `Traits`.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[bad](../Topic/basic_ios::bad.md)|Kennzeichnet einen Verlust der Integrität des Streampuffers.|  
|[nicht aktiviert](../Topic/basic_ios::clear.md)|Löscht alle Fehlerflags.|  
|[copyfmt](../Topic/basic_ios::copyfmt.md)|Kopiert Flags aus einem Stream in einen anderen.|  
|[eof](../Topic/basic_ios::eof.md)|Gibt an, dass das Ende eines Streams erreicht wurde.|  
|[Ausnahmen](../Topic/basic_ios::exceptions.md)|Gibt an, welche Ausnahmen vom Datenstrom ausgelöst werden.|  
|[fail](../Topic/basic_ios::fail.md)|Kennzeichnet einen Fehler beim Extrahieren eines gültigen Felds aus einem Stream.|  
|[fill](../Topic/basic_ios::fill.md)|Gibt das Zeichen an oder zurück, das verwendet wird, wenn der Text nicht so breit ist wie der Stream.|  
|[good](../Topic/basic_ios::good.md)|Gibt an, dass der Stream in einem guten Zustand ist.|  
|[imbue](../Topic/basic_ios::imbue.md)|Ändert das Gebietsschema.|  
|[init](../Topic/basic_ios::init.md)|Wird von `basic_ios`\-Konstruktoren aufgerufen.|  
|[move](../Topic/basic_ios::move.md)|Verschiebt alle Werte, mit Ausnahme des Zeigers auf den Streampuffer, aus dem Parameter in das aktuelle Objekt.|  
|[narrow](../Topic/basic_ios::narrow.md)|Sucht das entsprechende Zeichen zu einem angegebenen `char_type`.|  
|[rdbuf](../Topic/basic_ios::rdbuf.md)|Leitet einen Stream in den angegebenen Puffer weiter.|  
|[rdstate](../Topic/basic_ios::rdstate.md)|Liest den Status der Bits für Flags.|  
|[set\_rdbuf](../Topic/basic_ios::set_rdbuf.md)|Weist einen Streampuffer zu, der der Lesepuffer für dieses Streamobjekt sein soll.|  
|[setstate](../Topic/basic_ios::setstate.md)|Legt zusätzliche Flags fest.|  
|[swap](../Topic/basic_ios::swap.md)|Tauscht die Werte in diesem `basic_ios`\-Objekt gegen die Werte eines anderen `basic_ios`\-Objekts aus.  Die Zeiger auf die Streampuffer werden nicht ausgetauscht.|  
|[tie](../Topic/basic_ios::tie.md)|Stellt sicher, dass ein Stream vor einem anderen Stream verarbeitet wird.|  
|[widen](../Topic/basic_ios::widen.md)|Sucht den entsprechenden `char_type` zu einem angegebenen Zeichen.|  
  
### Operatoren  
  
|||  
|-|-|  
|[explicit operator bool](../Topic/basic_ios::operator%20bool.md)|Ermöglicht es, ein `basic_ios`\-Objekt als ein `bool`\-Objekt zu verwenden.  Die automatische Typkonvertierung wird deaktiviert, um häufig vorkommende unbeabsichtigte Nebeneffekte zu verhindern.|  
|[operator void \*](../Topic/basic_ios::operator%20void%20*.md)|Gibt an, ob der Stream weiterhin brauchbar ist.|  
|[operator \!](../Topic/basic_ios::operator!.md)|Gibt an, ob der Stream nicht unbrauchbar ist.|  
  
## Anforderungen  
 **Header:** \<ios\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)