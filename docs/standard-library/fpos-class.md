---
title: fpos-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- iosfwd/std::fpos
- iosfwd/std::fpos::seekpos
- iosfwd/std::fpos::state
- iosfwd/std::fpos::operator streamoff
dev_langs:
- C++
helpviewer_keywords:
- std::fpos [C++]
- std::fpos [C++], seekpos
- std::fpos [C++], state
ms.assetid: ffd0827c-fa34-47f4-b10e-5cb707fcde47
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ce85d846d142e2c15a0fba6d2d3fb76c924b97f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966601"
---
# <a name="fpos-class"></a>fpos-Klasse

Die Vorlagenklasse beschreibt ein Objekt, das alle Informationen, die zum Wiederherstellen eines beliebigen Dateipositionsindikators innerhalb eines Streams erforderlich sind, speichern kann. Ein Objekt der Klasse fpos\< **St**> speichert effektiv mindestens zwei Memberobjekte:

- Ein Byteoffset vom Typ [streamoff](../standard-library/ios-typedefs.md#streamoff)

- Ein konvertierungszustand, für die Verwendung durch ein Objekt der Klasse Basic_filebuf und vom Typ `St`, in der Regel `mbstate_t`.

Es kann auch eine beliebige Dateiposition speichern, die von einem Objekt der Klasse [basic_filebuf](../standard-library/basic-filebuf-class.md) und vom Typ `fpos_t` verwendet werden kann. In einer Umgebung mit begrenzter Dateigröße werden `streamoff` und `fpos_t` jedoch manchmal synonym verwendet. In einer Umgebung ohne Streams, mit zustandsabhängiger Codierung, wird `mbstate_t` möglicherweise nicht verwendet. Daher kann die Anzahl der gespeicherten Memberobjekte variieren.

## <a name="syntax"></a>Syntax

```cpp
template <class Statetype>
class fpos
```

### <a name="parameters"></a>Parameter

*Statetype* Zustandsinformationen.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[fpos](#fpos)|Erstellt ein Objekt, das Informationen zu einer Position (Offset) in einem Stream enthält.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[seekpos](#seekpos)|Wird nur intern von der C++-Standardbibliothek verwendet. Rufen Sie diese Methode nicht aus Ihrem Code auf.|
|[state](#state)|Legt den Konvertierungszustand fest oder gibt ihn zurück.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator!=](#op_neq)|Testet Dateipositionsindikatoren auf Ungleichheit.|
|[operator+](#op_add)|Erhöht einen Dateipositionsindikator.|
|[operator+=](#op_add_eq)|Erhöht einen Dateipositionsindikator.|
|[operator-](#operator-)|Verringert einen Dateipositionsindikator.|
|[operator-=](#operator-_eq)|Verringert einen Dateipositionsindikator.|
|[operator==](#op_eq_eq)|Testet Dateipositionsindikatoren auf Gleichheit.|
|[operator streamoff](#op_streamoff)|Wandelt ein Objekt vom Typ `fpos` in ein Objekt vom Typ `streamoff` um.|

## <a name="requirements"></a>Anforderungen

**Header:** \<ios>

**Namespace:** std

## <a name="fpos"></a> fpos::fpos

Erstellt ein Objekt, das Informationen zu einer Position (Offset) in einem Stream enthält.

```cpp
fpos(streamoff _Off = 0);

fpos(Statetype _State, fpos_t _Filepos);
```

### <a name="parameters"></a>Parameter

*_Off* der Offset in den Stream.

*_State* den Status der `fpos` Objekt.

*_Filepos* der Offset in den Stream.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor speichert den Offset *_Off*, relativ zum Anfang der Datei, und klicken Sie in den ursprünglichen konvertierungszustand (Wenn dies gewünscht ist). Wenn *_Off* ist-1. das resultierende Objekt stellt eine ungültige Streamposition dar.

Der zweite Konstruktor speichert einen NULL-Offset und das Objekt *_State*.

## <a name="op_neq"></a> fpos::operator!=

Testet Dateipositionsindikatoren auf Ungleichheit.

```cpp
bool operator!=(const fpos<Statetype>& right) const;
```

### <a name="parameters"></a>Parameter

*richtige* der dateipositionsindikator, gegen den verglichen.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Dateipositionsindikatoren nicht identisch sind, andernfalls **FALSE**

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt `!(*this == right)`zurück.

### <a name="example"></a>Beispiel

```cpp
// fpos_op_neq.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main( )
{
   using namespace std;

   fpos<int> pos1, pos2;
   ifstream file;
   char c;

   // Compare two fpos object
   if ( pos1 != pos2 )
      cout << "File position pos1 and pos2 are not equal" << endl;
   else
      cout << "File position pos1 and pos2 are equal" << endl;

   file.open( "fpos_op_neq.txt" );
   file.seekg( 0 );   // Goes to a zero-based position in the file
   pos1 = file.tellg( );
   file.get( c);
   cout << c << endl;

   // Increment pos1
   pos1 += 1;
   file.get( c );
   cout << c << endl;

   pos1 = file.tellg( ) - fpos<int>( 2);
   file.seekg( pos1 );
   file.get( c );
   cout << c << endl;

   // Increment pos1
   pos1 = pos1 + fpos<int>( 1 );
   file.get(c);
   cout << c << endl;

   pos1 -= fpos<int>( 2 );
   file.seekg( pos1 );
   file.get( c );
   cout << c << endl;

   file.close( );
}
```

## <a name="op_add"></a> fpos::operator+

Erhöht einen Dateipositionsindikator.

```cpp
fpos<Statetype> operator+(streamoff _Off) const;
```

### <a name="parameters"></a>Parameter

*_Off* der Offset, der durch den der dateipositionsindikator erhöht werden sollen.

### <a name="return-value"></a>Rückgabewert

Die Position in der Datei

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt „**fpos(\*this) +=** `_Off`“ zurück.

### <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von `operator+` finden Sie unter [operator!=](#op_neq).

## <a name="op_add_eq"></a> fpos::operator+=

Erhöht einen Dateipositionsindikator.

```cpp
fpos<Statetype>& operator+=(streamoff _Off);
```

### <a name="parameters"></a>Parameter

*_Off* der Offset, der durch den der dateipositionsindikator erhöht werden sollen.

### <a name="return-value"></a>Rückgabewert

Die Position in der Datei

### <a name="remarks"></a>Hinweise

Addiert die Memberfunktion *_Off* auf das gespeicherte Offset-Memberobjekt-Objekt und klicken Sie dann die gibt  **\*dies**. Für die Positionierung innerhalb einer Datei ist das Ergebnis in der Regel nur für binäre Datenströme gültig, die über keine zustandsabhängige Codierung verfügen.

### <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von `operator+=` finden Sie unter [operator!=](#op_neq).

## <a name="fpos__operator-"></a> fpos::operator-

Verringert einen Dateipositionsindikator.

```cpp
streamoff operator-(const fpos<Statetype>& right) const;

fpos<Statetype> operator-(streamoff _Off) const;
```

### <a name="parameters"></a>Parameter

*richtige* Dateiposition.

*_Off* Stream Offset.

### <a name="return-value"></a>Rückgabewert

Die erste Memberfunktion gibt `(streamoff)*this - (streamoff) right` zurück. Die zweite Memberfunktion gibt `fpos(*this) -= _Off` zurück.

### <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von `operator-` finden Sie unter [operator!=](#op_neq).

## <a name="fpos__operator-_eq"></a> fpos::operator-=

Verringert einen Dateipositionsindikator.

```cpp
fpos<Statetype>& operator-=(streamoff _Off);
```

### <a name="parameters"></a>Parameter

*_Off* Stream Offset.

### <a name="return-value"></a>Rückgabewert

Die Memberfunktion gibt `fpos(*this) -= _Off`zurück.

### <a name="remarks"></a>Hinweise

Für die Positionierung innerhalb einer Datei ist das Ergebnis in der Regel nur für binäre Datenströme gültig, die über keine zustandsabhängige Codierung verfügen.

### <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von `operator-=` finden Sie unter [operator!=](#op_neq).

## <a name="op_eq_eq"></a> fpos::operator==

Testet Dateipositionsindikatoren auf Gleichheit.

```cpp
bool operator==(const fpos<Statetype>& right) const;
```

### <a name="parameters"></a>Parameter

*richtige* der dateipositionsindikator, gegen den verglichen.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Dateipositionsindikatoren identisch sind, andernfalls **FALSE**

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt `(streamoff)*this == (streamoff)right`zurück.

### <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von `operator+=` finden Sie unter [operator!=](#op_neq).

## <a name="op_streamoff"></a> fpos::operator streamoff

Wandelt ein Objekt vom Typ `fpos` in ein Objekt vom Typ `streamoff` um

```cpp
operator streamoff() const;
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt das gespeicherte Offset-Memberobjekt und alle zusätzlichen Offsets zurück, die als Teil des `fpos_t`-Memberobjekts gespeichert sind.

### <a name="example"></a>Beispiel

```cpp
// fpos_op_streampos.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;
   streamoff s;
   ofstream file( "rdbuf.txt");

   fpos<mbstate_t> f = file.tellp( );
   // Is equivalent to ..
   // streampos f = file.tellp( );
   s = f;
   cout << s << endl;
}
```

```Output
0
```

## <a name="seekpos"></a> fpos::seekpos

Diese Methode wird nur intern von der C++-Standardbibliothek verwendet. Rufen Sie diese Methode nicht aus Ihrem Code auf.

```cpp
fpos_t seekpos() const;
```

## <a name="state"></a> fpos::state

Legt den Konvertierungszustand fest oder gibt ihn zurück.

```cpp
Statetype state() const;

void state(Statetype _State);
```

### <a name="parameters"></a>Parameter

*_State* der neue Konvertierungsstatus.

### <a name="return-value"></a>Rückgabewert

Der Konvertierungsstatus

### <a name="remarks"></a>Hinweise

Die erste Memberfunktion gibt den Wert, der in gespeicherte zurück die `St` Member-Objekt. Die zweite Memberfunktion speichert *_State* in die `St` Member-Objekt.

### <a name="example"></a>Beispiel

```cpp
// fpos_state.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
#include <fstream>

int main() {
   using namespace std;
   streamoff s;
   ifstream file( "fpos_state.txt" );

   fpos<mbstate_t> f = file.tellg( );
   char ch;
   while ( !file.eof( ) )
      file.get( ch );
   s = f;
   cout << f.state( ) << endl;
   f.state( 9 );
   cout << f.state( ) << endl;
}
```

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)<br/>
