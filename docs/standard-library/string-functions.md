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
ms.openlocfilehash: 0089a7259601b766bff3b470c5ba23c1b9952fb6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
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

`is` Der Eingabedatenstrom, aus der ist eine Zeichenfolge extrahiert werden soll.

`str` Die Zeichenfolge, die in das die Zeichen aus dem Eingabestream gelesen werden.

`delim` Das Zeilentrennzeichen.

### <a name="return-value"></a>Rückgabewert

Der Eingabestream `is`.

### <a name="remarks"></a>Hinweise

Das mit `(1)` markierte Funktionssignaturpaar extrahiert Zeichen aus `is` bis `delim` gefunden wird, und speichert die Zeichen in `str`.

Das mit `(2)` markierte Funktionssignaturpaar verwendet „newline“ als Standard-Zeilentrennzeichen und verhält sich wie **getline**( `is`, `str`, `is`. `widen`(' `\n`')).

Die zweite Funktion jedes Paars ist analog zur ersten, um [rvalue-Verweise](../cpp/lvalues-and-rvalues-visual-cpp.md) zu unterstützen.

Die Extraktion wird beendet, sobald eines der folgenden Ereignisse eintritt:

- Das Ende der Datei; in diesem Fall wird das interne Statusflag von `is` auf `ios_base::eofbit` festgelegt.

- Nachdem die Funktion ein Element extrahiert hat, das im Vergleich **delim** entspricht; in diesem Fall wird das Element weder zurückgestellt noch an die gesteuerte Sequenz angefügt.

- Nachdem die Funktion `str.`[max_size](../standard-library/basic-string-class.md#max_size)-Elemente extrahiert hat; in diesem Fall wird das interne Statusflag von `is` auf `ios_base::failbit` festgelegt.

- Ein anderer als einer der oben genannten Fehler; in diesem Fall wird das interne Statusflag von `is` auf `ios_base::badbit` festgelegt.

Informationen zu internen Statusflags finden Sie unter [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

Wenn die Funktion keine Elemente extrahiert, wird das interne Statusflag von `is` auf `ios_base::failbit` festgelegt. In jedem Fall gibt `getline` `is` zurück.

Wenn eine Ausnahme ausgelöst wird, bleiben `is` und `str` in einem gültigen Zustand.

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

Konvertiert eine Zeichenfolge in ein `double`.

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
|`str`|Die zu konvertierende Zeichenfolge.|
|`idx`|Der Indexwert des ersten Zeichens ohne Konvertierung.|

### <a name="return-value"></a>Rückgabewert

Der `double`-Wert.

### <a name="remarks"></a>Hinweise

Mit der Funktion wird die Abfolge von Elementen in `str` in einen Wert `val` des Typs `double` konvertiert, als ob `strtod( str.c_str(), _Eptr)` aufgerufen wird, wobei `_Eptr` ein internes Objekt für die Funktion ist. Bei ` str.c_str() == *_Eptr` wird ein Objekt vom Typ `invalid_argument` ausgegeben. Wenn solch ein Aufruf `errno` festlegt, wird ein Objekt vom Typ `out_of_range` ausgegeben. Andernfalls gilt: Wenn `idx` kein NULL-Zeiger ist, speichert die Funktion `*_Eptr -  str.c_str()` in `*idx` und gibt `val` zurück.

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
|`str`|Die zu konvertierende Zeichenfolge.|
|`idx`|Der Indexwert des ersten Zeichens ohne Konvertierung.|

### <a name="return-value"></a>Rückgabewert

Der Float-Wert.

### <a name="remarks"></a>Hinweise

Mit der Funktion wird die Abfolge von Elementen in `str` in einen Wert `val` des Typs `float` konvertiert, als ob `strtof( str.c_str(), _Eptr)` aufgerufen wird, wobei `_Eptr` ein internes Objekt für die Funktion ist. Bei ` str.c_str() == *_Eptr` wird ein Objekt vom Typ `invalid_argument` ausgegeben. Wenn solch ein Aufruf `errno` festlegt, wird ein Objekt vom Typ `out_of_range` ausgegeben. Andernfalls gilt: Wenn `idx` kein NULL-Zeiger ist, speichert die Funktion `*_Eptr -  str.c_str()` in `*idx` und gibt `val` zurück.

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
|`str`|Die zu konvertierende Zeichenfolge.|
|`idx`|Enthält den Index des ersten Zeichens ohne Konvertierung bei der Rückgabe.|
|`base`|Die zu verwendende Zahlenbasis.|

### <a name="remarks"></a>Hinweise

Die Funktion `stoi` konvertiert die Zeichenfolge in `str` in einen Wert des Typs `int` und gibt den Wert zurück. Wenn beispielsweise die Zeichenfolge "10" übergeben wurde, ist der durch `stoi` zurückgegebene Wert die Ganzzahl 10.

`stoi` ähnelt der Funktion `strtol` bei Einzelbyte-Zeichen, wenn der Aufruf über `strtol( str.c_str(), _Eptr, idx)` erfolgt, wobei `_Eptr` ein internes Objekt der Funktion ist, oder `wcstol` bei Breitzeichen, wenn der Aufruf ähnlich über `wcstol(Str.c_str(), _Eptr, idx)` erfolgt. Weitere Informationen finden Sie unter [strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md).

Wenn `str.c_str() == *_Eptr`, `stoi` löst ein Objekt des Typs `invalid_argument`. Wenn bei solch einem Aufruf `errno` festgelegt wird oder der zurückgegebene Wert nicht als ein Objekt vom Typ `int` dargestellt werden kann, wird ein Objekt vom Typ `out_of_range` ausgegeben. Andernfalls gilt: Wenn `idx` kein NULL-Zeiger ist, speichert die Funktion `*_Eptr - str.c_str()` in `*idx`.

## <a name="stol"></a> stol

Konvertiert eine Zeichenfolge in ein `long`.

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
|`str`|Die zu konvertierende Zeichenfolge.|
|`idx`|Der Indexwert des ersten Zeichens ohne Konvertierung.|
|`base`|Die zu verwendende Zahlenbasis.|

### <a name="return-value"></a>Rückgabewert

Der lange ganzzahlige Wert.

### <a name="remarks"></a>Hinweise

Mit der Funktion wird die Abfolge von Elementen in `str` in einen Wert `val` des Typs `long` konvertiert, als ob `strtol( str.c_str(), _Eptr, idx)` aufgerufen wird, wobei `_Eptr` ein internes Objekt für die Funktion ist. Bei ` str.c_str() == *_Eptr` wird ein Objekt vom Typ `invalid_argument` ausgegeben. Wenn solch ein Aufruf `errno` festlegt, wird ein Objekt vom Typ `out_of_range` ausgegeben. Andernfalls gilt: Wenn `idx` kein NULL-Zeiger ist, speichert die Funktion `*_Eptr -  str.c_str()` in `*idx` und gibt `val` zurück.

## <a name="stold"></a> stold

Konvertiert eine Zeichenfolge in ein `long double`.

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
|`str`|Die zu konvertierende Zeichenfolge.|
|`idx`|Der Indexwert des ersten Zeichens ohne Konvertierung.|

### <a name="return-value"></a>Rückgabewert

Der `long double`-Wert.

### <a name="remarks"></a>Hinweise

Mit der Funktion wird die Abfolge von Elementen in `str` in einen Wert `val` des Typs `long double` konvertiert, als ob `strtold( str.c_str(), _Eptr)` aufgerufen wird, wobei `_Eptr` ein internes Objekt für die Funktion ist. Bei ` str.c_str() == *_Eptr` wird ein Objekt vom Typ `invalid_argument` ausgegeben. Wenn solch ein Aufruf `errno` festlegt, wird ein Objekt vom Typ `out_of_range` ausgegeben. Andernfalls gilt: Wenn `idx` kein NULL-Zeiger ist, speichert die Funktion `*_Eptr -  str.c_str()` in `*idx` und gibt `val` zurück.

## <a name="stoll"></a> stoll

Konvertiert eine Zeichenfolge in ein `long long`.

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
|`str`|Die zu konvertierende Zeichenfolge.|
|`idx`|Der Indexwert des ersten Zeichens ohne Konvertierung.|
|`base`|Die zu verwendende Zahlenbasis.|

### <a name="return-value"></a>Rückgabewert

Der `long long`-Wert.

### <a name="remarks"></a>Hinweise

Mit der Funktion wird die Abfolge von Elementen in `str` in einen Wert `val` des Typs `long long` konvertiert, als ob `strtoll( str.c_str(), _Eptr, idx)` aufgerufen wird, wobei `_Eptr` ein internes Objekt für die Funktion ist. Bei ` str.c_str() == *_Eptr` wird ein Objekt vom Typ `invalid_argument` ausgegeben. Wenn solch ein Aufruf `errno` festlegt, wird ein Objekt vom Typ `out_of_range` ausgegeben. Andernfalls gilt: Wenn `idx` kein NULL-Zeiger ist, speichert die Funktion `*_Eptr -  str.c_str()` in `*idx` und gibt `val` zurück.

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
|`str`|Die zu konvertierende Zeichenfolge.|
|`idx`|Der Indexwert des ersten Zeichens ohne Konvertierung.|
|`base`|Die zu verwendende Zahlenbasis.|

### <a name="return-value"></a>Rückgabewert

Der lange ganzzahlige Wert ohne Vorzeichen.

### <a name="remarks"></a>Hinweise

Mit der Funktion wird die Abfolge von Elementen in `str` in einen Wert `val` des Typs `unsigned long` konvertiert, als ob `strtoul( str.c_str(), _Eptr, idx)` aufgerufen wird, wobei `_Eptr` ein internes Objekt für die Funktion ist. Bei ` str.c_str() == *_Eptr` wird ein Objekt vom Typ `invalid_argument` ausgegeben. Wenn solch ein Aufruf `errno` festlegt, wird ein Objekt vom Typ `out_of_range` ausgegeben. Andernfalls gilt: Wenn `idx` kein NULL-Zeiger ist, speichert die Funktion `*_Eptr -  str.c_str()` in `*idx` und gibt `val` zurück.

## <a name="stoull"></a> stoull

Konvertiert eine Zeichenfolge in ein `unsigned long long`.

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
|`str`|Die zu konvertierende Zeichenfolge.|
|`idx`|Der Indexwert des ersten Zeichens ohne Konvertierung.|
|`base`|Die zu verwendende Zahlenbasis.|

### <a name="return-value"></a>Rückgabewert

Der `unsigned long long`-Wert.

### <a name="remarks"></a>Hinweise

Mit der Funktion wird die Abfolge von Elementen in `str` in einen Wert `val` des Typs `unsigned long long` konvertiert, als ob `strtoull( str.c_str(), _Eptr, idx)` aufgerufen wird, wobei `_Eptr` ein internes Objekt für die Funktion ist. Bei ` str.c_str() == *_Eptr` wird ein Objekt vom Typ `invalid_argument` ausgegeben. Wenn solch ein Aufruf `errno` festlegt, wird ein Objekt vom Typ `out_of_range` ausgegeben. Andernfalls gilt: Wenn `idx` kein NULL-Zeiger ist, speichert die Funktion `*_Eptr -  str.c_str()` in `*idx` und gibt `val` zurück.

## <a name="swap"></a>  swap

Tauscht die Arrays von Zeichen für zwei Zeichenfolgen aus.

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

`left` Eine Zeichenfolge, deren Elemente mit denen einer anderen Zeichenfolge ausgetauscht werden sollen.

`right` Die andere Zeichenfolge zurück, dessen Elemente mit der ersten Zeichenfolge ausgetauscht werden sollen.

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
|`Val`|Der zu konvertierende Wert.|

### <a name="return-value"></a>Rückgabewert

Das `string`, das den Wert darstellt.

### <a name="remarks"></a>Hinweise

Mit der Funktion wird `Val` in eine Sequenz von Elementen konvertiert, die in einem für die Funktion internen `Buf`-Arrayobjekt gespeichert werden, als würde `sprintf(Buf, Fmt, Val)` aufgerufen, wobei `Fmt` Folgendem entspricht:

- `"%d"`, wenn `Val` den Typ `int` aufweist

- `"%u"`, wenn `Val` den Typ `unsigned int` aufweist

- `"%ld"`, wenn `Val` den Typ `long` aufweist

- `"%lu"`, wenn `Val` den Typ `unsigned long` aufweist

- `"%lld"`, wenn `Val` den Typ `long long` aufweist

- `"%llu"`, wenn `Val` den Typ `unsigned long long` aufweist

- `"%f"`, wenn `Val` den Typ `float` oder `double` aufweist

- `"%Lf"`, wenn `Val` den Typ `long double` aufweist

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

- `L"%d"`, wenn `Val` den Typ `int` aufweist

- `L"%u"`, wenn `Val` den Typ `unsigned int` aufweist

- `L"%ld"`, wenn `Val` den Typ `long` aufweist

- `L"%lu"`, wenn `Val` den Typ `unsigned long` aufweist

- `L"%lld"`, wenn `Val` den Typ `long long` aufweist

- `L"%llu"`, wenn `Val` den Typ `unsigned long long` aufweist

- `L"%f"`, wenn `Val` den Typ `float` oder `double` aufweist

- `L"%Lf"`, wenn `Val` den Typ `long double` aufweist

Die Funktion gibt `wstring(Buf)` zurück.

## <a name="see-also"></a>Siehe auch

[\<string>](../standard-library/string.md)<br/>
