---
title: '&lt;ios&gt;-Funktionen'
ms.date: 11/04/2016
f1_keywords:
- xiosbase/std::defaultfloat
- xiosbase/std::boolalpha
- xiosbase/std::dec
- ios/std::fixed
- ios/std::hex
- ios/std::internal
- ios/std::left
- ios/std::noboolalpha
- ios/std::noshowbase
- ios/std::noshowpoint
- ios/std::noshowpos
- ios/std::noskipws
- ios/std::nounitbuf
- ios/std::nouppercase
- ios/std::oct
- ios/std::right
- ios/std::scientific
- ios/std::showbase
- ios/std::showpoint
- ios/std::showpos
- ios/std::skipws
- ios/std::unitbuf
- ios/std::uppercase
ms.assetid: 1382d53f-e531-4b41-adf6-6a1543512e51
helpviewer_keywords:
- std::defaultfloat [C++]
- std::boolalpha [C++]
- std::dec [C++]
- std::fixed [C++]
- std::hex [C++]
- std::internal [C++]
- std::left [C++]
- std::noboolalpha [C++]
- std::noshowbase [C++]
- std::noshowpoint [C++]
- std::noshowpos [C++]
- std::noskipws [C++]
- std::nounitbuf [C++]
- std::nouppercase [C++]
- std::oct [C++]
- std::right [C++]
- std::scientific [C++]
- std::showbase [C++]
- std::showpoint [C++]
- std::showpos [C++]
- std::skipws [C++]
- std::unitbuf [C++]
- std::uppercase [C++]
ms.openlocfilehash: 18f42f8e5bcd69872e4300d154eb72f489015e36
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51519679"
---
# <a name="ltiosgt-functions"></a>&lt;ios&gt;-Funktionen

||||
|-|-|-|
|[defaultfloat](#ios_defaultfloat)|[boolalpha](#boolalpha)|[dec](#dec)|
|[fixed](#fixed)|[hex](#hex)|[internal](#internal)|
|[left](#left)|[noboolalpha](#noboolalpha)|[noshowbase](#noshowbase)|
|[noshowpoint](#noshowpoint)|[noshowpos](#noshowpos)|[noskipws](#noskipws)|
|[nounitbuf](#nounitbuf)|[nouppercase](#nouppercase)|[oct](#oct)|
|[right](#right)|[scientific](#scientific)|[showbase](#showbase)|
|[showpoint](#showpoint)|[showpos](#showpos)|[skipws](#skipws)|
|[unitbuf](#unitbuf)|[uppercase](#uppercase)|

## <a name="boolalpha"></a> boolalpha

Gibt an, dass Variablen des Typs [bool](../cpp/bool-cpp.md) im Stream als **TRUE** oder **FALSE** angezeigt werden.

```cpp
ios_base& boolalpha(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt, von dem _*str* abgeleitet wird.

### <a name="remarks"></a>Hinweise

Standardmäßig werden Variablen vom Typ **"bool"** als 1 oder 0 angezeigt werden.

`boolalpha` Ruft effektiv `str`.[ SETF](../standard-library/ios-base-class.md#setf)( `ios_base::boolalpha`), und gibt dann zurück *str*.

[noboolalpha](../standard-library/ios-functions.md#noboolalpha) kehrt den Effekt von `boolalpha` um.

### <a name="example"></a>Beispiel

```cpp
// ios_boolalpha.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   bool b = true;
   cout << b << endl;
   boolalpha( cout );
   cout << b << endl;
   noboolalpha( cout );
   cout << b << endl;
   cout << boolalpha << b << endl;
}
```

```Output
1
true
1
true
```

## <a name="dec"></a> dec

Gibt an, dass ganzzahlige Variablen in Basis-10-Schreibweise angezeigt werden.

```cpp
ios_base& dec(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt, von dem _*str* abgeleitet wird.

### <a name="remarks"></a>Hinweise

Standardmäßig werden Ganzzahlvariablen in Basis-10-Schreibweise angezeigt.

`dec` Ruft effektiv `str.` [Setf](../standard-library/ios-base-class.md#setf)( `ios_base::dec`, `ios_base::basefield`), und gibt dann zurück *str*.

### <a name="example"></a>Beispiel

```cpp
// ios_dec.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   int i = 100;

   cout << i << endl;   // Default is base 10
   cout << hex << i << endl;
   dec( cout );
   cout << i << endl;
   oct( cout );
   cout << i << endl;
   cout << dec << i << endl;
}
```

```Output
100
64
100
144
100
```

## <a name="ios_defaultfloat"></a>&lt;ios&gt; defaultfloat

Konfiguriert die Flags eines `ios_base`-Objekts, sodass ein Standard-Anzeigeformat für Floatwerte verwendet wird.

```cpp
ios_base& defaultfloat(ios_base& _Iosbase);
```

### <a name="parameters"></a>Parameter

*"_Iosbase"*<br/>
Ein `ios_base`-Objekt.

### <a name="remarks"></a>Hinweise

Der Manipulator ruft _I `osbase.`[ios_base::unsetf](../standard-library/ios-base-class.md#unsetf)`(ios_base::floatfield)` auf und gibt dann _I `osbase` zurück.

## <a name="fixed"></a> fixed

Gibt an, dass eine Gleitkommazahl in fester Dezimalschreibweise angezeigt wird.

```cpp
ios_base& fixed(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt, von dem _*str* abgeleitet wird.

### <a name="remarks"></a>Hinweise

`fixed` ist die standardanzeigeschreibweise für Gleitkommazahlen an. [scientific](../standard-library/ios-functions.md#scientific) bewirkt, dass Gleitkommazahlen in wissenschaftlicher Schreibweise angezeigt werden.

Der Manipulator ruft *str*.[ SETF](../standard-library/ios-base-class.md#setf)( `ios_base::fixed`, `ios_base::floatfield` ), und gibt dann zurück *str*.

### <a name="example"></a>Beispiel

```cpp
// ios_fixed.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   float i = 1.1F;

   cout << i << endl;   // fixed is the default
   cout << scientific << i << endl;
   cout.precision( 1 );
   cout << fixed << i << endl;
}
```

```Output
1.1
1.100000e+000
1.1
```

## <a name="hex"></a> hex

Gibt an, dass ganzzahlige Variablen in Basis-16-Schreibweise angezeigt werden soll.

```cpp
ios_base& hex(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt, von dem _*str* abgeleitet wird.

### <a name="remarks"></a>Hinweise

Standardmäßig werden Ganzzahlvariablen in Basis-10-Schreibweise angezeigt. Ebenfalls verändern [dec](../standard-library/ios-functions.md#dec) und [oct](../standard-library/ios-functions.md#oct) die Anzeige von Ganzzahlvariablen.

Der Manipulator ruft `str` **.** [Setf](../standard-library/ios-base-class.md#setf)( `ios_base::hex`, `ios_base::basefield`), und gibt dann zurück *str*.

### <a name="example"></a>Beispiel

Finden Sie unter [Dec](../standard-library/ios-functions.md#dec) ein Beispiel zur Verwendung für `hex`.

## <a name="internal"></a> internal

Bewirkt, dass ein Nummernzeichen linksbündig und die Zahl rechtsbündig ausgerichtet wird.

```cpp
ios_base& internal(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt aus dem *str* abgeleitet ist.

### <a name="remarks"></a>Hinweise

Durch [showpos](../standard-library/ios-functions.md#showpos) zeigt das Nummernzeichen für positive Zahlen an.

Der Manipulator ruft `str` auf. [SETF](../standard-library/ios-base-class.md#setf)( [ios_base:: internal](../standard-library/ios-base-class.md#fmtflags), [ios_base:: adjustfield](../standard-library/ios-base-class.md#fmtflags)), und gibt dann zurück *str*.

### <a name="example"></a>Beispiel

```cpp
// ios_internal.cpp
// compile with: /EHsc
#include <iostream>
#include <iomanip>

int main( void )
{
   using namespace std;
   float i = -123.456F;
   cout.fill( '.' );
   cout << setw( 10 ) << i << endl;
   cout << setw( 10 ) << internal << i << endl;
}
```

```Output
..-123.456
-..123.456
```

## <a name="left"></a> left

Bewirkt, dass Text, der nicht so breit ist wie die Ausgabebreite, im Stream linksbündig angezeigt wird.

```cpp
ios_base& left(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt, von dem _*str* abgeleitet wird.

### <a name="remarks"></a>Hinweise

Der Manipulator ruft `str`.[ SETF](../standard-library/ios-base-class.md#setf)( `ios_base::left`, `ios_base::adjustfield`), und gibt dann zurück *str*.

### <a name="example"></a>Beispiel

```cpp
// ios_left.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   double f1= 5.00;
   cout.width( 20 );
   cout << f1 << endl;
   cout << left << f1 << endl;
}
```

```Output
                   5
5
```

## <a name="noboolalpha"></a> noboolalpha

Gibt an, dass Variablen des Typs [bool](../cpp/bool-cpp.md) im Stream als 1 oder 0 angezeigt werden.

```cpp
ios_base& noboolalpha(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt, von dem _*str* abgeleitet wird.

### <a name="remarks"></a>Hinweise

In der Standardeinstellung ist `noboolalpha` aktiviert.

`noboolalpha` Ruft effektiv `str`.[ Unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::boolalpha`), und gibt dann zurück *str*.

[boolalpha](../standard-library/ios-functions.md#boolalpha) kehrt den Effekt von `noboolalpha` um.

### <a name="example"></a>Beispiel

Unter [boolalpha](../standard-library/ios-functions.md#boolalpha) finden Sie ein Beispiel für die Verwendung von `noboolalpha`.

## <a name="noshowbase"></a> noshowbase

Deaktiviert die Angabe der Schreibweisenbasis, mit der eine Zahl angezeigt wird.

```cpp
ios_base& noshowbase(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt, von dem _*str* abgeleitet wird.

### <a name="remarks"></a>Hinweise

Standardmäßig ist `noshowbase` aktiviert. Verwenden Sie [showbase](../standard-library/ios-functions.md#showbase), um die Schreibweisenbasis von Zahlen zu kennzeichnen.

Der Manipulator ruft `str`.[ Unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::showbase`), und gibt dann zurück *str*.

### <a name="example"></a>Beispiel

Unter [showbase](../standard-library/ios-functions.md#showbase) finden Sie ein Beispiel zur Verwendung von `noshowbase`.

## <a name="noshowpoint"></a> noshowpoint

Zeigt nur den ganzzahligen Teil von Gleitkommazahlen an, dessen Bruchteil null ist.

```cpp
ios_base& noshowpoint(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt, von dem _*str* abgeleitet wird.

### <a name="remarks"></a>Hinweise

`noshowpoint` ist standardmäßig aktiviert; verwenden Sie [showpoint](../standard-library/ios-functions.md#showpoint) und [precision](../standard-library/ios-base-class.md#precision), um Nullen hinter dem Dezimaltrennzeichen angezeigt zu bekommen.

Der Manipulator ruft `str`.[ Unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::showpoint`), und gibt dann zurück *str*.

### <a name="example"></a>Beispiel

```cpp
// ios_noshowpoint.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   double f1= 5.000;
   cout << f1 << endl;   // noshowpoint is default
   cout.precision( 4 );
   cout << showpoint << f1 << endl;
   cout << noshowpoint << f1 << endl;
}
```

```Output
5
5.000
5
```

## <a name="noshowpos"></a> noshowpos

Bewirkt, dass positive Zahlen nicht explizit signiert werden.

```cpp
ios_base& noshowpos(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt, von dem _*str* abgeleitet wird.

### <a name="remarks"></a>Hinweise

Standardmäßig ist `noshowpos` aktiviert.

Der Manipulator ruft `str`.[ Unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::showps`), dann gibt *str*.

### <a name="example"></a>Beispiel

Unter [showpos](../standard-library/ios-functions.md#showpos) finden Sie ein Beispiel für die Verwendung von `noshowpos`.

## <a name="noskipws"></a> noskipws

Bewirkt, dass Leerzeichen vom Eingabestream gelesen werden.

```cpp
ios_base& noskipws(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt, von dem _*str* abgeleitet wird.

### <a name="remarks"></a>Hinweise

In der Standardeinstellung ist [skipws](../standard-library/ios-functions.md#skipws) aktiviert. Wenn im Eingabestream ein Leerzeichen erkannt wird, wird dadurch das Ende des Puffers markiert.

Der Manipulator ruft `str`.[ Unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::skipws`), und gibt dann zurück *str*.

### <a name="example"></a>Beispiel

```cpp
// ios_noskipws.cpp
// compile with: /EHsc
#include <iostream>
#include <string>

int main() {
   using namespace std;
   string s1, s2, s3;
   cout << "Enter three strings: ";
   cin >> noskipws >> s1 >> s2 >> s3;
   cout << "." << s1  << "." << endl;
   cout << "." << s2 << "." << endl;
   cout << "." << s3 << "." << endl;
}
```

## <a name="nounitbuf"></a> nounitbuf

Bewirkt, dass die Ausgabe gepuffert und verarbeitet wird, wenn der Puffer voll ist.

```cpp
ios_base& nounitbuf(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt, von dem _*str* abgeleitet wird.

### <a name="remarks"></a>Hinweise

[unitbuf](../standard-library/ios-functions.md#unitbuf) bewirkt, dass der Puffer verarbeitet wird, wenn dieser nicht leer ist.

Der Manipulator ruft `str`.[ Unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::unitbuf`), und gibt dann zurück *str*.

## <a name="nouppercase"></a>nouppercase

Gibt an, dass hexadezimale Ziffern und der Exponent in wissenschaftlicher Schreibweise in Kleinbuchstaben angezeigt werden.

```cpp
ios_base& nouppercase(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt, von dem _*str* abgeleitet wird.

### <a name="remarks"></a>Hinweise

Der Manipulator ruft `str`.[ Unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::uppercase`), und gibt dann zurück *str*.

### <a name="example"></a>Beispiel

Unter [uppercase](../standard-library/ios-functions.md#uppercase) finden Sie ein Beispiel für die Verwendung von `nouppercase`.

## <a name="oct"></a> oct

Gibt an, dass ganzzahlige Variablen in Basis-8-Schreibweise angezeigt werden.

```cpp
ios_base& oct(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt aus dem *str* abgeleitet ist.

### <a name="remarks"></a>Hinweise

Standardmäßig werden Ganzzahlvariablen in Basis-10-Schreibweise angezeigt. Ebenfalls verändern [dec](../standard-library/ios-functions.md#dec) und [hex](../standard-library/ios-functions.md#hex) die Anzeige von Ganzzahlvariablen.

Der Manipulator ruft `str`.[ SETF](../standard-library/ios-base-class.md#setf)( `ios_base::oct`, `ios_base::basefield`), und gibt dann zurück *str*.

### <a name="example"></a>Beispiel

Finden Sie unter [Dec](../standard-library/ios-functions.md#dec) ein Beispiel zur Verwendung für `oct`.

## <a name="right"></a> right

Bewirkt, dass Text, der nicht so breit ist wie die Ausgabebreite, im Stream rechtsbündig angezeigt wird.

```cpp
ios_base& right(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt aus dem *str* abgeleitet ist.

### <a name="remarks"></a>Hinweise

[left](../standard-library/ios-functions.md#left) modifiziert auch die Textausrichtung.

Der Manipulator ruft `str`.[ SETF](../standard-library/ios-base-class.md#setf)( `ios_base::right`, `ios_base::adjustfield`), und gibt dann zurück *str*.

### <a name="example"></a>Beispiel

```cpp
// ios_right.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   double f1= 5.00;
   cout << f1 << endl;
   cout.width( 20 );
   cout << f1 << endl;
   cout.width( 20 );
   cout << left << f1 << endl;
   cout.width( 20 );
   cout << f1 << endl;
   cout.width( 20 );
   cout << right << f1 << endl;
   cout.width( 20 );
   cout << f1 << endl;
}
```

```Output
5
                   5
5
5
                   5
                   5
```

## <a name="scientific"></a> scientific

Bewirkt, dass Gleitkommazahlen in wissenschaftlicher Schreibweise angezeigt werden.

```cpp
ios_base& scientific(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt, von dem _*str* abgeleitet wird.

### <a name="remarks"></a>Hinweise

Für Gleitkommazahlen ist die [fixed](../standard-library/ios-functions.md#fixed)-Schreibweise standardmäßig aktiviert.

Der Manipulator ruft `str`.[ SETF](../standard-library/ios-base-class.md#setf)( `ios_base::scientific`, `ios_base::floatfield`), und gibt dann zurück *str*.

### <a name="example"></a>Beispiel

```cpp
// ios_scientific.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   float i = 100.23F;

   cout << i << endl;
   cout << scientific << i << endl;
}
```

```Output
100.23
1.002300e+002
```

## <a name="showbase"></a> showbase

Gibt die Schreibweisenbasis an, mit der eine Zahl angezeigt wird.

```cpp
ios_base& showbase(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt, von dem _*str* abgeleitet wird.

### <a name="remarks"></a>Hinweise

Die Schreibweisenbasis einer Zahl kann mit [dec](../standard-library/ios-functions.md#dec), [oct](../standard-library/ios-functions.md#oct) und [hex](../standard-library/ios-functions.md#hex) geändert werden.

Der Manipulator ruft `str`.[ SETF](../standard-library/ios-base-class.md#setf)( `ios_base::showbase`), und gibt dann zurück *str*.

### <a name="example"></a>Beispiel

```cpp
// ios_showbase.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   int j = 100;

   cout << showbase << j << endl;   // dec is default
   cout << hex << j << showbase << endl;
   cout << oct << j << showbase << endl;

   cout << dec << j << noshowbase << endl;
   cout << hex << j << noshowbase << endl;
   cout << oct << j << noshowbase << endl;
}
```

```Output
100
0x64
0144
100
64
144
```

## <a name="showpoint"></a> showpoint

Zeigt den ganzzahligen Teil einer Gleitkommazahl und Ziffern rechts vom Dezimaltrennzeichen an, selbst wenn der Bruchteil null ist.

```cpp
ios_base& showpoint(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt, von dem _*str* abgeleitet wird.

### <a name="remarks"></a>Hinweise

[noshowpoint](../standard-library/ios-functions.md#noshowpoint) ist standardmäßig aktiviert.

Der Manipulator ruft `str`.[ SETF](../standard-library/ios-base-class.md#setf)( `ios_base::showpoint`), und gibt dann zurück *str*.

### <a name="example"></a>Beispiel

Unter [noshowpoint](../standard-library/ios-functions.md#noshowpoint) finden Sie ein Beispiel für die Verwendung von `showpoint`.

## <a name="showpos"></a> showpos

Bewirkt, dass positive Zahlen explizit signiert werden.

```cpp
ios_base& showpos(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt, von dem _*str* abgeleitet wird.

### <a name="remarks"></a>Hinweise

[noshowpos](../standard-library/ios-functions.md#noshowpos) ist die Standardeinstellung.

Der Manipulator ruft `str`.[ SETF](../standard-library/ios-base-class.md#setf)( `ios_base::showpos`), und gibt dann zurück *str*.

### <a name="example"></a>Beispiel

```cpp
// ios_showpos.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   int i = 1;

   cout << noshowpos << i << endl;   // noshowpos is default
   cout << showpos << i << endl;
}
```

```Output
1
+1
```

## <a name="skipws"></a> skipws

Bewirkt, dass Leerzeichen nicht vom Eingabestream gelesen werden.

```cpp
ios_base& skipws(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt, von dem _*str* abgeleitet wird.

### <a name="remarks"></a>Hinweise

In der Standardeinstellung ist `skipws` aktiviert. [noskipws](../standard-library/ios-functions.md#noskipws) bewirkt, dass Leerzeichen aus Eingabestream gelesen werden.

Der Manipulator ruft `str`.[ SETF](../standard-library/ios-base-class.md#setf)( `ios_base::skipws`), und gibt dann zurück *str*.

### <a name="example"></a>Beispiel

```cpp
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   char s1, s2, s3;
   cout << "Enter three characters: ";
   cin >> skipws >> s1 >> s2 >> s3;
   cout << "." << s1  << "." << endl;
   cout << "." << s2 << "." << endl;
   cout << "." << s3 << "." << endl;
}
```

```Input
1 2 3
```

```Output
Enter three characters: 1 2 3
.1.
.2.
.3.
```

## <a name="unitbuf"></a> unitbuf

Bewirkt, dass die Ausgabe verarbeitet wird, wenn der Puffer nicht leer ist.

```cpp
ios_base& unitbuf(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt aus dem *str* abgeleitet ist.

### <a name="remarks"></a>Hinweise

Bitte beachten Sie, dass `endl` auch den Puffer leert.

[nounitbuf](../standard-library/ios-functions.md#nounitbuf) ist standardmäßig aktiviert.

Der Manipulator ruft `str`.[ SETF](../standard-library/ios-base-class.md#setf)( [ios_base:: unitbuf](../standard-library/ios-base-class.md#fmtflags)), und gibt dann zurück *str*.

## <a name="uppercase"></a> uppercase

Gibt an, dass hexadezimale Ziffern und der Exponent in wissenschaftlicher Schreibweise in Großbuchstaben angezeigt werden.

```cpp
ios_base& uppercase(ios_base& str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Ein Verweis auf ein [ios_base](../standard-library/ios-base-class.md)-Objekt oder auf einen Typ, der von `ios_base` erbt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Objekt aus dem *str* abgeleitet ist.

### <a name="remarks"></a>Hinweise

[nouppercase](../standard-library/ios-functions.md#nouppercase) ist standardmäßig aktiviert.

Der Manipulator ruft `str`.[ SETF](../standard-library/ios-base-class.md#setf)( [ios_base:: uppercade](../standard-library/ios-base-class.md#fmtflags)), und gibt dann zurück *str*.

### <a name="example"></a>Beispiel

```cpp
// ios_uppercase.cpp
// compile with: /EHsc
#include <iostream>

int main( void )
{
   using namespace std;

   double i = 1.23e100;
   cout << i << endl;
   cout << uppercase << i << endl;

   int j = 10;
   cout << hex << nouppercase << j << endl;
   cout << hex << uppercase << j << endl;
}
```

```Output
1.23e+100
1.23E+100
a
A
```

## <a name="see-also"></a>Siehe auch

[\<ios>](../standard-library/ios.md)<br/>
