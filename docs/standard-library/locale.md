---
title: '&lt;Gebietsschema&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <locale>
- locale/std::<locale>
- std::<locale>
dev_langs:
- C++
helpviewer_keywords:
- locale header
ms.assetid: ca56f9d2-7128-44da-8df1-f4c78c17fbf2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b81483b21f42f17320cb6d7b636fe5dd1f4c5e73
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
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
|[codecvt_base](../standard-library/codecvt-base-class.md)|Eine Basisklasse für die codecvt-Klasse, die verwendet wird, um einen Enumerationstyp zu definieren, der als **Ergebnis** gekennzeichnet ist. Dieser wird als Rückgabetyp für die Facetmemberfunktionen verwendet, um das Ergebnis einer Konvertierung anzugeben.|
|[codecvt_byname](../standard-library/codecvt-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als Sortierungsfacet eines angegebenen Gebietsschemas dienen kann, sodass für einen kulturellen Bereich spezifische Informationen über Konvertierungen abgerufen werden können.|
|[collate](../standard-library/collate-class.md)|Eine Sortierungsvorlagenklasse, die ein Facet bereitstellt, das Konventionen zum Sortieren von Zeichenfolgen verarbeitet.|
|[collate_byname](../standard-library/collate-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als Sortierungsfacet eines angegebenen Gebietsschemas dienen kann, sodass für einen kulturellen Bereich spezifische Informationen über Konventionen zum Sortieren von Zeichenfolgen abgerufen werden können.|
|[ctype](../standard-library/ctype-class.md)|Eine Vorlagenklasse, die ein Facet bereitstellt, das verwendet wird, um Zeichen zu klassifizieren, zwischen Groß- und Kleinbuchstaben zu wechseln und zwischen dem systemeigenen Zeichensatz und dem vom Gebietsschema verwendeten Zeichensatz zu konvertieren.|
|[ctype\<char>](../standard-library/ctype-char-class.md)|Eine Klasse, ist eine explizite Spezialisierung der Vorlagenklasse **Ctype\<CharType**> eingeben `char`, beschreibt ein Objekt, das als gebietsschemafacet zur verschiedene Eigenschaften eines Zeichens vom Typ charakterisieren dienen kann `char`.|
|[ctype_base](../standard-library/ctype-base-class.md)|Eine Basisklasse für die ctype-Klasse, die verwendet wird, um die Enumerationstypen zu definieren, mit denen Zeichen entweder einzeln oder innerhalb eines gesamten Bereichs klassifiziert oder getestet werden.|
|[ctype_byname](../standard-library/ctype-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als ctype-Facet eines angegebenen Gebietsschemas dienen kann und die Klassifizierung von Zeichen sowie die Konvertierung von Zeichen zwischen Groß-/Kleinschreibung und zwischen systemeigenen und gebietsschemaspezifischen Zeichensätzen ermöglicht.|
|[locale](../standard-library/locale-class.md)|Eine Klasse, die ein Gebietsschemaobjekt beschreibt, das kulturspezifische Informationen als einen Satz von Facets kapselt, die zusammen eine bestimmte lokalisierte Umgebung definieren.|
|[messages](../standard-library/messages-class.md)|Eine Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um lokalisierte Meldungen aus einem Katalog von internationalisierten Meldungen für ein bestimmtes Gebietsschema abzurufen.|
|[messages_base](../standard-library/messages-base-class.md)|Eine Basisklasse, die einen `int`-Typ für den Katalog von Meldungen beschreibt.|
|[messages_byname](../standard-library/messages-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als Meldungsfacet eines angegebenen Gebietsschemas dienen kann und das Abrufen von lokalisierten Meldungen ermöglicht.|
|[money_base](../standard-library/money-base-class.md)|Eine Basisklasse für die ctype-Klasse, die verwendet wird, um die Enumerationstypen zu definieren, mit denen Zeichen entweder einzeln oder innerhalb eines gesamten Bereichs klassifiziert oder getestet werden.|
|[money_get](../standard-library/money-get-class.md)|Eine Vorlagenklasse, die ein Objekt beschreibt, das als gebietsschemafacet zur Steuerelement Konvertierungen von Sequenzen des Typs dienen können **CharType** in monetäre Werte.|
|[money_put](../standard-library/money-put-class.md)|Eine Vorlagenklasse, die ein Objekt beschreibt, das als gebietsschemafacet zur Steuerelement Konvertierungen von monetären Werten in Sequenzen vom Typ dienen können **CharType**.|
|[moneypunct](../standard-library/moneypunct-class.md)|Eine Vorlagenklasse, die ein Objekt beschreibt, das als gebietsschemafacet beschreiben die Sequenzen vom Typ dienen können **CharType** verwendet, um ein Monetäres Eingabefeld oder ein Monetäres Ausgabefeld darzustellen.|
|[moneypunct_byname](../standard-library/moneypunct-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als moneypunct-Facet eines angegebenen Gebietsschemas dienen kann und die Formatierung von monetären Ein- und Ausgabefeldern ermöglicht.|
|[num_get](../standard-library/num-get-class.md)|Eine Vorlagenklasse, die ein Objekt beschreibt, das als gebietsschemafacet zur Steuerelement Konvertierungen von Sequenzen des Typs dienen können **CharType** in numerische Werte.|
|[num_put](../standard-library/num-put-class.md)|Eine Vorlagenklasse, die ein Objekt beschreibt, das als gebietsschemafacet zur Steuerelement Konvertierungen von numerischen Werten in Sequenzen vom Typ dienen können **CharType**.|
|[numpunct](../standard-library/numpunct-class.md)|Eine Vorlagenklasse, die ein Objekt beschreibt, das als lokales Facet beschreiben die Sequenzen vom Typ dienen können **CharType** verwendet, um Informationen zur Formatierung und Interpunktion von numerischen und booleschen Ausdrücken dargestellt.|
|[numpunct_byname](../standard-library/numpunct-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als moneypunct-Facet eines angegebenen Gebietsschemas dienen kann und die Formatierung und Interpunktion von numerischen und booleschen Ausdrücken ermöglicht.|
|[time_base](../standard-library/time-base-class.md)|Eine Klasse, die als Basisklasse für Facets der time_get-Vorlagenklasse dient und nur den Enumerationstyp "dateorder" und mehrere Konstanten dieses Typs definiert.|
|[time_get](../standard-library/time-get-class.md)|Eine Vorlagenklasse, die ein Objekt beschreibt, das als gebietsschemafacet zur Steuerelement Konvertierungen von Sequenzen des Typs dienen können **CharType** in Zeitwerte.|
|[time_get_byname](../standard-library/time-get-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als gebietsschemafacet vom Typ Time_get dienen können\<**CharType**, **InputIterator**>.|
|[time_put](../standard-library/time-put-class.md)|Eine Vorlagenklasse, die ein Objekt beschreibt, das als gebietsschemafacet zur Steuerelement Konvertierungen von Zeitwerten in Sequenzen vom Typ dienen können **CharType**.|
|[time_put_byname](../standard-library/time-put-byname-class.md)|Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als gebietsschemafacet vom Typ dienen können `time_put` \< **CharType**, **OutputIterator**>.|
|[wbuffer_convert-Klasse](../standard-library/wbuffer-convert-class.md)|Beschreibt einen Streampuffer, der die Übertragung von Elementen in einen bzw. aus einem Streampuffer steuert.|
|[wstring_convert-Klasse](../standard-library/wstring-convert-class.md)|Eine Vorlagenklasse, die Konvertierungen zwischen einer breiten Zeichenfolge und einer Bytezeichenfolge durchführt.|

## <a name="see-also"></a>Siehe auch

[Codepages](../c-runtime-library/code-pages.md)<br/>
[Gebietsschemanamen, Sprachen und Zeichenfolgen für Länder/Regionen](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
