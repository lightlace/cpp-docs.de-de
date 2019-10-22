---
title: basic_iostream-Klasse
ms.date: 11/04/2016
f1_keywords:
- istream/std::basic_iostream
- istream/std::basic_iostream::swap
helpviewer_keywords:
- basic_iostream class
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
ms.openlocfilehash: 190c9aa23493cea67bae44be93fd3fdbdecc4447
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72690008"
---
# <a name="basic_iostream-class"></a>basic_iostream-Klasse

Eine Streamklasse für Ein- und Ausgabe.

## <a name="syntax"></a>Syntax

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_iostream : public basic_istream<Elem, Tr>,
    public basic_ostream<Elem, Tr>
{
public:
    explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

    virtual ~basic_iostream();

};
```

## <a name="remarks"></a>Hinweise

In der Klassen Vorlage wird ein Objekt beschrieben, das Einfügevorgänge über seine Basisklasse [basic_ostream](../standard-library/basic-ostream-class.md) <  `Elem`, `Tr` > und Extraktionen über seine Basisklasse [basic_istream](../standard-library/basic-istream-class.md) <  `Elem` `Tr` >. Die beiden Objekte nutzen gemeinsam die virtuelle Basisklasse [basic_ios](../standard-library/basic-ios-class.md)< `Elem``Tr`>. Außerdem verwalten sie einen gemeinsamen Streampuffer mit Elementen des Typs `Elem`, deren Zeichenmerkmale durch die `Tr`-Klasse bestimmt sind. Der Konstruktor initialisiert seine Basisklassen über `basic_istream`( **strbuf**) und `basic_ostream`( **strbuf**).

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[basic_iostream](#basic_iostream)|Erstellen eines `basic_iostream`-Objekts|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[swap](#swap)|Tauscht den Inhalt des bereitgestellten `basic_iostream`-Objekts mit dem Inhalt dieses Objekts aus.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator=](#op_eq)|Weist diesem Objekt den Wert eines angegebenen `basic_iostream`-Objekts zu . Dies ist eine Verschiebezuweisung über einen `rvalue`, die keine Kopie hinterlässt.|

## <a name="requirements"></a>Anforderungen

**Header:** \<istream>

**Namespace:** std

## <a name="basic_iostream"></a> basic_iostream::basic_iostream

Erstellen eines `basic_iostream`-Objekts

```cpp
explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

basic_iostream(basic_iostream&& right);

basic_iostream();
```

### <a name="parameters"></a>Parameter

*\ "*
Ein vorhandenes `basic_streambuf`-Objekt.

*Rechte* \
Ein vorhandenes `basic_iostream`-Objekt, das verwendet wird, um ein neues `basic_iostream`-Objekt zu erstellen.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert die Basisobjekte über `basic_istream(strbuf)` und `basic_ostream(strbuf)`.

Der zweite Konstruktor initialisiert die Basisobjekte durch Aufrufen von `move(right)`.

## <a name="op_eq"></a> basic_iostream::operator=

Weisen Sie diesem Objekt den Wert eines angegebenen `basic_iostream`-Objekts zu . Dies ist eine Verschiebezuweisung über einen rvalue, die keine Kopie hinterlässt.

```cpp
basic_iostream& operator=(basic_iostream&& right);
```

### <a name="parameters"></a>Parameter

*Rechte* \
Ein `rvalue`-Verweis auf ein `basic_iostream`-Objekt, aus dem zugewiesen werden soll.

### <a name="remarks"></a>Hinweise

Der Member-Operator ruft `swap(right)` auf.

## <a name="swap"></a> basic_iostream::swap

Tauscht den Inhalt des bereitgestellten `basic_iostream`-Objekts mit dem Inhalt dieses Objekts aus.

```cpp
void swap(basic_iostream& right);
```

### <a name="parameters"></a>Parameter

*Rechte* \
Das auszutauschende `basic_iostream`-Objekt.

### <a name="remarks"></a>Hinweise

Die Member-Funktion ruft `swap(right)` auf.

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream-Programmierung](../standard-library/iostream-programming.md)\
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)
