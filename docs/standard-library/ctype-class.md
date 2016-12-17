---
title: "ctype-Klasse"
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
  - "ctype"
  - "std::ctype"
  - "std.ctype"
  - "CType"
  - "xlocale/std::ctype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ctype-Klasse"
ms.assetid: 3627154c-49d9-47b5-b28f-5bbedee38e3b
caps.latest.revision: 19
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# ctype-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Klasse, die ein Facet bereitstellt, das verwendet wird, um Zeichen zu klassifizieren, zwischen Groß\- und Kleinbuchstaben zu wechseln und zwischen dem systemeigenen Zeichensatz und dem vom Gebietsschema verwendeten Zeichensatz zu konvertieren.  
  
## Syntax  
  
```  
template <class CharType>  
   class ctype : public ctype_base;  
```  
  
#### Parameter  
 `CharType`  
 Der Typ, der innerhalb eines Programms verwendet wird, um Zeichen zu codieren.  
  
## Hinweise  
 Wie bei jedem Gebietsschemafacet hat die statische Objekt\-ID einen anfänglichen gespeicherten Wert von NULL.  Beim ersten Versuch, auf den gespeicherten Wert zuzugreifen, wird ein eindeutiger positiver Wert in **ID** gespeichert. Für Klassifizierungskriterien wird ein geschachtelter Bitmaskentyp in der ctype\_base\-Basisklasse bereitgestellt.  
  
 Die C\+\+\-Standardbibliothek definiert zwei explizite Spezialisierungen dieser Vorlagenklasse:  
  
-   [ctype](#vclrf_locale_ctype_class)\<`char`\>, eine explizite Spezialisierung, deren Unterschiede gesondert beschrieben werden.  
  
-   **ctype**\<`wchar_t`\>, die Elemente als Breitzeichen behandelt.  
  
 Andere Spezialisierungen der Vorlagenklasse **ctype**\<**CharType**\>:  
  
-   Konvertiert einen Wert ***ch*** vom Typ **CharType** in einen Wert vom Typ `char` mit dem Ausdruck \(`char`\)**ch**.  
  
-   Konvertiert einen Wert ***byte*** vom Typ `char` in einen Wert vom Typ **CharType** mit dem Ausdruck **CharType** \(**byte**\).  
  
 Alle anderen Vorgänge werden für `char`\-Werte auf die gleiche Weise wie für die explizite Spezialisierung **ctype**\<`char`\> ausgeführt.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[ctype](../Topic/ctype::ctype.md)|Konstruktor für Objekte der Klasse `ctype`, die als Gebietsschemafacets für Zeichen dienen.|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/ctype::char_type.md)|Ein Typ, der ein Zeichen beschreibt, das von einem Gebietsschema verwendet wird.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[do\_is](../Topic/ctype::do_is.md)|Eine virtuelle Funktion, die aufgerufen wird, um zu testen, ob ein einzelnes Zeichen über ein bestimmtes Attribut verfügt, oder die Attribute jedes Zeichens in einem Bereich klassifiziert und in einem Array speichert.|  
|[do\_narrow](../Topic/ctype::do_narrow.md)|Eine virtuelle Funktion, die aufgerufen wird, um ein Zeichen vom Typ `CharType`, das von einem Gebietsschema verwendet wird, in das entsprechende Zeichen vom Typ `char` im systemeigenen Zeichensatz zu konvertieren.|  
|[do\_scan\_is](../Topic/ctype::do_scan_is.md)|Eine virtuelle Funktion, die aufgerufen wird, um das erste Zeichen in einem Bereich zu suchen, der einer angegebenen Maske entspricht.|  
|[do\_scan\_not](../Topic/ctype::do_scan_not.md)|Eine virtuelle Funktion, die aufgerufen wird, um das erste Zeichen in einem Bereich zu suchen, der einer angegebenen Maske nicht entspricht.|  
|[do\_tolower](../Topic/ctype::do_tolower.md)|Eine virtuelle Funktion, die aufgerufen wird, um ein Zeichen oder einen Zeichenbereich in Kleinbuchstaben umzuwandeln.|  
|[do\_toupper](../Topic/ctype::do_toupper.md)|Eine virtuelle Funktion, die aufgerufen wird, um ein Zeichen oder einen Zeichenbereich in Großbuchstaben umzuwandeln.|  
|[do\_widen](../Topic/ctype::do_widen.md)|Eine virtuelle Funktion, die aufgerufen wird, um ein Zeichen vom Typ `char` im systemeigenen Zeichensatz in das entsprechende Zeichen vom Typ `CharType`, das von einem Gebietsschema verwendet wird, zu konvertieren.|  
|[is](../Topic/ctype::is.md)|Testet, ob ein einzelnes Zeichen über ein bestimmtes Attribut verfügt, oder klassifiziert die Attribute jedes Zeichens in einem Bereich und speichert sie in einem Array.|  
|[narrow](../Topic/ctype::narrow.md)|Konvertiert ein Zeichen vom Typ `CharType`, das von einem Gebietsschema verwendet wird, in das entsprechende Zeichen vom Typ "char" im systemeigenen Zeichensatz.|  
|[scan\_is](../Topic/ctype::scan_is.md)|Sucht das erste Zeichen in einem Bereich, der einer bestimmten Maske entspricht.|  
|[scan\_not](../Topic/ctype::scan_not.md)|Sucht das erste Zeichen in einem Bereich, der einer bestimmten Maske nicht entspricht.|  
|[tolower](../Topic/ctype::tolower.md)|Konvertiert ein Zeichen oder einen Zeichenbereich in Kleinbuchstaben.|  
|[toupper](../Topic/ctype::toupper.md)|Konvertiert ein Zeichen oder einen Zeichenbereich in Großbuchstaben.|  
|[widen](../Topic/ctype::widen.md)|Konvertiert ein Zeichen vom Typ `char` im systemeigenen Zeichensatz in das entsprechende Zeichen vom Typ `CharType`, das von einem Gebietsschema verwendet wird.|  
  
## Anforderungen  
 **Header:** \<Gebietsschema\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<locale\>](../standard-library/locale.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)