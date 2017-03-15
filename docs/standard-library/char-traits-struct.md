---
title: "char_traits-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::char_traits"
  - "std.char_traits"
  - "iosfwd/std::char_traits"
  - "char_traits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits-Klasse"
  - "char_traits-Struktur"
ms.assetid: 568e59f0-4521-4207-9223-9dcf6a16d620
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# char_traits-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die char\_traits\-Struktur beschreibt die Attribute, die einem Zeichen zugeordnet sind.  
  
## Syntax  
  
```  
template <  
   class CharType  
> struct char_traits;  
```  
  
#### Parameter  
 `CharType`  
 Der Datentyp des Elements.  
  
## Hinweise  
 Die Vorlagenstruktur beschreibt verschiedene Zeichenmerkmale für den Typ **CharType**.  Die Vorlagenklasse [basic\_string](../standard-library/basic-string-class.md) sowie mehrere iostream\-Vorlagenklassen, einschließlich [basic\_ios](../standard-library/basic-ios-class.md), verwenden diese Informationen zum Bearbeiten von Elementen des Typs **CharType**.  Ein solcher Elementtyp darf weder explizite Erstellung noch explizite Zerstörung erfordern.  Er muss einen Standardkonstruktor, einen Kopierkonstruktor und einen Zuweisungsoperator mit der erwarteten Semantik bereitstellen.  Eine bitweise Kopie muss dieselbe Auswirkung wie eine Zuweisung haben.  Keine der Memberfunktionen der char\_traits\-Struktur kann Ausnahmen auslösen.  
  
### TypeDefs  
  
|||  
|-|-|  
|[char\_type](../Topic/char_traits::char_type.md)|Ein Typ von Zeichen.|  
|[int\_type](../Topic/char_traits::int_type.md)|Ein ganzzahliger Typ, der ein Zeichen des Typs `char_type` oder ein Dateiendezeichen \(End\-of\-File, EOF\) darstellen kann.|  
|[off\_type](../Topic/char_traits::off_type.md)|Ein ganzzahliger Typ, der Offsets zwischen Positionen in einem Stream darstellen kann.|  
|[pos\_type](../Topic/char_traits::pos_type.md)|Ein ganzzahliger Typ, der Positionen in einem Stream darstellen kann.|  
|[state\_type](../Topic/char_traits::state_type.md)|Ein Typ, der den Konvertierungsstatus für Multibytezeichen in einem Stream darstellt.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[assign](../Topic/char_traits::assign.md)|Weist den Wert eines Zeichens einem anderen zu.|  
|[compare](../Topic/char_traits::compare.md)|Vergleicht zwei Zeichenfolgen bis zu einer angegebenen Anzahl von Zeichen.|  
|[copy](../Topic/char_traits::copy.md)|Kopiert eine angegebene Anzahl von Zeichen aus einer Zeichenfolge in eine andere.  Veraltet.  Verwenden Sie stattdessen [char\_traits::\_Copy\_s](../Topic/char_traits::_Copy_s.md).|  
|[\_Copy\_s](../Topic/char_traits::_Copy_s.md)|Kopiert eine angegebene Anzahl von Zeichen aus einer Zeichenfolge in eine andere.|  
|[eof](../Topic/char_traits::eof.md)|Gibt das Zeichen für Dateiende \(End\-of\-File, EOF\) zurück.|  
|[eq](../Topic/char_traits::eq.md)|Überprüft, ob zwei `char_type`\-Zeichen gleich sind.|  
|[eq\_int\_type](../Topic/char_traits::eq_int_type.md)|Überprüft, ob zwei Zeichen, die als `int_type`s angegeben sind, gleich sind.|  
|[find](../Topic/char_traits::find.md)|Sucht nach dem ersten Vorkommen eines angegebenen Zeichens in einem Bereich von Zeichen.|  
|[length](../Topic/char_traits::length.md)|Gibt die Länge einer Zeichenfolge zurück.|  
|[lt](../Topic/char_traits::lt.md)|Überprüft, ob ein Zeichen kleiner als ein anderes ist.|  
|[move](../Topic/char_traits::move.md)|Kopiert eine angegebene Anzahl von Zeichen in einer Sequenz in eine andere, möglicherweise überlappende, Sequenz.  Veraltet.  Verwenden Sie stattdessen [char\_traits::\_Move\_s](../Topic/char_traits::_Move_s.md).|  
|[\_Move\_s](../Topic/char_traits::_Move_s.md)|Kopiert eine angegebene Anzahl von Zeichen in einer Sequenz in eine andere, möglicherweise überlappende, Sequenz.|  
|[not\_eof](../Topic/char_traits::not_eof.md)|Überprüft, ob ein Zeichen das Zeichen für Dateiende \(End\-of\-File, EOF\) ist.|  
|[to\_char\_type](../Topic/char_traits::to_char_type.md)|Konvertiert ein `int_type`\-Zeichen in das entsprechende `char_type`\-Zeichen und gibt das Ergebnis zurück.|  
|[to\_int\_type](../Topic/char_traits::to_int_type.md)|Konvertiert ein `char_type`\-Zeichen in das entsprechende `int_type`\-Zeichen und gibt das Ergebnis zurück.|  
  
## Anforderungen  
 **Header:** \<string\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)