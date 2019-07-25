---
title: path-Klasse
ms.date: 09/27/2018
f1_keywords:
- filesystem/std::experimental::filesystem::path
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
ms.openlocfilehash: 10c865aa2bc2431850c69e9dfedbef37414b2cb9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455096"
---
# <a name="path-class"></a>path-Klasse

Die **path** -Klasse speichert ein Objekt vom `string_type`Typ, `myname` das hier zur Veranschaulichung aufgerufen wird und als Pfadname verwendet werden kann. `string_type`ist ein Synonym für `basic_string<value_type>`, wobei `value_type` ein Synonym für **wchar_t** unter Windows oder **char** auf POSIX ist.

Weitere Informationen und Codebeispiele finden Sie unter [Datei System NavigationC++()](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Syntax

```cpp
class path;
```

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[path](#path)|Erstellt ein Objekt vom Typ `path`.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[const_iterator](#const_iterator)|Ein Synonym für `iterator`.|
|[Iterator](#iterator)|Ein bidirektionaler konstanter Iterator, der `path` die Komponenten `myname`von festlegt.|
|[string_type](#string_type)|Der Typ ist ein Synonym für `basic_string<value_type>`.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[append](#append)|Fügt die angegebene Sequenz an, `mypath`konvertiert und fügt eine preferred_separator nach Bedarf ein.|
|[assign](#assign)|Ersetzt `mypath` durch die angegebene Sequenz, konvertiert nach Bedarf.|
|[begin](#begin)|Gibt einen `path::iterator` -Wert zurück, der das erste Pfad Element im Pfadnamen angibt, falls vorhanden.|
|[c_str](#c_str)|Gibt einen Zeiger auf das erste Zeichen in `mypath`zurück.|
|[clear](#clear)|Führt `mypath.clear()`aus.|
|[compare](#compare)|Gibt Vergleichswerte zurück.|
|[concat](#compare)|Fügt die angegebene Sequenz nach Bedarf `mypath`an, konvertiert (aber kein Trennzeichen) an.|
|[empty](#empty)|Gibt `mypath.empty()`zurück.|
|[end](#end)|Gibt einen Sequenz Ende-Iterator vom Typ `iterator`zurück.|
|[weiterung](#extension)|Gibt das Suffix von `filename()`zurück.|
|[filename](#filename)|Gibt die Stammverzeichniskomponente von „myname“ zurück, insbesondere `empty() path() : *--end()`. Die Komponente kann leer sein.|
|[generic_string](#generic_string)|Gibt `this->string<Elem, Traits, Alloc>(al)` zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird (unter Windows).|
|[generic_u16string](#generic_u16string)|Gibt `u16string()` zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird (unter Windows).|
|[generic_u32string](#generic_u32string)|Gibt `u32string()` zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird (unter Windows).|
|[generic_u8string](#generic_u8string)|Gibt `u8string()` zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird (unter Windows).|
|[generic_wstring](#generic_wstring)|Gibt `wstring()` zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird (unter Windows).|
|[has_extension](#has_extension)|Gibt `!extension().empty()`zurück.|
|[has_filename](#has_filename)|Gibt `!filename().empty()`zurück.|
|[has_parent_path](#has_parent_path)|Gibt `!parent_path().empty()`zurück.|
|[has_relative_path](#has_relative_path)|Gibt `!relative_path().empty()`zurück.|
|[has_root_directory](#has_root_directory)|Gibt `!root_directory().empty()`zurück.|
|[has_root_name](#has_root_name)|Gibt `!root_name().empty()`zurück.|
|[has_root_path](#has_root_path)|Gibt `!root_path().empty()`zurück.|
|[has_stem](#has_stem)|Gibt `!stem().empty()`zurück.|
|[is_absolute](#is_absolute)|Für Windows gibt die Funktion zurück `has_root_name() && has_root_directory()`. Für POSIX gibt die Funktion zurück `has_root_directory()`.|
|[is_relative](#is_relative)|Gibt `!is_absolute()`zurück.|
|[make_preferred](#make_preferred)|Konvertiert jedes Trennzeichen nach Bedarf in eine preferred_separator.|
|[native](#native)|Gibt `myname`zurück.|
|[parent_path](#parent_path)|Gibt die übergeordnete Pfadkomponente `myname`von zurück.|
|[preferred_separator](#preferred_separator)|Das konstante Objekt gibt je nach Betriebssystem des Hosts das bevorzugte Zeichen zum Trennen von Pfadkomponenten zurück. |
|[relative_path](#relative_path)|Gibt die relative Pfadkomponente von `myname`zurück. |
|[remove_filename](#remove_filename)|Entfernt den Dateinamen.|
|[replace_extension](#replace_extension)|Ersetzt die Erweiterung von `myname`. |
|[replace_filename](#replace_filename)|Ersetzt den Dateinamen.|
|[root_directory](#root_directory)|Gibt die Stammverzeichnis Komponente von `myname`zurück. |
|[root_name](#root_name)|Gibt die Stamm Namen Komponente von `myname`zurück. |
|[root_path](#root_path)|Gibt die Stamm Pfadkomponente von `myname`zurück.|
|[stem](#stem)|Gibt die `stem` Komponente von `myname`zurück.|
|[string](#string)|Konvertiert die in `mypath`gespeicherte Sequenz.|
|[swap](#swap)|Führt `swap(mypath, right.mypath)`aus.|
|[u16string](#u16string)|Konvertiert die in `mypath` gespeicherte Sequenz in UTF-16 und gibt Sie in einem Objekt vom Typ `u16string`zurück.|
|[u32string](#u32string)|Konvertiert die in `mypath` gespeicherte Sequenz in UTF-32 und gibt Sie in einem Objekt vom Typ `u32string`zurück.|
|[u8string](#u8string)|Konvertiert die in `mypath` gespeicherte Sequenz in UTF-8 und gibt Sie in einem Objekt vom Typ `u8string`zurück.|
|[value_type](#value_type)|Der Typ beschreibt die Pfadelemente, die vom Hostbetriebssystem bevorzugt werden.|
|[wstring](#wstring)|Konvertiert die in `mypath` gespeicherte Sequenz in die Codierung, die vom Host System für eine `wchar_t` Sequenz bevorzugt wird, und gibt diese in einem Objekt `wstring`vom Typ gespeicherten zurück.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator=](#op_as)|Ersetzt die Elemente des Pfads durch eine Kopie eines anderen Pfades.|
|[operator+=](#op_add)|Verschiedene `concat` Ausdrücke.|
|[operator/=](#op_divide)|Verschiedene `append` Ausdrücke.|
|[Operator string_type](#op_string)|Gibt `myname`zurück.|

## <a name="requirements"></a>Anforderungen

**Header:** \<Dateisystem >

**Namespace:** std::experimental::filesystem

## <a name="append"></a>Path:: Append

Fügt die angegebene Sequenz an, `mypath`konvertiert und fügt bei Bedarf `preferred_separator` ein ein.

```cpp
template <class Source>
path& append(const Source& source);

template <class InIt>
path& append(InIt first, InIt last);
```

### <a name="parameters"></a>Parameter

*Ausgangs*\
Angegebene Sequenz.

*erstes*\
Beginn der angegebenen Sequenz.

*letzten*\
Ende der angegebenen Sequenz.

## <a name="assign"></a>Path:: Assign

Ersetzt `mypath` durch die angegebene Sequenz, konvertiert nach Bedarf.

```cpp
template <class Source>
path& assign(const Source& source);

template <class InIt>
path& assign(InIt first, InIt last);
```

### <a name="parameters"></a>Parameter

*Ausgangs*\
Angegebene Sequenz.

*erstes*\
Beginn der angegebenen Sequenz.

*letzten*\
Ende der angegebenen Sequenz.

## <a name="begin"></a>Path:: begin

Gibt einen `path::iterator` -Wert zurück, der das erste Pfad Element im Pfadnamen angibt, falls vorhanden.

```cpp
iterator begin() const;
```

## <a name="c_str"></a>Pfad:: c_str

Gibt einen Zeiger auf das erste Zeichen in `mypath`zurück.

```cpp
const value_type& *c_str() const noexcept;
```

## <a name="clear"></a>Path:: Clear

Führt `mypath.clear()`aus.

```cpp
void clear() noexcept;
```

## <a name="compare"></a>Path:: Compare

Diese erste Funktion gibt `mypath.compare(pval.native())` zurück. Die zweite Funktion gibt `mypath.compare(str)` zurück. Die dritte Funktion gibt `mypath.compare(ptr)`zurück.

```cpp
int compare(const path& pval) const noexcept;
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```

### <a name="parameters"></a>Parameter

*PVAL*\
Der zu vergleichende Pfad.

*SRT*\
Zu vergleichende Zeichenfolge.

*PTR*\
Der zu vergleichende Zeiger.

## <a name="concat"></a>Pfad:: Concat

Fügt die angegebene Sequenz nach Bedarf `mypath`an, konvertiert (aber kein Trennzeichen) an.

```cpp
template <class Source>
path& concat(const Source& source);

template <class InIt>
path& concat(InIt first, InIt last);
```

### <a name="parameters"></a>Parameter

*Ausgangs*\
Angegebene Sequenz.

*erstes*\
Beginn der angegebenen Sequenz.

*letzten*\
Ende der angegebenen Sequenz.

## <a name="const_iterator"></a>Pfad:: const_iterator

Ein Synonym für `iterator`.

```cpp
typedef iterator const_iterator;
```

## <a name="empty"></a>Path:: Empty

Gibt `mypath.empty()`zurück.

```cpp
bool empty() const noexcept;
```

## <a name="end"></a>Path:: End

Gibt einen Sequenz Ende-Iterator vom Typ `iterator`zurück.

```cpp
iterator end() const;
```

## <a name="extension"></a>Path:: Extension

Gibt das Suffix von `filename()`zurück.

```cpp
path extension() const;
```

### <a name="remarks"></a>Hinweise

Gibt das Suffix der `filename() X` folgenden zurück:

Wenn `X == path(".") || X == path("..")` oder wenn `X` keinen Punkt enthält, ist das Suffix leer.

Andernfalls beginnt das Suffix mit dem rechten Punkt (und umfasst diesen).

## <a name="filename"></a>Path:: filename

Gibt die Stammverzeichniskomponente von „myname“ zurück, insbesondere `empty() path() : *--end()`. Die Komponente kann leer sein.

```cpp
path filename() const;
```

## <a name="generic_string"></a>Pfad:: generic_string

Gibt `this->string<Elem, Traits, Alloc>(al)` zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird (unter Windows).

```cpp
template <class Elem,
    class Traits = char_traits<Elem>,
    class Alloc = allocator<Elem>>
  basic_string<Elem, Traits, Alloc>
    generic_string(const Alloc& al = Alloc()) const;

string generic_string() const;
```

## <a name="generic_u16string"></a>Pfad:: generic_u16string

Gibt `u16string()` zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird (unter Windows).

```cpp
u16string generic_u16string() const;
```

## <a name="generic_u32string"></a>Pfad:: generic_u32string

Gibt `u32string()` zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird (unter Windows).

```cpp
u32string generic_u32string() const;
```

## <a name="generic_u8string"></a>Pfad:: generic_u8string

Gibt `u8string()` zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird (unter Windows).

```cpp
string generic_u8string() const;
```

## <a name="generic_wstring"></a>Pfad:: generic_wstring

Gibt `wstring()` zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird (unter Windows).

```cpp
wstring generic_wstring() const;
```

## <a name="has_extension"></a>Pfad:: has_extension

Gibt `!extension().empty()`zurück.

```cpp
bool has_extension() const;
```

## <a name="has_filename"></a>Pfad:: has_filename

Gibt `!filename().empty()`zurück.

```cpp
bool has_filename() const;
```

## <a name="has_parent_path"></a>Pfad:: has_parent_path

Gibt `!parent_path().empty()`zurück.

```cpp
bool has_parent_path() const;
```

## <a name="has_relative_path"></a>Pfad:: has_relative_path

Gibt `!relative_path().empty()`zurück.

```cpp
bool has_relative_path() const;
```

## <a name="has_root_directory"></a>Pfad:: has_root_directory

Gibt `!root_directory().empty()`zurück.

```cpp
bool has_root_directory() const;
```

## <a name="has_root_name"></a>Pfad:: has_root_name

Gibt `!root_name().empty()`zurück.

```cpp
bool has_root_name() const;
```

## <a name="has_root_path"></a>Pfad:: has_root_path

Gibt `!root_path().empty()`zurück.

```cpp
bool has_root_path() const;
```

## <a name="has_stem"></a>Pfad:: has_stem

Gibt `!stem().empty()`zurück.

```cpp
bool has_stem() const;
```

## <a name="is_absolute"></a>Pfad:: is_absolute

Für Windows gibt die Funktion zurück `has_root_name() && has_root_directory()`. Für POSIX gibt die Funktion zurück `has_root_directory()`.

```cpp
bool is_absolute() const;
```

## <a name="is_relative"></a>Pfad:: is_relative

Gibt `!is_absolute()`zurück.

```cpp
bool is_relative() const;
```

## <a name="iterator"></a>Path:: Iterator

Ein bidirektionaler konstanter Iterator, der die Pfad Komponenten `myname`von festlegt.

```cpp
class iterator
   {
   // bidirectional iterator for path
   typedef bidirectional_iterator_tag iterator_category;
   typedef path_type value_type;
   typedef ptrdiff_t difference_type;
   typedef const value_type *pointer;
   typedef const value_type& reference;
   // ...
   };
```

### <a name="remarks"></a>Hinweise

Die Klasse beschreibt einen bidirektionalen Konstanten Iterator, der `path` die Komponenten `myname` von in der Sequenz festlegt:

1. den Stammnamen, falls vorhanden

1. das Stammverzeichnis, falls vorhanden

1. die übrigen Verzeichnis Elemente des übergeordneten `path`Elements (sofern vorhanden), die mit dem Dateinamen enden, falls vorhanden.

Für `pval` ein Objekt vom Typ `path`:

1. `path::iterator X = pval.begin()`legt das erste `path` Element im Pfadnamen fest, falls vorhanden.

1. `X == pval.end()`ist true, `X` wenn auf das Ende der Komponenten Sequenz verweist.

3. `*X`gibt eine Zeichenfolge zurück, die der aktuellen Komponente entspricht.

1. `++X` legt die nächste Komponente in der Sequenz fest, falls vorhanden.

1. `--X` legt die vorhergehende Komponente in der Sequenz fest, falls vorhanden.

1. Durch `myname` die Änderung werden alle Iteratoren ungültig, die `myname`Elemente in festlegen.

## <a name="make_preferred"></a>Pfad:: make_preferred

Konvertiert jedes Trennzeichen nach `preferred_separator` Bedarf in eine.

```cpp
path& make_preferred();
```

## <a name="native"></a>Path:: Native

Gibt `myname`zurück.

```cpp
const string_type& native() const noexcept;
```

## <a name="op_as"></a>Path:: Operator =

Ersetzt die Elemente des Pfads durch eine Kopie eines anderen Pfades.

```cpp
path& operator=(const path& right);
path& operator=(path&& right) noexcept;

template <class Source>
path& operator=(const Source& source);
```

### <a name="parameters"></a>Parameter

*Richting*\
Der [Pfad](../standard-library/path-class.md) , der in die `path`kopiert wird.

*Ausgangs*\
Der Quellpfad.

### <a name="remarks"></a>Hinweise

Der erste Member-Operator `right.myname` kopiert `myname`in. Der zweite Member-Operator `right.myname` wechselt `myname`zu. Der dritte Member-Operator verhält sich wie `*this = path(source)`.

## <a name="op_add"></a>Path:: Operator + =

Verschiedene `concat` Ausdrücke.

```cpp
path& operator+=(const path& right);
path& operator+=(const string_type& str);
path& operator+=(const value_type *ptr);
path& operator+=(value_type elem);

template <class Source>
path& operator+=(const Source& source);

template <class Elem>
path& operator+=(Elem elem);
```

### <a name="parameters"></a>Parameter

*Richting*\
Der hinzugefügte Pfad.

*SRT*\
Die hinzugefügte Zeichenfolge.

*PTR*\
Der hinzugefügte Zeiger.

*Elem*\
Der hinzu `value_type` gefügte oder `Elem`.

*Ausgangs*\
Die hinzugefügte Quelle.

### <a name="remarks"></a>Hinweise

Die Memberfunktionen verhalten sich wie die folgenden entsprechenden Ausdrücke:

1. `concat(right);`

1. `concat(path(str));`

1. `concat(ptr);`

1. `concat(string_type(1, elem));`

1. `concat(source);`

1. `concat(path(basic_string<Elem>(1, elem)));`

## <a name="op_divide"></a>Path:: Operator/=

Verschiedene `append` Ausdrücke.

```cpp
path& operator/=(const path& right);

template <class Source>
path& operator/=(const Source& source);
```

### <a name="parameters"></a>Parameter

*Richting*\
Der hinzugefügte Pfad.

*Ausgangs*\
Die hinzugefügte Quelle.

### <a name="remarks"></a>Hinweise

Die Memberfunktionen verhalten sich wie die folgenden entsprechenden Ausdrücke:

1. `append(right);`

1. `append(source);`

## <a name="op_string"></a>Path:: Operator string_type

Gibt `myname`zurück.

```cpp
operator string_type() const;
```

## <a name="parent_path"></a>Pfad::p arent_path

Gibt die übergeordnete Pfadkomponente `myname`von zurück.

```cpp
path parent_path() const;
```

### <a name="remarks"></a>Hinweise

Gibt die übergeordnete Pfadkomponente `myname`von zurück, insbesondere das `myname` Präfix `filename().native()` von nach dem Entfernen und alle unmittelbar vorangehenden Verzeichnis Trennzeichen. (Auch wenn `begin() != end()`, ist dies die Kombination aller Elemente im Bereich `[begin(), --end())` , indem Sie nacheinander anwenden `operator/=`.) Die Komponente kann leer sein.

## <a name="path"></a>Pfad::p ATH

Erstellt eine `path` auf verschiedene Weise.

```cpp
path();

path(const path& right);
path(path&& right) noexcept;

template <class Source>
path(const Source& source);

template <class Source>
path(const Source& source, const locale& loc);

template <class InIt>
path(InIt first, InIt last);

template <class InIt>
path(InIt first, InIt last, const locale& loc);
```

### <a name="parameters"></a>Parameter

*Richting*\
Der Pfad, in dem der konstruierte Pfad eine Kopie sein soll.

*Ausgangs*\
Die Quelle, deren Kopie der erstellte Pfad sein soll.

*a.a.o.* \
Das angegebene Gebiets Schema.

*erstes*\
Die Position des ersten zu kopierenden Elements.

*letzten*\
Die Position des letzten Elements, das kopiert werden soll.

### <a name="remarks"></a>Hinweise

Die Konstruktoren werden auf `myname` unterschiedliche Weise konstruiert:

`path()` Dies ist`myname()`.

Für `path(const path& right`) ist `myname(right.myname)`der Wert.

`path(path&& right)` Dies ist`myname(right.myname)`.

`template<class Source> path(const Source& source)` Dies ist`myname(source)`.

Dies `template<class Source> path(const Source& source, const locale& loc)` ist `myname(source)`der Fall, wenn Sie alle benötigten Codecvt `loc`-Facetten von erhalten.

`template<class InIt> path(InIt first, InIt last)` Dies ist`myname(first, last)`.

Dies `template<class InIt> path(InIt first, InIt last, const locale& loc)` ist `myname(first, last)`der Fall, wenn Sie alle benötigten Codecvt `loc`-Facetten von erhalten.

## <a name="preferred_separator"></a>Pfad::p referred_separator

Das konstante Objekt gibt je nach Betriebssystem des Hosts das bevorzugte Zeichen zum Trennen von Pfadkomponenten zurück.

```cpp
#if _WIN32_C_LIB
static constexpr value_type preferred_separator == L'\\';
#else // assume Posix
static constexpr value_type preferred_separator == '/';
#endif // filesystem model now defined
```

### <a name="remarks"></a>Hinweise

Beachten Sie, dass es in den meisten Kontexten unter Windows gleichermaßen zulässig ist, an dieser Stelle „L'/'“ zu verwenden.

## <a name="relative_path"></a>Pfad:: RELATIVE_PATH

Gibt die relative Pfadkomponente von `myname`zurück.

```cpp
path relative_path() const;
```

### <a name="remarks"></a>Hinweise

Gibt die relative Pfadkomponente von `myname`zurück, insbesondere das Suffix `myname` von nach `root_path().native()` dem Entfernen und die unmittelbar nachfolgenden redundante Verzeichnis Trennzeichen. Die Komponente kann leer sein.

## <a name="remove_filename"></a>Pfad:: remove_filename

Entfernt den Dateinamen.

```cpp
path& remove_filename();
```

## <a name="replace_extension"></a>Pfad:: replace_extension

Ersetzt die Erweiterung von `myname`.

```cpp
path& replace_extension(const path& newext = path());
```

### <a name="parameters"></a>Parameter

*NewExt*\
Die neue Erweiterung.

### <a name="remarks"></a>Hinweise

Entfernt zuerst das Suffix `extension().native()` aus `myname`. `!newext.empty() && newext[0] != dot` Wenn (wobei `dot` `dot` ist `*path(".").c_str()`), dann wird an `myname`angefügt. Anschließend wird " *netwext* " `myname`an angefügt.

## <a name="replace_filename"></a>Pfad:: replace_filename

Ersetzt den Dateinamen.

```cpp
path& replace_filename(const path& pval);
```

### <a name="parameters"></a>Parameter

*PVAL*\
Der Pfad des Datei namens.

### <a name="remarks"></a>Hinweise

Die Memberfunktion führt Folgendes aus:

```cpp
remove_filename();

*this /= pval;
return (*this);
```

## <a name="root_directory"></a>Pfad:: root_directory

Gibt die Stammverzeichnis Komponente von `myname`zurück.

```cpp
path root_directory() const;
```

### <a name="remarks"></a>Hinweise

Die Komponente kann leer sein.

## <a name="root_name"></a>Pfad:: root_name

Gibt die Stamm Namen Komponente von `myname`zurück.

```cpp
path root_name() const;
```

### <a name="remarks"></a>Hinweise

Die Komponente kann leer sein.

## <a name="root_path"></a>Pfad:: root_path

Gibt die Stamm Pfadkomponente von `myname`zurück.

```cpp
path root_path() const;
```

### <a name="remarks"></a>Hinweise

Gibt die Stamm Pfadkomponente von `myname`zurück, `root_name()`insbesondere  / . `root_directory` Die Komponente kann leer sein.

## <a name="stem"></a>Path:: stem

Gibt die `stem` Komponente von `myname`zurück.

```cpp
path stem() const;
```

### <a name="remarks"></a>Hinweise

Gibt die `stem` Komponente von `myname`zurück, `filename().native()` insbesondere mit allen `extension().native()` nachfolgenden entfernten. Die Komponente kann leer sein.

## <a name="string"></a>Path:: String

Konvertiert die in `mypath`gespeicherte Sequenz.

```cpp
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const;
string string() const;
```

### <a name="remarks"></a>Hinweise

Die erste Member-Funktion (Template) konvertiert die gespeicherte Sequenz `mypath` auf die gleiche Weise wie die folgende:

1. `string()` für `string<char, Traits, Alloc>()`

1. `wstring()` für `string<wchar_t, Traits, Alloc>()`

1. `u16string()` für `string<char16_t, Traits, Alloc>()`

1. `u32string()` für `string<char32_t, Traits, Alloc>()`

Die zweite Member-Funktion konvertiert die in `mypath` gespeicherte Sequenz in die Codierung, die vom Host System für eine **char** -Sequenz bevorzugt wird, und gibt Sie in `string`einem Objekt vom Typ gespeichert zurück.

## <a name="string_type"></a>Pfad:: string_type

Der Typ ist ein Synonym für `basic_string<value_type>`.

```cpp
typedef basic_string<value_type> string_type;
```

## <a name="swap"></a>Path:: Swap

Führt `swap(mypath, right.mypath)`aus.

```cpp
void swap(path& right) noexcept;
```

## <a name="u16string"></a>Pfad:: u16string

Konvertiert die in `mypath` gespeicherte Sequenz in UTF-16 und gibt Sie in einem Objekt vom Typ `u16string`zurück.

```cpp
u16string u16string() const;
```

## <a name="u32string"></a>Pfad:: u32string

Konvertiert die in `mypath` gespeicherte Sequenz in UTF-32 und gibt Sie in einem Objekt vom Typ `u32string`zurück.

```cpp
u32string u32string() const;
```

## <a name="u8string"></a>Pfad:: "u8string"

Konvertiert die in `mypath` gespeicherte Sequenz in UTF-8 und gibt Sie in einem Objekt vom Typ `u8string`zurück.

```cpp
string u8string() const;
```

## <a name="value_type"></a>Pfad:: value_type

Der Typ beschreibt die `path` Elemente, die vom Host Betriebssystem bevorzugt werden.

```cpp
#if _WIN32_C_LIB
typedef wchar_t value_type;
#else // assume Posix
typedef char value_type;
#endif // filesystem model now defined
```

## <a name="wstring"></a>Path:: wstring

Konvertiert die in `mypath` gespeicherte Sequenz in die Codierung, die vom Host System für eine **wchar_t** -Sequenz bevorzugt wird, und gibt diese in einem `wstring`Objekt vom Typ gespeichert zurück.

```cpp
wstring wstring() const;
```

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)
