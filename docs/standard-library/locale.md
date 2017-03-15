---
title: "&lt;locale&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<locale>"
  - "std.<locale>"
  - "locale/std::<locale>"
  - "std::<locale>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "locale-Header"
ms.assetid: ca56f9d2-7128-44da-8df1-f4c78c17fbf2
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# &lt;locale&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert Vorlagenklassen und Funktionen, die von C\+\+\-Programmen verwendet werden können, um verschiedene kulturelle Konventionen bezüglich der Darstellung und der Formatierung von numerischen, monetären und kalendarischen Daten, einschließlich Internationalisierungsunterstützung für Zeichenklassifizierung und Zeichenfolgensortierreihenfolge, zu kapseln und zu bearbeiten.  
  
## Syntax  
  
```  
  
#include <locale>  
  
```  
  
### Funktionen  
  
|||  
|-|-|  
|[has\_facet](../Topic/has_facet.md)|Testet, ob ein bestimmtes Facet in einem angegebenen Gebietsschema gespeichert wird.|  
|[isalnum](../Topic/isalnum.md)|Testet, ob ein Element in einem Gebietsschema ein alphabetisches oder ein numerisches Zeichen ist.|  
|[isalpha](../Topic/isalpha.md)|Testet, ob ein Element in einem Gebietsschema ein alphabetisches Zeichen ist.|  
|[iscntrl](../Topic/iscntrl.md)|Testet, ob ein Element in einem Gebietsschema ein Steuerzeichen ist.|  
|[isdigit](../Topic/isdigit.md)|Testet, ob ein Element in einem Gebietsschema ein numerisches Zeichen ist.|  
|[isgraph](../Topic/isgraph.md)|Testet, ob ein Element in einem Gebietsschema ein alphanumerisches Zeichen oder ein Interpunktionszeichen ist.|  
|[islower](../Topic/islower.md)|Testet, ob ein Element in einem Gebietsschema kleingeschrieben ist.|  
|[isprint](../Topic/isprint.md)|Testet, ob ein Element in einem Gebietsschema ein druckbares Zeichen ist.|  
|[ispunct](../Topic/ispunct.md)|Testet, ob ein Element in einem Gebietsschema ein Interpunktionszeichen ist.|  
|[isspace](../Topic/isspace.md)|Testet, ob ein Element in einem Gebietsschema ein Leerzeichen ist.|  
|[isupper](../Topic/isupper.md)|Testet, ob ein Element in einem Gebietsschema großgeschrieben ist.|  
|[isxdigit](../Topic/isxdigit.md)|Testet, ob ein Element in einem Gebietsschema ein Zeichen ist, mit dem eine Hexadezimalzahl dargestellt wird.|  
|[tolower](../Topic/tolower.md)|Konvertiert ein Zeichen in einen Kleinbuchstaben.|  
|[toupper](../Topic/toupper.md)|Konvertiert ein Zeichen in einen Großbuchstaben.|  
|[use\_facet](../Topic/use_facet.md)|Gibt einen Verweis auf ein Facet eines angegebenen Typs zurück, der in einem Gebietsschema gespeichert wird.|  
  
### Klassen  
  
|||  
|-|-|  
|[codecvt](../standard-library/codecvt-class.md)|Eine Vorlagenklasse, die ein Facet bereitstellt, das zum Konvertieren zwischen internen und externen Zeichencodierungen verwendet wird.|  
|[codecvt\_base](../standard-library/codecvt-base-class.md)|Eine Basisklasse für die codecvt\-Klasse, die verwendet wird, um einen Enumerationstyp zu definieren, der als **Ergebnis** gekennzeichnet ist. Dieser wird als Rückgabetyp für die Facetmemberfunktionen verwendet, um das Ergebnis einer Konvertierung anzugeben.|  
|[codecvt\_byname](../standard-library/codecvt-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als Sortierungsfacet eines angegebenen Gebietsschemas dienen kann, sodass für einen kulturellen Bereich spezifische Informationen über Konvertierungen abgerufen werden können.|  
|[collate](../standard-library/collate-class.md)|Eine Sortierungsvorlagenklasse, die ein Facet bereitstellt, das Konventionen zum Sortieren von Zeichenfolgen verarbeitet.|  
|[collate\_byname](../standard-library/collate-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als Sortierungsfacet eines angegebenen Gebietsschemas dienen kann, sodass für einen kulturellen Bereich spezifische Informationen über Konventionen zum Sortieren von Zeichenfolgen abgerufen werden können.|  
|[ctype](../standard-library/ctype-class.md)|Eine Vorlagenklasse, die ein Facet bereitstellt, das verwendet wird, um Zeichen zu klassifizieren, zwischen Groß\- und Kleinbuchstaben zu wechseln und zwischen dem systemeigenen Zeichensatz und dem vom Gebietsschema verwendeten Zeichensatz zu konvertieren.|  
|[ctype\<char\>](../standard-library/ctype-char-class.md)|Eine Klasse, die eine explizite Spezialisierung der Vorlagenklasse **ctype\<CharType**\> für den Typ `char` darstellt und ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um verschiedene Eigenschaften eines Zeichens vom Typ `char` zu kennzeichnen.|  
|[ctype\_base](../standard-library/ctype-base-class.md)|Eine Basisklasse für die ctype\-Klasse, die verwendet wird, um die Enumerationstypen zu definieren, mit denen Zeichen entweder einzeln oder innerhalb eines gesamten Bereichs klassifiziert oder getestet werden.|  
|[ctype\_byname](../standard-library/ctype-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als ctype\-Facet eines angegebenen Gebietsschemas dienen kann und die Klassifizierung von Zeichen sowie die Konvertierung von Zeichen zwischen Groß\-\/Kleinschreibung und zwischen systemeigenen und gebietsschemaspezifischen Zeichensätzen ermöglicht.|  
|[Gebietsschema](../standard-library/locale-class.md)|Eine Klasse, die ein Gebietsschemaobjekt beschreibt, das kulturspezifische Informationen als einen Satz von Facets kapselt, die zusammen eine bestimmte lokalisierte Umgebung definieren.|  
|[Meldungen](../standard-library/messages-class.md)|Eine Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um lokalisierte Meldungen aus einem Katalog von internationalisierten Meldungen für ein bestimmtes Gebietsschema abzurufen.|  
|[messages\_base](../standard-library/messages-base-class.md)|Eine Basisklasse, die einen `int`\-Typ für den Katalog von Meldungen beschreibt.|  
|[messages\_byname](../standard-library/messages-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als Meldungsfacet eines angegebenen Gebietsschemas dienen kann und das Abrufen von lokalisierten Meldungen ermöglicht.|  
|[money\_base](../standard-library/money-base-class.md)|Eine Basisklasse für die ctype\-Klasse, die verwendet wird, um die Enumerationstypen zu definieren, mit denen Zeichen entweder einzeln oder innerhalb eines gesamten Bereichs klassifiziert oder getestet werden.|  
|[money\_get](../standard-library/money-get-class.md)|Eine Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um Konvertierungen von Sequenzen vom Typ **CharType** in monetäre Werte zu steuern.|  
|[money\_put](../standard-library/money-put-class.md)|Eine Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um Konvertierungen von monetären Werten in Sequenzen vom Typ **CharType** zu steuern.|  
|[moneypunct](../standard-library/moneypunct-class.md)|Eine Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um die Sequenzen vom Typ **CharType** zu beschreiben, die verwendet werden, um ein monetäres Eingabefeld oder ein monetäres Ausgabefeld darzustellen.|  
|[moneypunct\_byname](../standard-library/moneypunct-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als moneypunct\-Facet eines angegebenen Gebietsschemas dienen kann und die Formatierung von monetären Ein\- und Ausgabefeldern ermöglicht.|  
|[num\_get](../standard-library/num-get-class.md)|Eine Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um Konvertierungen von Sequenzen vom Typ **CharType** in numerische Werte zu steuern.|  
|[num\_put](../standard-library/num-put-class.md)|Eine Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um Konvertierungen von numerischen Werten in Sequenzen vom Typ **CharType** zu steuern.|  
|[numpunct](../standard-library/numpunct-class.md)|Eine Vorlagenklasse, die ein Objekt beschreibt, das als lokales Facet dienen kann, um die Sequenzen vom Typ **CharType** zu beschreiben, mit denen Informationen zur Formatierung und Interpunktion von numerischen und booleschen Ausdrücken dargestellt werden.|  
|[numpunct\_byname](../standard-library/numpunct-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als moneypunct\-Facet eines angegebenen Gebietsschemas dienen kann und die Formatierung und Interpunktion von numerischen und booleschen Ausdrücken ermöglicht.|  
|[time\_base](../standard-library/time-base-class.md)|Eine Klasse, die als Basisklasse für Facets der time\_get\-Vorlagenklasse dient und nur den Enumerationstyp "dateorder" und mehrere Konstanten dieses Typs definiert.|  
|[time\_get](../standard-library/time-get-class.md)|Eine Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um Konvertierungen von Sequenzen vom Typ **CharType** in Zeitwerte zu steuern.|  
|[time\_get\_byname](../standard-library/time-get-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet vom Typ time\_get\<**CharType**, **InputIterator**\> dienen kann.|  
|[time\_put](../standard-library/time-put-class.md)|Eine Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um Konvertierungen von Zeitwerten in Sequenzen vom Typ **CharType** zu steuern.|  
|[time\_put\_byname](../standard-library/time-put-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet vom Typ `time_put`\<**CharType**, **OutputIterator**\> dienen kann.|  
|[wbuffer\_convert\-Klasse](../standard-library/wbuffer-convert-class.md)|Beschreibt einen Streampuffer, der die Übertragung von Elementen in einen bzw. aus einem Streampuffer steuert.|  
|[wstring\_convert\-Klasse](../standard-library/wstring-convert-class.md)|Eine Vorlagenklasse, die Konvertierungen zwischen einer breiten Zeichenfolge und einer Bytezeichenfolge durchführt.|  
  
## Siehe auch  
 [Codepages](../c-runtime-library/code-pages.md)   
 [Gebietsschema\-Namen, Sprachen und Zeichenfolgen für Länder und Regionen](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)