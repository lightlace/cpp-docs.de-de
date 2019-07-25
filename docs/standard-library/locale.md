---
title: '&lt;locale&gt;'
ms.date: 11/04/2016
f1_keywords:
- <locale>
- locale/std::<locale>
- std::<locale>
helpviewer_keywords:
- locale header
ms.assetid: ca56f9d2-7128-44da-8df1-f4c78c17fbf2
ms.openlocfilehash: 708184a6a6a443456f0d70f57b6be17b281ac4f5
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453916"
---
# <a name="ltlocalegt"></a>&lt;locale&gt;

Definiert Vorlagenklassen und Funktionen, die von C++-Programmen verwendet werden können, um verschiedene kulturelle Konventionen bezüglich der Darstellung und der Formatierung von numerischen, monetären und kalendarischen Daten, einschließlich Internationalisierungsunterstützung für Zeichenklassifizierung und Zeichenfolgensortierreihenfolge, zu kapseln und zu bearbeiten.

## <a name="syntax"></a>Syntax

```cpp
#include <locale>
```

### <a name="functions"></a>Funktionen

|Funktion|Beschreibung|
|-|-|
|[has_facet](../standard-library/locale-functions.md#has_facet)|Testet, ob ein bestimmtes Facet in einem angegebenen Gebietsschema gespeichert wird.|
|[isalnum](../standard-library/locale-functions.md#isalnum)|Testet, ob ein Element in einem Gebietsschema ein alphabetisches oder ein numerisches Zeichen ist.|
|[isalpha](../standard-library/locale-functions.md#isalpha)|Testet, ob ein Element in einem Gebietsschema ein alphabetisches Zeichen ist.|
|[iscntrl](../standard-library/locale-functions.md#iscntrl)|Testet, ob ein Element in einem Gebietsschema ein Steuerzeichen ist.|
|[isdigit](../standard-library/locale-functions.md#isdigit)|Testet, ob ein Element in einem Gebietsschema ein numerisches Zeichen ist.|
|[isgraph](../standard-library/locale-functions.md#isgraph)|Testet, ob ein Element in einem Gebietsschema ein alphanumerisches Zeichen oder ein Interpunktionszeichen ist.|
|[islower](../standard-library/locale-functions.md#islower)|Testet, ob ein Element in einem Gebietsschema kleingeschrieben ist.|
|[isprint](../standard-library/locale-functions.md#isprint)|Testet, ob ein Element in einem Gebietsschema ein druckbares Zeichen ist.|
|[ispunct](../standard-library/locale-functions.md#ispunct)|Testet, ob ein Element in einem Gebietsschema ein Interpunktionszeichen ist.|
|[isspace](../standard-library/locale-functions.md#isspace)|Testet, ob ein Element in einem Gebietsschema ein Leerzeichen ist.|
|[isupper](../standard-library/locale-functions.md#isupper)|Testet, ob ein Element in einem Gebietsschema großgeschrieben ist.|
|[isxdigit](../standard-library/locale-functions.md#isxdigit)|Testet, ob ein Element in einem Gebietsschema ein Zeichen ist, mit dem eine Hexadezimalzahl dargestellt wird.|
|[tolower](../standard-library/locale-functions.md#tolower)|Konvertiert ein Zeichen in einen Kleinbuchstaben.|
|[toupper](../standard-library/locale-functions.md#toupper)|Konvertiert ein Zeichen in einen Großbuchstaben.|
|[use_facet](../standard-library/locale-functions.md#use_facet)|Gibt einen Verweis auf ein Facet eines angegebenen Typs zurück, der in einem Gebietsschema gespeichert wird.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[codecvt](../standard-library/codecvt-class.md)|Eine Vorlagenklasse, die ein Facet bereitstellt, das zum Konvertieren zwischen internen und externen Zeichencodierungen verwendet wird.|
|[codecvt_base](../standard-library/codecvt-base-class.md)|Eine Basisklasse für die Codecvt-Klasse, die verwendet wird, um einen Enumerationstyp `result`zu definieren, der als bezeichnet wird, der als Rückgabetyp für die facetmember-Funktionen verwendet wird, um das Ergebnis einer Konvertierung anzugeben.|
|[codecvt_byname](../standard-library/codecvt-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als Sortierungsfacet eines angegebenen Gebietsschemas dienen kann, sodass für einen kulturellen Bereich spezifische Informationen über Konvertierungen abgerufen werden können.|
|[collate](../standard-library/collate-class.md)|Eine Sortierungsvorlagenklasse, die ein Facet bereitstellt, das Konventionen zum Sortieren von Zeichenfolgen verarbeitet.|
|[collate_byname](../standard-library/collate-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als Sortierungsfacet eines angegebenen Gebietsschemas dienen kann, sodass für einen kulturellen Bereich spezifische Informationen über Konventionen zum Sortieren von Zeichenfolgen abgerufen werden können.|
|[ctype](../standard-library/ctype-class.md)|Eine Vorlagenklasse, die ein Facet bereitstellt, das verwendet wird, um Zeichen zu klassifizieren, zwischen Groß- und Kleinbuchstaben zu wechseln und zwischen dem systemeigenen Zeichensatz und dem vom Gebietsschema verwendeten Zeichensatz zu konvertieren.|
|[ctype\<char>](../standard-library/ctype-char-class.md)|Eine Klasse, die eine explizite Spezialisierung der Vorlagen Klasse `ctype<CharType>` für den Typ " **char**" ist, die ein Objekt beschreibt, das als Gebiets Schema Aspekt dienen kann, um verschiedene Eigenschaften eines Zeichens vom Typ " **char**" zu bezeichnen.|
|[ctype_base](../standard-library/ctype-base-class.md)|Eine Basisklasse für die ctype-Klasse, die verwendet wird, um die Enumerationstypen zu definieren, mit denen Zeichen entweder einzeln oder innerhalb eines gesamten Bereichs klassifiziert oder getestet werden.|
|[ctype_byname](../standard-library/ctype-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als ctype-Facet eines angegebenen Gebietsschemas dienen kann und die Klassifizierung von Zeichen sowie die Konvertierung von Zeichen zwischen Groß-/Kleinschreibung und zwischen systemeigenen und gebietsschemaspezifischen Zeichensätzen ermöglicht.|
|[locale](../standard-library/locale-class.md)|Eine Klasse, die ein Gebietsschemaobjekt beschreibt, das kulturspezifische Informationen als einen Satz von Facets kapselt, die zusammen eine bestimmte lokalisierte Umgebung definieren.|
|[messages](../standard-library/messages-class.md)|Eine Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um lokalisierte Meldungen aus einem Katalog von internationalisierten Meldungen für ein bestimmtes Gebietsschema abzurufen.|
|[messages_base](../standard-library/messages-base-class.md)|Eine Basisklasse, die einen **int** -Typ für den Katalog von Nachrichten beschreibt.|
|[messages_byname](../standard-library/messages-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als Meldungsfacet eines angegebenen Gebietsschemas dienen kann und das Abrufen von lokalisierten Meldungen ermöglicht.|
|[money_base](../standard-library/money-base-class.md)|Eine Basisklasse für die ctype-Klasse, die verwendet wird, um die Enumerationstypen zu definieren, mit denen Zeichen entweder einzeln oder innerhalb eines gesamten Bereichs klassifiziert oder getestet werden.|
|[money_get](../standard-library/money-get-class.md)|Eine Vorlagen Klasse, die ein Objekt beschreibt, das als Gebiets Schema-Facette dienen kann, um Konvertierungen von Sequenzen vom Typ **CharType** in monetäre Werte zu steuern.|
|[money_put](../standard-library/money-put-class.md)|Eine Vorlagen Klasse, die ein Objekt beschreibt, das als Gebiets Schema-Facette dienen kann, um Konvertierungen von Währungswerten in Sequenzen vom Typ **CharType**zu steuern.|
|[moneypunct](../standard-library/moneypunct-class.md)|Eine Vorlagen Klasse, die ein Objekt beschreibt, das als Gebiets Schema Aspekt dienen kann, um die Sequenzen vom Typ **CharType** zu beschreiben, die zur Darstellung eines monetären Eingabe Felds oder eines monetären Ausgabe Felds verwendet werden.|
|[moneypunct_byname](../standard-library/moneypunct-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als moneypunct-Facet eines angegebenen Gebietsschemas dienen kann und die Formatierung von monetären Ein- und Ausgabefeldern ermöglicht.|
|[num_get](../standard-library/num-get-class.md)|Eine Vorlagen Klasse, die ein Objekt beschreibt, das als Gebiets Schema-Facette dienen kann, um Konvertierungen von Sequenzen vom Typ **CharType** in numerische Werte zu steuern.|
|[num_put](../standard-library/num-put-class.md)|Eine Vorlagen Klasse, die ein Objekt beschreibt, das als Gebiets Schema-Facette dienen kann, um Konvertierungen numerischer Werte in Sequenzen vom Typ **CharType**zu steuern.|
|[numpunct](../standard-library/numpunct-class.md)|Eine Vorlagen Klasse, die ein Objekt beschreibt, das als lokaler Aspekt dienen kann, um die Sequenzen vom Typ **CharType** zu beschreiben, mit denen Informationen zur Formatierung und Interpunktions Zeichen von numerischen und booleschen Ausdrücken dargestellt werden.|
|[numpunct_byname](../standard-library/numpunct-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als moneypunct-Facet eines angegebenen Gebietsschemas dienen kann und die Formatierung und Interpunktion von numerischen und booleschen Ausdrücken ermöglicht.|
|[time_base](../standard-library/time-base-class.md)|Eine Klasse, die als Basisklasse für Facets der time_get-Vorlagenklasse dient und nur den Enumerationstyp "dateorder" und mehrere Konstanten dieses Typs definiert.|
|[time_get](../standard-library/time-get-class.md)|Eine Vorlagen Klasse, die ein Objekt beschreibt, das als Gebiets Schema-Facette dienen kann, um Konvertierungen von Sequenzen vom Typ **CharType** in Time-Werte zu steuern.|
|[time_get_byname](../standard-library/time-get-byname-class.md)|Eine abgeleitete Vorlagen Klasse, die ein Objekt beschreibt, das als Gebiets Schema des Typs Time_get\<**CharType**, **InputIterator**> fungieren kann.|
|[time_put](../standard-library/time-put-class.md)|Eine Vorlagen Klasse, die ein Objekt beschreibt, das als Gebiets Schema-Facette dienen kann, um Konvertierungen von Zeitwerten in Sequenzen vom Typ **CharType**zu steuern.|
|[time_put_byname](../standard-library/time-put-byname-class.md)|Eine abgeleitete Vorlagen Klasse, die ein Objekt beschreibt, das als Gebiets Schema des Typs `time_put` \< **CharType**, **OutputIterator**> fungieren kann.|
|[wbuffer_convert-Klasse](../standard-library/wbuffer-convert-class.md)|Beschreibt einen Streampuffer, der die Übertragung von Elementen in einen bzw. aus einem Streampuffer steuert.|
|[wstring_convert-Klasse](../standard-library/wstring-convert-class.md)|Eine Vorlagenklasse, die Konvertierungen zwischen einer breiten Zeichenfolge und einer Bytezeichenfolge durchführt.|

## <a name="see-also"></a>Siehe auch

[Codepages](../c-runtime-library/code-pages.md)\
[Gebietsschema-Namen, Sprachen und Zeichenfolgen für Länder und Regionen](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
