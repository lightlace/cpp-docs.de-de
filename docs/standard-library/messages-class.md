---
title: messages-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocmes/std::messages
- xlocmes/std::messages::char_type
- xlocmes/std::messages::string_type
- xlocmes/std::messages::close
- xlocmes/std::messages::do_close
- xlocmes/std::messages::do_get
- xlocmes/std::messages::do_open
- xlocmes/std::messages::get
- xlocmes/std::messages::open
dev_langs:
- C++
helpviewer_keywords:
- std::messages [C++]
- std::messages [C++], char_type
- std::messages [C++], string_type
- std::messages [C++], close
- std::messages [C++], do_close
- std::messages [C++], do_get
- std::messages [C++], do_open
- std::messages [C++], get
- std::messages [C++], open
ms.assetid: c4c71f40-4f24-48ab-9f7c-daccd8d5bd83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ffc59d3425f403fb1dca43f70876cfbfb5d3dd9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="messages-class"></a>messages-Klasse

Die Vorlagenklasse beschreibt ein Objekt, das als Gebietsschemafacet dienen kann, um lokalisierte Meldungen aus einem Katalog von internationalisierten Meldungen für ein bestimmtes Gebietsschema abzurufen.

Während die Nachrichtenklasse implementiert wird, sind derzeit keine Meldungen vorhanden.

## <a name="syntax"></a>Syntax

```cpp
template <class CharType>
class messages : public messages_base;
```

### <a name="parameters"></a>Parameter

`CharType` Der Typ, der innerhalb eines Programms zum Codieren von Zeichen in einem Gebietsschema verwendet wird.

## <a name="remarks"></a>Hinweise

Wie bei jedem Gebietsschemafacet hat die statische Objekt-ID einen anfänglichen gespeicherten Wert von NULL. Beim ersten Versuch, auf den gespeicherten Wert zuzugreifen, wird ein eindeutiger positiver Wert in **id** gespeichert.

Dieses Facet öffnet im Grunde einen Katalog von Meldungen, die in der messages_base-Basisklasse definiert sind, ruft die erforderlichen Informationen ab und schließt den Katalog.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[messages](#messages)|Die Meldungsfacet-Konstruktorfunktion.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[char_type](#char_type)|Ein Zeichentyp, mit dem Meldungen angezeigt werden.|
|[string_type](#string_type)|Ein Typ, der eine Zeichenfolge vom Typ `basic_string` beschreibt, die Zeichen vom Typ `CharType` enthält.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[close](#close)|Schließt den Meldungskatalog.|
|[do_close](#do_close)|Eine virtuelle Funktion, die aufgerufen wird, um den Meldungskatalog zu schließen.|
|[do_get](#do_get)|Eine virtuelle Funktion, die aufgerufen wird, um den Meldungskatalog abzurufen.|
|[do_open](#do_open)|Eine virtuelle Funktion, die aufgerufen wird, um den Meldungskatalog zu öffnen.|
|[get](#get)|Ruft den Meldungskatalog ab.|
|[open](#open)|Öffnet den Meldungskatalog.|

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="char_type"></a> messages::char_type

Ein Zeichentyp, mit dem Meldungen angezeigt werden.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Hinweise

Der Typ stellt ein Synonym für den Vorlagenparameter **CharType** dar.

## <a name="close"></a> messages::close

Schließt den Meldungskatalog.

```cpp
void close(catalog _Catval) const;
```

### <a name="parameters"></a>Parameter

`_Catval` Der Katalog, die geschlossen werden.

### <a name="remarks"></a>Hinweise

Die Memberfunktion ruft [do_close](#do_close)(_ *Catval*) auf.

## <a name="do_close"></a> messages::do_close

Eine virtuelle Funktion, die aufgerufen wird, um den Meldungskatalog zu schließen.

```cpp
virtual void do_close(catalog _Catval) const;
```

### <a name="parameters"></a>Parameter

`_Catval` Der Katalog, die geschlossen werden.

### <a name="remarks"></a>Hinweise

Die geschützte Memberfunktion schließt den Meldungskatalog `_Catval`, der durch einen früheren Aufruf an [do_open](#do_open) geöffnet worden sein muss.

*_Catval* muss aus einem vorher geöffneten Katalog abgerufen werden, der nicht geschlossen wurde.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [close](#close), mit dem `do_close` aufgerufen wird.

## <a name="do_get"></a> messages::do_get

Eine virtuelle Funktion, die aufgerufen wird, um den Meldungskatalog abzurufen.

```cpp
virtual string_type do_get(
    catalog _Catval,
    int _Set,
    int _Message,
    const string_type& _Dfault) const;
```

### <a name="parameters"></a>Parameter

`_Catval` Die ID-Wert, den meldungskatalog zu durchsuchenden angeben.

`_Set` Identifiziert die erste verwendet, um eine Nachricht in einem Katalog Nachricht gesucht werden soll.

`_Message` Die zweite verwendet, um eine Nachricht in einem Katalog Nachricht gesucht werden soll.

`_Dfault` Die Zeichenfolge, die bei einem Fehler zurückgegeben werden.

### <a name="return-value"></a>Rückgabewert

Er gibt bei einem Fehler eine Kopie von `_Dfault` zurück. Andernfalls gibt er eine Kopie einer angegebenen Meldungssequenz zurück.

### <a name="remarks"></a>Hinweise

Die geschützte Memberfunktion versucht eine Meldungssequenz auf dem Meldungskatalog `_Catval` abzurufen. Dabei verwendet sie möglicherweise `_Set`, `_Message` und `_Dfault`.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [get](#get), mit dem `do_get` aufgerufen wird.

## <a name="do_open"></a> messages::do_open

Eine virtuelle Funktion, die aufgerufen wird, um den Meldungskatalog zu öffnen.

```cpp
virtual catalog do_open(
    const string& _Catname,
    const locale& _Loc) const;
```

### <a name="parameters"></a>Parameter

`_Catname` Der Name des Katalogs ein, der gesucht werden soll.

`_Loc` Das Gebietsschema, die im Katalog gesucht wird.

### <a name="return-value"></a>Rückgabewert

Er gibt einen Wert zurück, der bei einem Fehler kleiner als null ist. Andernfalls kann der Rückgabewert als erstes Argument bei einem späteren Aufruf an [get](#get) verwendet werden.

### <a name="remarks"></a>Hinweise

Die geschützte Memberfunktion versucht einen Meldungskatalog mit dem Namen `_Catname` aufzurufen. Dabei verwendet sie möglicherweise das Gebietsschema `_Loc`

Der Rückgabewert sollte als Argument für einen späteren Aufruf an [close](#close) verwendet werden.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [open](#open), mit dem `do_open` aufgerufen wird.

## <a name="get"></a> messages::get

Ruft den Meldungskatalog ab.

```cpp
string_type get(
    catalog _CatVal,
    int _Set,
    int _Message,
    const string_type& _Dfault) const;
```

### <a name="parameters"></a>Parameter

`_Catval` Die ID-Wert, den meldungskatalog zu durchsuchenden angeben.

`_Set` Identifiziert die erste verwendet, um eine Nachricht in einem Katalog Nachricht gesucht werden soll.

`_Message` Die zweite verwendet, um eine Nachricht in einem Katalog Nachricht gesucht werden soll.

`_Dfault` Die Zeichenfolge, die bei einem Fehler zurückgegeben werden.

### <a name="return-value"></a>Rückgabewert

Er gibt bei einem Fehler eine Kopie von `_Dfault` zurück. Andernfalls gibt er eine Kopie einer angegebenen Meldungssequenz zurück.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt [do_get](#do_get)(`_Catval`,`_Set` `_Message`,`_Dfault`) zurück.

## <a name="messages"></a> messages::messages

Die Meldungsfacet-Konstruktorfunktion.

```cpp
explicit messages(
    size_t _Refs = 0);

protected: messages(
    const char* _Locname,
    size_t _Refs = 0);
```

### <a name="parameters"></a>Parameter

`_Refs` Integer-Wert verwendet, um den Typ der Verwaltung des Arbeitsspeichers für das Objekt angeben.

`_Locname` Der Name des Gebietsschemas.

### <a name="remarks"></a>Hinweise

Mögliche Werte für den `_Refs`-Parameter und ihre Bedeutung:

- 0: Die Lebensdauer des Objekts wird von den Gebietsschemas verwaltet, in denen es enthalten ist.

- 1: Die Lebensdauer des Objekts muss manuell verwaltet werden.

- \> 1: Diese Werte sind nicht definiert.

Direkte Beispiele hierfür sind nicht möglich, da der Destruktor geschützt ist.

Der Konstruktor initialisiert sein Basisobjekt mit **locale::**[facet](../standard-library/locale-class.md#facet_class)(`_Refs`).

## <a name="open"></a> messages::open

Öffnet den Meldungskatalog.

```cpp
catalog open(
    const string& _Catname,
    const locale& _Loc) const;
```

### <a name="parameters"></a>Parameter

`_Catname` Der Name des Katalogs ein, der gesucht werden soll.

`_Loc` Das Gebietsschema, die im Katalog gesucht wird.

### <a name="return-value"></a>Rückgabewert

Er gibt einen Wert zurück, der bei einem Fehler kleiner als null ist. Andernfalls kann der Rückgabewert als erstes Argument bei einem späteren Aufruf an [get](#get) verwendet werden.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt [do_open](#do_open)(`_Catname`,`_Loc`) zurück.

## <a name="string_type"></a> messages::string_type

Ein Typ, der eine Zeichenfolge vom Typ `basic_string` beschreibt, die Zeichen vom Typ **CharType** enthält.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Hinweise

Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [basic_string](../standard-library/basic-string-class.md), deren Objekte Kopien der Meldungssequenzen speichern können.

## <a name="see-also"></a>Siehe auch

[\<locale>](../standard-library/locale.md)<br/>
[messages_base-Klasse](../standard-library/messages-base-class.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
