---
title: '&lt;string&gt;-Funktionen | Microsoft-Dokumentationen'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- string/std::getline
- string/std::stod
- string/std::stof
- string/std::stoi
- string/std::stol
- string/std::stold
- string/std::stoll
- string/std::stoul
- string/std::stoull
- string/std::swap
- string/std::to_string
- string/std::to_wstring
ms.assetid: 1a4ffd11-dce5-4cc6-a043-b95de034c7c4
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::getline [C++]
- std::stod [C++]
- std::stof [C++]
- std::stoi [C++]
- std::stol [C++]
- std::stold [C++]
- std::stoll [C++]
- std::stoul [C++]
- std::stoull [C++]
- std::swap [C++]
- std::to_string [C++]
- std::to_wstring [C++]
ms.workload:
- cplusplus
ms.openlocfilehash: a80749e6eaffe02d748167f462580782a2755f89
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106742"
---
# <a name="ltstringgt-functions"></a>&lt;string&gt;-Funktionen

||||
|-|-|-|
|[getline](#getline)|[stod](#stod)|[stof](#stof)|
|[stoi](#stoi)|[stol](#stol)|[stold](#stold)|
|[stoll](#stoll)|[stoul](#stoul)|[stoull](#stoull)|
|[swap](#swap)|[to_string](#to_string)|[to_wstring](#to_wstring)|

## <a name="getline"></a> getline

Extrahiert Zeichenfolgen zeilenweise aus dem Eingabestream.

```cpp
// (1) delimiter as parameter
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& is,
    basic_string<CharType, Traits, Allocator>& str,
    CharType delim);


template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>&& is,
    basic_string<CharType, Traits, Allocator>& str,
    const CharType delim);


// (2) default delimiter used
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& is,
    basic_string<CharType, Traits, Allocator>& str);


template <class Allocator, class Traits, class Allocator>
basic_istream<Allocator, Traits>& getline(
    basic_istream<Allocator, Traits>&& is,
    basic_string<Allocator, Traits, Allocator>& str);
```

### <a name="parameters"></a>Parameter

*is*<br/>
Der Eingabestream, aus dem eine Zeichenfolge extrahiert werden soll.

*str*<br/>
Die Zeichenfolge, in die die Zeichen aus dem Eingabestream gelesen werden.

*Delim*<br/>
Das Zeilentrennzeichen.

### <a name="return-value"></a>Rückgabewert

Der Eingabedatenstrom *ist*.

### <a name="remarks"></a>Hinweise

Markierte funktionssignaturpaar `(1)` Extrahieren von Zeichen aus *ist* bis *Delim* gefunden wird, speichern sie in *str*.

Markierte funktionssignaturpaar `(2)` verwendet "Newline" als Standard-Zeilentrennzeichen und verhält sich wie **Getline**(`is`, `str`, `is`. `widen`(' `\n`')).

Die zweite Funktion jedes Paars ist analog zur ersten, um [rvalue-Verweise](../cpp/lvalues-and-rvalues-visual-cpp.md) zu unterstützen.

Die Extraktion wird beendet, sobald eines der folgenden Ereignisse eintritt:

- Am Ende der Datei in diesem Fall das interne Statusflag von *ist* nastaven NA hodnotu `ios_base::eofbit`.

- Nachdem die Funktion ein Element extrahiert hat, das `delim` entspricht; in diesem Fall wird das Element weder zurückgestellt noch an die kontrollierte Sequenz angefügt.

- Nachdem die Funktion extrahiert `str.` [Max_size](../standard-library/basic-string-class.md#max_size) Elemente, in dem Fall das interne Statusflag von *ist* nastaven NA hodnotu `ios_base::failbit`.

- Ein anderer Fehler als die oben aufgeführten, in diesem Fall das interne Statusflag von *ist* auf festgelegt ist `ios_base::badbit`

Informationen zu internen Statusflags finden Sie unter [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

Wenn die Funktion keine Elemente extrahiert, das interne Statusflag von *ist* nastaven NA hodnotu `ios_base::failbit`. In jedem Fall `getline` gibt *ist*.

Wenn eine Ausnahme ausgelöst wird, *ist* und *str* , die in einem gültigen Zustand belassen werden.

### <a name="example"></a>Beispiel

Der folgende Code zeigt `getline()` in zwei Modi: zuerst mit dem Standardtrennzeichen (newline) und dann mit einem Leerzeichen als Trennzeichen. Mit dem Dateiendezeichen (STRG-Z auf der Tastatur) wird die Beendigung der while-Schleifen gesteuert. Dadurch wird das interne Statusflag von `cin` auf `eofbit` festgelegt; dies muss mit [basic_ios::clear()](../standard-library/basic-ios-class.md#clear) gelöscht werden, damit die zweite while-Schleife ordnungsgemäß ausgeführt werden kann.

```cpp
// compile with: /EHsc /W4
#include <string>
#include <iostream>
#include <vector>

using namespace std;

int main()
{
    string str;
    vector<string> v1;
    cout << "Enter a sentence, press ENTER between sentences. (Ctrl-Z to stop): " << endl;
    // Loop until end-of-file (Ctrl-Z) is input, store each sentence in a vector.
    // Default delimiter is the newline character.
    while (getline(cin, str)) {
        v1.push_back(str);
    }

    cout << "The following input was stored with newline delimiter:" << endl;
    for (const auto& p : v1) {
        cout << p << endl;
    }

    cin.clear();

    vector<string> v2;
    // Now try it with a whitespace delimiter
    while (getline(cin, str, ' ')) {
        v2.push_back(str);
    }

    cout << "The following input was stored with whitespace as delimiter:" << endl;
    for (const auto& p : v2) {
        cout << p << endl;
    }
}

```

## <a name="stod"></a> stod

Konvertiert eine Zeichenfolge in eine **doppelte**.

```cpp
double stod(
    const string& str,
    size_t* idx = 0);

double stod(
    const wstring& str,
    size_t* idx = 0
;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*str*|Die zu konvertierende Zeichenfolge.|
|*IDX*|Der Indexwert des ersten Zeichens ohne Konvertierung.|

### <a name="return-value"></a>Rückgabewert

Die **doppelte** Wert.

### <a name="remarks"></a>Hinweise

Die Funktion konvertiert die Reihenfolge der Elemente in *str* auf einen Wert `val` des Typs **doppelte** als wäre `strtod( str.c_str(), _Eptr)`, wobei `_Eptr` ist ein Objekt an die Funktion internen. Bei ` str.c_str() == *_Eptr` wird ein Objekt vom Typ `invalid_argument` ausgegeben. Wenn solch ein Aufruf `errno` festlegt, wird ein Objekt vom Typ `out_of_range` ausgegeben. Andernfalls gilt: Wenn *Idx* ist kein null-Zeiger, speichert die Funktion `*_Eptr -  str.c_str()` in `*idx` und gibt `val`.

## <a name="stof"></a> stof

Konvertiert eine Zeichenfolge in eine Float-Zahl.

```cpp
float stof(
    const string& str,
    size_t* idx = 0);

float stof(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*str*|Die zu konvertierende Zeichenfolge.|
|*IDX*|Der Indexwert des ersten Zeichens ohne Konvertierung.|

### <a name="return-value"></a>Rückgabewert

Der Float-Wert.

### <a name="remarks"></a>Hinweise

Die Funktion konvertiert die Reihenfolge der Elemente in *str* auf einen Wert `val` des Typs **"float"** als wäre `strtof( str.c_str(), _Eptr)`, wobei `_Eptr` ist ein Objekt an die Funktion internen. Bei ` str.c_str() == *_Eptr` wird ein Objekt vom Typ `invalid_argument` ausgegeben. Wenn solch ein Aufruf `errno` festlegt, wird ein Objekt vom Typ `out_of_range` ausgegeben. Andernfalls gilt: Wenn *Idx* ist kein null-Zeiger, speichert die Funktion `*_Eptr -  str.c_str()` in `*idx` und gibt `val`.

## <a name="stoi"></a> stoi

Konvertiert eine Zeichenfolge in eine Ganzzahl.

```cpp
int stoi(
    const string& str,
    size_t* idx = 0,
    int base = 10);

int stoi(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="return-value"></a>Rückgabewert

Der Ganzzahlwert.

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*str*|Die zu konvertierende Zeichenfolge.|
|*IDX*|Enthält den Index des ersten Zeichens ohne Konvertierung bei der Rückgabe.|
|*base*|Die zu verwendende Zahlenbasis.|

### <a name="remarks"></a>Hinweise

Die Funktion `stoi` konvertiert die Sequenz von Zeichen in *str* auf einen Wert vom Typ **Int** und den Wert zurückgibt. Wenn beispielsweise die Zeichenfolge "10" übergeben wurde, ist der durch `stoi` zurückgegebene Wert die Ganzzahl 10.

`stoi` ähnelt der Funktion `strtol` bei Einzelbyte-Zeichen, wenn der Aufruf über `strtol( str.c_str(), _Eptr, idx)` erfolgt, wobei `_Eptr` ein internes Objekt der Funktion ist, oder `wcstol` bei Breitzeichen, wenn der Aufruf ähnlich über `wcstol(Str.c_str(), _Eptr, idx)` erfolgt. Weitere Informationen finden Sie unter [strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md).

Wenn `str.c_str() == *_Eptr`, `stoi` löst ein Objekt des Typs `invalid_argument`. Wenn solch ein Aufruf festgelegt wäre `errno`, oder wenn der zurückgegebene Wert als ein Objekt des Typs dargestellt werden kann **Int**, löst ein Objekt des Typs `out_of_range`. Andernfalls gilt: Wenn *Idx* ist kein null-Zeiger, speichert die Funktion `*_Eptr - str.c_str()` in `*idx`.

## <a name="stol"></a> stol

Konvertiert eine Zeichenfolge in eine **lange**.

```cpp
long stol(
    const string& str,
    size_t* idx = 0,
    int base = 10);

long stol(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*str*|Die zu konvertierende Zeichenfolge.|
|*IDX*|Der Indexwert des ersten Zeichens ohne Konvertierung.|
|*base*|Die zu verwendende Zahlenbasis.|

### <a name="return-value"></a>Rückgabewert

Der lange ganzzahlige Wert.

### <a name="remarks"></a>Hinweise

Die Funktion konvertiert die Reihenfolge der Elemente in *str* auf einen Wert `val` des Typs **lange** als wäre `strtol( str.c_str(), _Eptr, idx)`, wobei `_Eptr` ist ein Objekt an die Funktion internen. Bei ` str.c_str() == *_Eptr` wird ein Objekt vom Typ `invalid_argument` ausgegeben. Wenn solch ein Aufruf `errno` festlegt, wird ein Objekt vom Typ `out_of_range` ausgegeben. Andernfalls gilt: Wenn *Idx* ist kein null-Zeiger, speichert die Funktion `*_Eptr -  str.c_str()` in `*idx` und gibt `val`.

## <a name="stold"></a> stold

Konvertiert eine Zeichenfolge in eine **long double**.

```cpp
double stold(
    const string& str,
    size_t* idx = 0);

double stold(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*str*|Die zu konvertierende Zeichenfolge.|
|*IDX*|Der Indexwert des ersten Zeichens ohne Konvertierung.|

### <a name="return-value"></a>Rückgabewert

Die **long double** Wert.

### <a name="remarks"></a>Hinweise

Die Funktion konvertiert die Reihenfolge der Elemente in *str* auf einen Wert `val` des Typs **long double** als wäre `strtold( str.c_str(), _Eptr)`, wobei `_Eptr` ist ein Objekt an die Funktion internen. Bei ` str.c_str() == *_Eptr` wird ein Objekt vom Typ `invalid_argument` ausgegeben. Wenn solch ein Aufruf `errno` festlegt, wird ein Objekt vom Typ `out_of_range` ausgegeben. Andernfalls gilt: Wenn *Idx* ist kein null-Zeiger, speichert die Funktion `*_Eptr -  str.c_str()` in `*idx` und gibt `val`.

## <a name="stoll"></a> stoll

Konvertiert eine Zeichenfolge in eine **long long**.

```cpp
long long stoll(
    const string& str,
    size_t* idx = 0,
    int base = 10);

long long stoll(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*str*|Die zu konvertierende Zeichenfolge.|
|*IDX*|Der Indexwert des ersten Zeichens ohne Konvertierung.|
|*base*|Die zu verwendende Zahlenbasis.|

### <a name="return-value"></a>Rückgabewert

Die **long long** Wert.

### <a name="remarks"></a>Hinweise

Die Funktion konvertiert die Reihenfolge der Elemente in *str* auf einen Wert `val` des Typs **long long** als wäre `strtoll( str.c_str(), _Eptr, idx)`, wobei `_Eptr` ist ein Objekt an die Funktion internen. Bei ` str.c_str() == *_Eptr` wird ein Objekt vom Typ `invalid_argument` ausgegeben. Wenn solch ein Aufruf `errno` festlegt, wird ein Objekt vom Typ `out_of_range` ausgegeben. Andernfalls gilt: Wenn *Idx* ist kein null-Zeiger, speichert die Funktion `*_Eptr -  str.c_str()` in `*idx` und gibt `val`.

## <a name="stoul"></a> stoul

Konvertiert eine Zeichenfolge in einen langen Wert ohne Vorzeichen.

```cpp
unsigned long stoul(
    const string& str,
    size_t* idx = 0,
    int base = 10);

unsigned long stoul(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*str*|Die zu konvertierende Zeichenfolge.|
|*IDX*|Der Indexwert des ersten Zeichens ohne Konvertierung.|
|*base*|Die zu verwendende Zahlenbasis.|

### <a name="return-value"></a>Rückgabewert

Der lange ganzzahlige Wert ohne Vorzeichen.

### <a name="remarks"></a>Hinweise

Die Funktion konvertiert die Reihenfolge der Elemente in *str* auf einen Wert `val` des Typs **unsigned long** als wäre `strtoul( str.c_str(), _Eptr, idx)`, wobei `_Eptr` ist ein Objekt an die Funktion internen . Bei ` str.c_str() == *_Eptr` wird ein Objekt vom Typ `invalid_argument` ausgegeben. Wenn solch ein Aufruf `errno` festlegt, wird ein Objekt vom Typ `out_of_range` ausgegeben. Andernfalls gilt: Wenn *Idx* ist kein null-Zeiger, speichert die Funktion `*_Eptr -  str.c_str()` in `*idx` und gibt `val`.

## <a name="stoull"></a> stoull

Konvertiert eine Zeichenfolge in eine **long long ohne Vorzeichen**.

```cpp
unsigned long long stoull(
    const string& str,
    size_t* idx = 0,
    int base = 10);

unsigned long long stoull(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*str*|Die zu konvertierende Zeichenfolge.|
|*IDX*|Der Indexwert des ersten Zeichens ohne Konvertierung.|
|*base*|Die zu verwendende Zahlenbasis.|

### <a name="return-value"></a>Rückgabewert

Die **long long ohne Vorzeichen** Wert.

### <a name="remarks"></a>Hinweise

Die Funktion konvertiert die Reihenfolge der Elemente in *str* auf einen Wert `val` des Typs **long long ohne Vorzeichen** als wäre `strtoull( str.c_str(), _Eptr, idx)`, wobei `_Eptr` ist ein Objekt innerhalb der -Funktion. Bei ` str.c_str() == *_Eptr` wird ein Objekt vom Typ `invalid_argument` ausgegeben. Wenn solch ein Aufruf `errno` festlegt, wird ein Objekt vom Typ `out_of_range` ausgegeben. Andernfalls gilt: Wenn *Idx* ist kein null-Zeiger, speichert die Funktion `*_Eptr -  str.c_str()` in `*idx` und gibt `val`.

## <a name="swap"></a>  swap

Tauscht die Arrays von Zeichen für zwei Zeichenfolgen aus.

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Eine Zeichenfolge, deren Elemente mit denen einer anderen Zeichenfolge ausgetauscht werden sollen.

*right*<br/>
Die andere Zeichenfolge, deren Elemente mit der ersten Zeichenfolge ausgetauscht werden sollen.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion führt die spezialisierte Memberfunktion *linken*.[ Swap](../standard-library/basic-string-class.md#swap)(*rechten*) für Zeichenfolgen wird die Konstante Komplexität gewährleistet wird.

### <a name="example"></a>Beispiel

```cpp
// string_swap.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // Declaring an object of type basic_string<char>
   string s1 ( "Tweedledee" );
   string s2 ( "Tweedledum" );
   cout << "Before swapping string s1 and s2:" << endl;
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   swap ( s1 , s2 );
   cout << "\nAfter swapping string s1 and s2:" << endl;
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;
}
```

```Output
Before swapping string s1 and s2:
The basic_string s1 = Tweedledee.
The basic_string s2 = Tweedledum.

After swapping string s1 and s2:
The basic_string s1 = Tweedledum.
The basic_string s2 = Tweedledee.
```

## <a name="to_string"></a> to_string

Konvertiert einen Wert in einen `string`-Wert.

```cpp
string to_string(int Val);
string to_string(unsigned int Val);
string to_string(long Val);
string to_string(unsigned long Val);
string to_string(long long Val);
string to_string(unsigned long long Val);
string to_string(float Val);
string to_string(double Val);
string to_string(long double Val);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*val*|Der zu konvertierende Wert.|

### <a name="return-value"></a>Rückgabewert

Das `string`, das den Wert darstellt.

### <a name="remarks"></a>Hinweise

Die Funktion konvertiert *Val* in eine Sequenz von in einem Arrayobjekt gespeicherten Elementen `Buf` intern an die Funktion, als wäre `sprintf(Buf, Fmt, Val)`, wobei `Fmt` ist

- `"%d"` Wenn `Val` weist den Typ **Int**

- `"%u"` Wenn `Val` weist den Typ **ganze Zahl ohne Vorzeichen**

- `"%ld"` Wenn `Val` weist den Typ **lange**

- `"%lu"` Wenn `Val` weist den Typ **unsigned long**

- `"%lld"` Wenn `Val` weist den Typ **long long**

- `"%llu"` Wenn `Val` weist den Typ **long long ohne Vorzeichen**

- `"%f"` Wenn `Val` weist den Typ **"float"** oder **double**

- `"%Lf"` Wenn `Val` weist den Typ **long double**

Die Funktion gibt `string(Buf)` zurück.

## <a name="to_wstring"></a> to_wstring

Konvertiert einen Wert in eine breite Zeichenfolge.

```cpp
wstring to_wstring(int Val);
wstring to_wstring(unsigned int Val);
wstring to_wstring(long Val);
wstring to_wstring(unsigned long Val);
wstring to_wstring(long long Val);
wstring to_wstring(unsigned long long Val);
wstring to_wstring(float Val);
wstring to_wstring(double Val);
wstring to_wstring(long double Val);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`Val`|Der zu konvertierende Wert.|

### <a name="return-value"></a>Rückgabewert

Die breite Zeichenfolge, die den Wert darstellt.

### <a name="remarks"></a>Hinweise

Mit der Funktion wird `Val` in eine Sequenz von Elementen konvertiert, die in einem für die Funktion internen `Buf`-Arrayobjekt gespeichert werden, als würde `swprintf(Buf, Len, Fmt, Val)` aufgerufen, wobei `Fmt` Folgendem entspricht:

- `L"%d"` Wenn `Val` weist den Typ **Int**

- `L"%u"` Wenn `Val` weist den Typ **ganze Zahl ohne Vorzeichen**

- `L"%ld"` Wenn `Val` weist den Typ **lange**

- `L"%lu"` Wenn `Val` weist den Typ **unsigned long**

- `L"%lld"` Wenn `Val` weist den Typ **long long**

- `L"%llu"` Wenn `Val` weist den Typ **long long ohne Vorzeichen**

- `L"%f"` Wenn `Val` weist den Typ **"float"** oder **double**

- `L"%Lf"` Wenn `Val` weist den Typ **long double**

Die Funktion gibt `wstring(Buf)` zurück.

## <a name="see-also"></a>Siehe auch

[\<string>](../standard-library/string.md)<br/>
