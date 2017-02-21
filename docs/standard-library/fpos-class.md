---
title: "fpos-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.fpos"
  - "std::fpos"
  - "iosfwd/std::fpos"
  - "fpos"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fpos-Klasse"
  - "fpos-Klasse, Infos über die fpos-Klasse"
ms.assetid: ffd0827c-fa34-47f4-b10e-5cb707fcde47
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# fpos-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das alle Informationen, die zum Wiederherstellen eines beliebigen Dateipositionsindikators innerhalb eines Streams erforderlich sind, speichern kann.  Ein Objekt der Klasse fpos\<**St**\> speichert effektiv mindestens zwei Memberobjekte:  
  
-   Ein Byteoffset vom Typ [streamoff](../Topic/streamoff.md).  
  
-   Ein Konvertierungzustand, der für ein Objekt der Klasse basic\_filebuf vom Typ **St** verwendet wird, in der Regel `mbstate_t`.  
  
 Es kann auch eine beliebige Dateiposition speichern, die von einem Objekt der Klasse [basic\_filebuf](../standard-library/basic-filebuf-class.md) vom Typ `fpos_t` verwendet werden kann.  In einer Umgebung mit begrenzter Dateigröße werden `streamoff` und `fpos_t` jedoch manchmal synonym verwendet.  In einer Umgebung ohne Streams, mit zustandsabhängiger Codierung, wird `mbstate_t` möglicherweise nicht verwendet.  Daher kann die Anzahl der gespeicherten Memberobjekte variieren.  
  
## Syntax  
  
```  
  
     template <class   
     Statetype  
     >  
class fpos  
```  
  
#### Parameter  
 *Statetype*  
 Zustandsinformationen.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[fpos](../Topic/fpos::fpos.md)|Erstellt ein Objekt, das Informationen zu einer Position \(Offset\) in einem Stream enthält.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[seekpos](../Topic/fpos::seekpos.md)|Wird nur intern von der C\+\+\-Standardbibliothek verwendet.  Rufen Sie diese Methode nicht aus Ihrem Code auf.|  
|[\-Zustand](../Topic/fpos::state.md)|Legt den Konvertierungszustand fest oder gibt ihn zurück.|  
  
### Operatoren  
  
|||  
|-|-|  
|[Operator\!\=](../Topic/fpos::operator!=.md)|Testet Dateipositionsindikatoren auf Ungleichheit.|  
|[operator\+](../Topic/fpos::operator+.md)|Erhöht einen Dateipositionsindikator.|  
|[operator \+\=](../Topic/fpos::operator+=.md)|Erhöht einen Dateipositionsindikator.|  
|[operator\-](../Topic/fpos::operator-.md)|Verringert einen Dateipositionsindikator.|  
|[Operator\-\=](../Topic/fpos::operator-=.md)|Verringert einen Dateipositionsindikator.|  
|[Operator\=\=](../Topic/fpos::operator==.md)|Testet Dateipositionsindikatoren auf Gleichheit.|  
|[operator streamoff](../Topic/fpos::operator%20streamoff.md)|Wandelt ein Objekt vom Typ `fpos` in ein Objekt vom Typ `streamoff` um.|  
  
## Anforderungen  
 **Header:** \<ios\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)