---
title: "time_get-Klasse"
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
  - "std.time_get"
  - "xloctime/std::time_get"
  - "time_get"
  - "std::time_get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "time_get-Klasse"
ms.assetid: 869d5f5b-dbab-4628-8333-bdea7e272023
caps.latest.revision: 21
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# time_get-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um Konvertierungen von Sequenzen des Typs `CharType` in Zeitwerte zu steuern.  
  
## Syntax  
  
```  
template <  
   class CharType,  
   class InputIterator = istreambuf_iterator<CharType>  
> class time_get : public time_base;  
```  
  
#### Parameter  
 `CharType`  
 Der Typ, der innerhalb eines Programms verwendet wird, um Zeichen zu codieren.  
  
 `InputIterator`  
 Der Iterator, von dem die Zeitwerte gelesen werden.  
  
## Hinweise  
 Wie bei jedem Gebietsschemafacet hat die statische Objekt\-ID einen anfänglichen gespeicherten Wert von NULL.  Beim ersten Versuch, auf den gespeicherten Wert zuzugreifen, wird ein eindeutiger positiver Wert in **ID** gespeichert.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[time\_get](../Topic/time_get::time_get.md)|Der Konstruktor für Objekte des Typs `time_get`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/time_get::char_type.md)|Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.|  
|[iter\_type](../Topic/time_get::iter_type.md)|Ein Typ, der einen Eingabeiterator beschreibt.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[date\_order](../Topic/time_get::date_order.md)|Gibt die Datumsreihenfolge zurück, die von einem Facet verwendet wird.|  
|[do\_date\_order](../Topic/time_get::do_date_order.md)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um die von einem Facet verwendete Datumsreihenfolge zurückzugeben.|  
|[do\_get](../Topic/time_get::do_get.md)|Liest und konvertiert Zeichendaten in einen Zeitwert.|  
|[do\_get\_date](../Topic/time_get::do_get_date.md)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine Zeichenfolge als das Datum zu analysieren, das vom `x`\-Bezeichner für `strftime` erstellt wurde.|  
|[do\_get\_monthname](../Topic/time_get::do_get_monthname.md)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine Zeichenfolge als Name des Monats zu analysieren.|  
|[do\_get\_time](../Topic/time_get::do_get_time.md)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine Zeichenfolge als das Datum zu analysieren, das vom `X`\-Bezeichner für `strftime` erstellt wurde.|  
|[do\_get\_weekday](../Topic/time_get::do_get_weekday.md)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine Zeichenfolge als Name des Wochentags zu analysieren.|  
|[do\_get\_year](../Topic/time_get::do_get_year.md)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine Zeichenfolge als Name des Jahres zu analysieren.|  
|[get](../Topic/time_get::get.md)|Liest aus einer Zeichendatenquelle und konvertiert die Daten in eine Zeit, die in einer Zeitstruktur gespeichert wird.|  
|[get\_date](../Topic/time_get::get_date.md)|Analysiert eine Zeichenfolge als das Datum, das vom `x`\-Bezeichner für `strftime` erzeugt wird.|  
|[get\_monthname](../Topic/time_get::get_monthname.md)|Analysiert eine Zeichenfolge als Name des Monats.|  
|[get\_time](../Topic/time_get::get_time.md)|Analysiert eine Zeichenfolge als das Datum, das vom `X`\-Bezeichner für `strftime` erzeugt wird.|  
|[get\_weekday](../Topic/time_get::get_weekday.md)|Analysiert eine Zeichenfolge als Name des Wochentags.|  
|[get\_year](../Topic/time_get::get_year.md)|Analysiert eine Zeichenfolge als Name des Jahres.|  
  
## Anforderungen  
 **Header:** \<Gebietsschema\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<locale\>](../standard-library/locale.md)   
 [time\_base\-Klasse](../standard-library/time-base-class.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)