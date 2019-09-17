---
title: basic_fstream-Klasse
ms.date: 11/04/2016
f1_keywords:
- fstream/std::basic_fstream
- fstream/std::basic_fstream::close
- fstream/std::basic_fstream::is_open
- fstream/std::basic_fstream::open
- fstream/std::basic_fstream::rdbuf
- fstream/std::basic_fstream::swap
helpviewer_keywords:
- std::basic_fstream [C++]
- std::basic_fstream [C++], close
- std::basic_fstream [C++], is_open
- std::basic_fstream [C++], open
- std::basic_fstream [C++], rdbuf
- std::basic_fstream [C++], swap
ms.assetid: 8473817e-42a4-430b-82b8-b476c86bcf8a
ms.openlocfilehash: 8d26d0fe0e4e4152cf05476f546b753650209dfe
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459599"
---
# <a name="basic_fstream-class"></a>basic_fstream-Klasse

Beschreibt ein Objekt, das das Einfügen und Extrahieren von Elementen und codierten Objekten über einen Streampuffer der Klasse [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> mit Elementen des Typs `Elem` steuert, dessen Zeichenmerkmale von der Klasse `Tr` bestimmt werden.

## <a name="syntax"></a>Syntax

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_fstream : public basic_iostream<Elem, Tr>
```

### <a name="parameters"></a>Parameter

*Elem*\
Das grundlegende Element des Dateipuffers.

*Stadtrat*\
Die Merkmale des grundlegenden Elements des Dateipuffers (in der Regel `char_traits`< `Elem`>).

## <a name="remarks"></a>Hinweise

Das Objekt speichert ein Objekt der Klasse `basic_filebuf`< `Elem`, `Tr`>.

> [!NOTE]
> Der Lesezeiger (get-Zeiger) und der Schreibzeiger (put-Zeiger) eines fstream-Objekts sind **NICHT** unabhängig voneinander. Wenn der get-Zeiger verschoben wird, wird auch der put-Zeiger verschoben.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht, wie ein `basic_fstream`-Objekt erstellt wird, aus dem gelesen und in das geschrieben werden kann.

```cpp
// basic_fstream_class.cpp
// compile with: /EHsc

#include <fstream>
#include <iostream>

using namespace std;

int main(int argc, char **argv)
{
    fstream fs("fstream.txt", ios::in | ios::out | ios::trunc);
    if (!fs.bad())
    {
        // Write to the file.
        fs << "Writing to a basic_fstream object..." << endl;
        fs.close();

        // Dump the contents of the file to cout.
        fs.open("fstream.txt", ios::in);
        cout << fs.rdbuf();
        fs.close();
    }
}
```

```Output
Writing to a basic_fstream object...
```

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[basic_fstream](#basic_fstream)|Konstruiert ein Objekt vom Typ `basic_fstream`.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[close](#close)|Schließt eine Datei.|
|[is_open](#is_open)|Ermittelt, ob eine Datei geöffnet ist.|
|[open](#open)|Öffnet eine Datei.|
|[rdbuf](#rdbuf)|Gibt die Adresse des gespeicherten Streampuffers zurück, die ein Zeiger auf [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> ist.|
|[swap](#swap)|Tauscht den Inhalt dieses Objekts gegen den Inhalt eines anderen `basic_fstream`-Objekts.|

## <a name="requirements"></a>Anforderungen

**Header:** \<fstream>

**Namespace:** std

## <a name="basic_fstream"></a> basic_fstream::basic_fstream

Konstruiert ein Objekt vom Typ `basic_fstream`.

```cpp
basic_fstream();

explicit basic_fstream(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::in | ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

explicit basic_fstream(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::in | ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

basic_fstream(basic_fstream&& right);
```

### <a name="parameters"></a>Parameter

*_Filename*\
Der Name der zu öffnenden Datei.

*_Mode*\
Eine der Enumerationen in [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*\
Der standardmäßige Datei öffnende Schutz, äquivalent zum *shflag* -Parameter in [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert die Basisklasse durch Aufrufen von [basic_iostream](../standard-library/basic-iostream-class.md)(`sb`). Hierbei entspricht `sb` dem gespeicherten Objekt der Klasse [basic_filebuf](../standard-library/basic-filebuf-class.md)\< **Elem**, **Tr**>. Er `sb` initialisiert außerdem durch Aufrufen `basic_filebuf` \< von **Elem**, **TR**>.

Der zweite und dritte Konstruktor initialisiert die Basisklasse durch Aufrufen von `basic_iostream`( **sb**). Er initialisiert `sb` außerdem durch Aufrufen `basic_filebuf` \< von **Elem**, **TR**> und dann **SB.** [Open](../standard-library/basic-filebuf-class.md#open)(_ *filename*, `_Mode`). Wenn die letztere Funktion einen NULL-Zeiger zurückgibt, ruft der Konstruktor [SetState](../standard-library/basic-ios-class.md#setstate)(`failbit`) auf.

Der vierte Konstruktor initialisiert das Objekt mit dem Inhalt von `right`, das als rvalue-Verweis behandelt wird.

### <a name="example"></a>Beispiel

Ein Beispiel, in dem `basic_fstream` verwendet wird, finden Sie unter [streampos](../standard-library/ios-typedefs.md#streampos).

## <a name="close"></a> basic_fstream::close

Schließt eine Datei.

```cpp
void close();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion ruft [rdbuf](#rdbuf) **->** [close](../standard-library/basic-filebuf-class.md#close) auf.

### <a name="example"></a>Beispiel

Sie finden ein Beispiel zur Verwendung von `close` unter [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).

## <a name="is_open"></a> basic_fstream::is_open

Ermittelt, ob eine Datei geöffnet ist.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Datei geöffnet ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt [rdbuf](#rdbuf) **->** [is_open](../standard-library/basic-filebuf-class.md#is_open) zurück.

### <a name="example"></a>Beispiel

Sie finden ein Beispiel zur Verwendung von `is_open` unter [basic_filebuf::is_open](../standard-library/basic-filebuf-class.md#is_open).

## <a name="open"></a> basic_fstream::open

Öffnet eine Datei.

```cpp
void open(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::in | ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

void open(
    const char* _Filename,
    ios_base::openmode _Mode);

void open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::in | ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

void open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode);
```

### <a name="parameters"></a>Parameter

*_Filename*\
Der Name der zu öffnenden Datei.

*_Mode*\
Eine der Enumerationen in [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*\
Der standardmäßige Datei öffnende Schutz, äquivalent zum *shflag* -Parameter in [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

### <a name="remarks"></a>Hinweise

Die Memberfunktion ruft [rdbuf](#rdbuf) **->** [open](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode`) auf. Wenn diese Funktion einen NULL-Zeiger zurückgibt, ruft die Funktion [SetState](../standard-library/basic-ios-class.md#setstate)( `failbit`) auf.

### <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung `open`von finden Sie unter [basic_filebuf:: Open](../standard-library/basic-filebuf-class.md#open) .

## <a name="op_eq"></a> basic_fstream::operator=

Weist diesem Objekt den Inhalt eines angegebenen Streamobjekts zu. Dies ist eine Verschiebezuweisung mit einem rvalue, der keine Kopie hinterlässt.

```cpp
basic_fstream& operator=(basic_fstream&& right);
```

### <a name="parameters"></a>Parameter

*Richting*\
Ein lvalue-Verweis auf ein `basic_fstream`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt `*this`zurück.

### <a name="remarks"></a>Hinweise

Der Member-Operator ersetzt den Inhalt des-Objekts, indem er den Inhalt von *right*verwendet, der als rvalue-Verweis behandelt wird.

## <a name="rdbuf"></a> basic_fstream::rdbuf

Gibt die Adresse des gespeicherten Streampuffers zurück, die ein Zeiger auf [basic_filebuf](../standard-library/basic-filebuf-class.md)\< **Elem**, **Tr**> ist.

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>Rückgabewert

Die Adresse des gespeicherten Streampuffers.

### <a name="example"></a>Beispiel

Sie finden ein Beispiel zur Verwendung von `rdbuf` unter [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).

## <a name="swap"></a> basic_fstream::swap

Tauscht den Inhalt von zwei `basic_fstream`-Objekten aus.

```cpp
void swap(basic_fstream& right);
```

### <a name="parameters"></a>Parameter

*Richting*\
Ein `lvalue`-Verweis auf ein `basic_fstream`-Objekt.

### <a name="remarks"></a>Hinweise

Die Member-Funktion tauscht den Inhalt dieses-Objekts und den Inhalt von *right*aus.

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream-Programmierung](../standard-library/iostream-programming.md)\
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)
