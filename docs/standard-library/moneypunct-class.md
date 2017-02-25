---
title: "moneypunct-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "moneypunct"
  - "std.moneypunct"
  - "xlocmon/std::moneypunct"
  - "std::moneypunct"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "moneypunct-Klasse"
ms.assetid: cf2650da-3e6f-491c-95d5-23e57f582ee6
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# moneypunct-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das als Gebietsschemafacet dienen kann, um die Sequenzen vom Typ `CharType` zu beschreiben, die verwendet werden, um ein monetäres Eingabefeld oder ein monetäres Ausgabefeld darzustellen.  Wenn der Vorlagenparameter `Intl` `true` ist, werden internationale Konventionen beachtet.  
  
## Syntax  
  
```  
template<class CharType, bool Intl>   
   class moneypunct;  
```  
  
#### Parameter  
 `CharType`  
 Der Typ, der innerhalb eines Programms verwendet wird, um Zeichen zu codieren.  
  
 `Intl`  
 Ein Flag, das festlegt, ob internationale Konventionen beachtet werden sollen.  
  
## Hinweise  
 Wie bei jedem Gebietsschemafacet hat die statische Objekt\-ID einen anfänglichen gespeicherten Wert von NULL.  Beim ersten Versuch, auf den gespeicherten Wert zuzugreifen, wird ein eindeutiger positiver Wert in **ID** gespeichert.  
  
 Das konstante statische Objekt "intl" speichert den Wert des Vorlagenparameters **Intl**.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[moneypunct](../Topic/moneypunct::moneypunct.md)|Konstruktor von Objekten des Typs `moneypunct`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/moneypunct::char_type.md)|Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.|  
|[string\_type](../Topic/moneypunct::string_type.md)|Ein Typ, der eine Zeichenfolge beschreibt, die Zeichen vom Typ `CharType` enthält.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[curr\_symbol](../Topic/moneypunct::curr_symbol.md)|Gibt eine gebietsschemaspezifische Sequenz von Elementen zurück, die als Währungssymbol verwendet werden soll.|  
|[decimal\_point](../Topic/moneypunct::decimal_point.md)|Gibt eine gebietsschemaspezifische Sequenz von Elementen zurück, die als Dezimalzeichen verwendet werden soll.|  
|[do\_curr\_symbol](../Topic/moneypunct::do_curr_symbol.md)|Eine geschützte virtuelle Memberfunktion, die eine gebietsschemaspezifische Sequenz von Elementen zurückgibt, die als Währungssymbol verwendet werden soll.|  
|[do\_decimal\_point](../Topic/moneypunct::do_decimal_point.md)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine gebietsschemaspezifische Sequenz von Elementen zurückzugeben, die als Dezimaltrennzeichen verwendet werden soll.|  
|[do\_frac\_digits](../Topic/moneypunct::do_frac_digits.md)|Die geschützte virtuelle Memberfunktion gibt eine gebietsschemaspezifische Anzahl von Ziffern zurück, die rechts vom Dezimaltrennzeichen angezeigt werden sollen.|  
|[do\_grouping](../Topic/moneypunct::do_grouping.md)|Die geschützte virtuelle Memberfunktion gibt eine gebietsschemaspezifische Regel zur Bestimmung zurück, wie Ziffern auf der linken Seite eines Dezimaltrennzeichens gruppiert werden.|  
|[do\_neg\_format](../Topic/moneypunct::do_neg_format.md)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine gebietsschemaspezifische Regel zur Formatierung von Ausgaben mit negativen Zahlen zurückzugeben.|  
|[do\_negative\_sign](../Topic/moneypunct::do_negative_sign.md)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine gebietsschemaspezifische Sequenz von Elementen zurückzugeben, die als Minuszeichen verwendet werden soll.|  
|[do\_pos\_format](../Topic/moneypunct::do_pos_format.md)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine gebietsschemaspezifische Regel zur Formatierung von Ausgaben mit positiven Zahlen zurückzugeben.|  
|[do\_positive\_sign](../Topic/moneypunct::do_positive_sign.md)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine gebietsschemaspezifische Sequenz von Elementen zurückzugeben, die als Pluszeichen verwendet werden soll.|  
|[do\_thousands\_sep](../Topic/moneypunct::do_thousands_sep.md)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine gebietsschemaspezifische Sequenz von Elementen zurückzugeben, die als Tausendertrennzeichen verwendet werden soll.|  
|[frac\_digits](../Topic/moneypunct::frac_digits.md)|Gibt eine gebietsschemaspezifische Anzahl von Ziffern zurück, die auf der rechten Seite eines Dezimaltrennzeichens angezeigt werden sollen.|  
|[Gruppieren](../Topic/moneypunct::grouping.md)|Gibt eine gebietsschemaspezifische Regel zur Bestimmung zurück, wie Ziffern auf der linken Seite eines Dezimaltrennzeichens gruppiert werden sollen.|  
|[neg\_format](../Topic/moneypunct::neg_format.md)|Gibt eine gebietsschemaspezifische Regel zur Formatierung von Ausgaben mit negativen Zahlen zurück.|  
|[negative\_sign](../Topic/moneypunct::negative_sign.md)|Gibt eine gebietsschemaspezifische Sequenz von Elementen zurück, die als Minuszeichen verwendet werden soll.|  
|[pos\_format](../Topic/moneypunct::pos_format.md)|Gibt eine gebietsschemaspezifische Regel zur Formatierung von Ausgaben mit positiven Zahlen zurück.|  
|[positive\_sign](../Topic/moneypunct::positive_sign.md)|Gibt eine gebietsschemaspezifische Sequenz von Elementen zurück, die als Pluszeichen verwendet werden soll.|  
|[thousands\_sep](../Topic/moneypunct::thousands_sep.md)|Gibt eine gebietsschemaspezifische Sequenz von Elementen zurück, die als Tausendertrennzeichen verwendet werden soll.|  
  
## Anforderungen  
 **Header:** \<Gebietsschema\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<locale\>](../standard-library/locale.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)