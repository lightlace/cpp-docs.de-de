---
title: path-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::path
dev_langs:
- C++
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd8fa524d0c41d437575a61ff4e4456fd9933404
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725308"
---
# <a name="path-class"></a>path-Klasse

Die **Pfad** Klasse speichert ein Objekt des Typs `string_type`namens `myname` hier zum Zweck der Darstellung, die für die Verwendung als Pfadname geeignet ist. `string_type` ist ein Synonym für `basic_string<value_type>`, wobei `value_type` ist ein Synonym für **Char** unter Windows oder **"wchar_t"** unter Posix.

Weitere Informationen und Codebeispiele finden Sie unter [Datei Dateisystemnavigation (C++)](../standard-library/file-system-navigation.md).

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
|[Iterator](#iterator)|Ein konstanter bidirektionaler-Iterator, der bestimmt die `path` Komponenten `myname`.|
|[string_type](#string_type)|Der Typ ist ein Synonym für `basic_string<value_type>`.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[append](#append)|Fügt der angegebenen Reihenfolge um `mypath`konvertiert, und ein "preferred_separator" einfügen, je nach Bedarf.|
|[assign](#assign)|Ersetzt `mypath` mit der angegebenen Reihenfolge aus, bei Bedarf konvertiert wird.|
|[begin](#begin)|Gibt eine `path::iterator` das erste Pfadelement im Pfadnamen, festlegen, falls vorhanden.|
|[c_str](#c_str)|Gibt einen Zeiger auf das erste Zeichen in `mypath`.|
|[clear](#clear)|Führt `mypath.clear()`.|
|[compare](#compare)|Vergleichswerte zurückgegeben.|
|[concat](#compare)|Fügt der angegebenen Reihenfolge um `mypath`, konvertiert (aber fügen kein Trennzeichen) nach Bedarf.|
|[empty](#empty)|Gibt `mypath.empty()`zurück.|
|[end](#end)|Gibt einen Sequenzende Iterator vom Typ `iterator`.|
|[Erweiterung](#extension)|Gibt das Suffix des `filename()`.|
|[filename](#filename)|Gibt die Stammverzeichniskomponente von myname zurück, insbesondere `empty() path() : *--end()`. Die Komponente kann leer sein.|
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
|[is_absolute](#is_absolute)|Für Windows, die Funktion zurückgibt `has_root_name() && has_root_directory()`. Für Posix gibt die Funktion `has_root_directory()`.|
|[is_relative](#is_relative)|Gibt `!is_absolute()`zurück.|
|[make_preferred](#make_preferred)|Konvertiert jedes Trennzeichen in ein "preferred_separator" ein, nach Bedarf.|
|[native](#native)|Gibt `myname`zurück.|
|[parent_path](#parent_path)|Gibt die übergeordnete Pfadkomponente von `myname`.|
|["preferred_separator"](#preferred_separator)|Das konstante Objekt gibt je nach Betriebssystem des Hosts das bevorzugte Zeichen zum Trennen von Pfadkomponenten zurück. |
|[RELATIVE_PATH](#relative_path)|Gibt die relative Pfadkomponente von `myname`. |
|[remove_filename](#remove_filename)|Entfernt den Dateinamen an.|
|[replace_extension](#replace_extension)|Ersetzt die Erweiterung der `myname`. |
|[replace_filename](#replace_filename)|RReplaces den Dateinamen.|
|[root_directory](#root_directory)|Gibt die stammverzeichniskomponente von `myname`. |
|[root_name](#root_name)|Gibt die stammnamenkomponente von `myname`. |
|[Rootpfad](#root_path)|Gibt die stammpfadkomponente von `myname`.|
|[Stamm](#stem)|Gibt die `stem` -Komponente `myname`.|
|[string](#string)|Konvertiert die Sequenz, die in gespeicherten `mypath`.|
|[swap](#swap)|Führt `swap(mypath, right.mypath)`.|
|[u16string](#u16string)|Konvertiert die Sequenz, die in gespeicherten `mypath` UTF-16 und gibt es in ein Objekt des Typs gespeichert `u16string`.|
|[u32string](#u32string)|Konvertiert die Sequenz, die in gespeicherten `mypath` UTF-32 und gibt es in ein Objekt des Typs gespeichert `u32string`.|
|[u8string](#u8string)|Konvertiert die Sequenz, die in gespeicherten `mypath` UTF-8 und gibt es in ein Objekt des Typs gespeichert `u8string`.|
|[value_type](#value_type)|Der Typ beschreibt die Pfadelemente, die vom Hostbetriebssystem bevorzugt werden.|
|[wstring](#wstring)|Konvertiert die Sequenz, die in gespeicherten `mypath` in die Codierung, die vom Hostsystem für bevorzugt eine `wchar_t` Sequenz und gibt es in ein Objekt des Typs gespeichert `wstring`.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator=](#op_as)|Ersetzt die Elemente des Pfads mit einer Kopie einen anderen Pfad an.|
|[operator+=](#op_add)|Verschiedene `concat` Ausdrücke.|
|[operator/=](#op_divide)|Verschiedene `append` Ausdrücke.|
|[Operator string_type](#op_string)|Gibt `myname`zurück.|

## <a name="requirements"></a>Anforderungen

**Header:** \<Filesystem >

**Namespace:** std::experimental::filesystem

## <a name="append"></a> Path:: Append

Fügt der angegebenen Reihenfolge um `mypath`, konvertiert und Einfügen von einer `preferred_separator` je nach Bedarf.

```cpp
template <class Source>
path& append(const Source& source);

template <class InIt>
path& append(InIt first, InIt last);
```

### <a name="parameters"></a>Parameter

*source*<br/>
Angegebene Sequenz.

*Erste*<br/>
Anfang der angegebenen Sequenz.

*last*<br/>
Ende der angegebenen Sequenz.

## <a name="assign"></a> Path:: Assign

Ersetzt `mypath` mit der angegebenen Reihenfolge aus, bei Bedarf konvertiert wird.

```cpp
template <class Source>
path& assign(const Source& source);

template <class InIt>
path& assign(InIt first, InIt last);
```

### <a name="parameters"></a>Parameter

*source*<br/>
Angegebene Sequenz.

*Erste*<br/>
Anfang der angegebenen Sequenz.

*last*<br/>
Ende der angegebenen Sequenz.

## <a name="begin"></a> Path:: begin

Gibt eine `path::iterator` das erste Pfadelement im Pfadnamen, festlegen, falls vorhanden.

```cpp
iterator begin() const;
```

## <a name="c_str"></a> Path::c_str

Gibt einen Zeiger auf das erste Zeichen in `mypath`.

```cpp
const value_type& *c_str() const noexcept;
```

## <a name="clear"></a> Path:: Clear

Führt `mypath.clear()`.

```cpp
void clear() noexcept;
```

## <a name="compare"></a> Path:: Compare

Diese erste Funktion gibt `mypath.compare(pval.native())` zurück. Die zweite Funktion gibt `mypath.compare(str)` zurück. Die dritte Funktion gibt `mypath.compare(ptr)`.

```cpp
int compare(const path& pval) const noexcept;
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```

### <a name="parameters"></a>Parameter

*"pval"*<br/>
Pfad zu vergleichen.

*str*<br/>
Zu vergleichende Zeichenfolge.

*ptr*<br/>
Zeiger auf die verglichen werden soll.

## <a name="concat"></a> Path:: concat

Fügt der angegebenen Reihenfolge um `mypath`, konvertiert (aber fügen kein Trennzeichen) nach Bedarf.

```cpp
template <class Source>
path& concat(const Source& source);

template <class InIt>
path& concat(InIt first, InIt last);
```

### <a name="parameters"></a>Parameter

*source*<br/>
Angegebene Sequenz.

*Erste*<br/>
Anfang der angegebenen Sequenz.

*last*<br/>
Ende der angegebenen Sequenz.

## <a name="const_iterator"></a> Path::const_iterator

Ein Synonym für `iterator`.

```cpp
typedef iterator const_iterator;
```

## <a name="empty"></a> Path:: Empty

Gibt `mypath.empty()`zurück.

```cpp
bool empty() const noexcept;
```

## <a name="end"></a> Path:: End

Gibt einen Sequenzende Iterator vom Typ `iterator`.

```cpp
iterator end() const;
```

## <a name="extension"></a> Path:: Extension

Gibt das Suffix des `filename()`.

```cpp
path extension() const;
```

### <a name="remarks"></a>Hinweise

Gibt das Suffix des `filename() X` so, dass:

Wenn `X == path(".") || X == path("..")` oder, wenn `X` enthält keinen Punkt, das Suffix leer ist.

Andernfalls beginnt das Suffix mit dem rechten Punkt (und umfasst diesen).

## <a name="filename"></a> Path:: FileName

Gibt die Stammverzeichniskomponente von myname zurück, insbesondere `empty() path() : *--end()`. Die Komponente kann leer sein.

```cpp
path filename() const;
```

## <a name="generic_string"></a> Path::generic_string

Gibt `this->string<Elem, Traits, Alloc>(al)` zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird (unter Windows).

```cpp
template <class Elem,
    class Traits = char_traits<Elem>,
    class Alloc = allocator<Elem>>
  basic_string<Elem, Traits, Alloc>
    generic_string(const Alloc& al = Alloc()) const;

string generic_string() const;
```

## <a name="generic_u16string"></a> Path::generic_u16string

Gibt `u16string()` zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird (unter Windows).

```cpp
u16string generic_u16string() const;
```

## <a name="generic_u32string"></a> Path::generic_u32string

Gibt `u32string()` zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird (unter Windows).

```cpp
u32string generic_u32string() const;
```

## <a name="generic_u8string"></a> Path::generic_u8string

Gibt `u8string()` zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird (unter Windows).

```cpp
string generic_u8string() const;
```

## <a name="generic_wstring"></a> Path::generic_wstring

Gibt `wstring()` zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird (unter Windows).

```cpp
wstring generic_wstring() const;
```

## <a name="has_extension"></a> Path::has_extension

Gibt `!extension().empty()`zurück.

```cpp
bool has_extension() const;
```

## <a name="has_filename"></a> Path:: has_filename

Gibt `!filename().empty()`zurück.

```cpp
bool has_filename() const;
```

## <a name="has_parent_path"></a> Path:: has_parent_path

Gibt `!parent_path().empty()`zurück.

```cpp
bool has_parent_path() const;
```

## <a name="has_relative_path"></a> Path:: has_relative_path

Gibt `!relative_path().empty()`zurück.

```cpp
bool has_relative_path() const;
```

## <a name="has_root_directory"></a> Path:: has_root_directory

Gibt `!root_directory().empty()`zurück.

```cpp
bool has_root_directory() const;
```

## <a name="has_root_name"></a> Path:: has_root_name

Gibt `!root_name().empty()`zurück.

```cpp
bool has_root_name() const;
```

## <a name="has_root_path"></a> Path:: has_root_path

Gibt `!root_path().empty()`zurück.

```cpp
bool has_root_path() const;
```

## <a name="has_stem"></a> Path::has_stem

Gibt `!stem().empty()`zurück.

```cpp
bool has_stem() const;
```

## <a name="is_absolute"></a> Path:: is_absolute

Für Windows, die Funktion zurückgibt `has_root_name() && has_root_directory()`. Für Posix gibt die Funktion `has_root_directory()`.

```cpp
bool is_absolute() const;
```

## <a name="is_relative"></a> Path:: is_relative

Gibt `!is_absolute()`zurück.

```cpp
bool is_relative() const;
```

## <a name="iterator"></a> Pfadelement

Einen bidirektionalen Konstanten Iterator auf, der die Pfadkomponenten von kennzeichnet `myname`.

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

Die Klasse beschreibt einen bidirektionalen Konstanten Iterator, der bestimmt die `path` Komponenten `myname` in der Sequenz:

1. den Stammnamen, falls vorhanden

1. das Stammverzeichnis, falls vorhanden

1. die übrigen verzeichniselemente des übergeordneten Elements `path`, falls vorhanden, mit dem Dateinamen enden, falls vorhanden

Für `pval` ein Objekt des Typs `path`:

1. `path::iterator X = pval.begin()` Legt die erste `path` im Pfadnamen, falls vorhanden.

1. `X == pval.end()` ist true, wenn `X` Punkt direkt hinter das Ende der Sequenz von Komponenten.

3. `*X` Gibt eine Zeichenfolge, die der aktuellen Komponente übereinstimmt

1. `++X` legt die nächste Komponente in der Sequenz fest, falls vorhanden.

1. `--X` legt die vorhergehende Komponente in der Sequenz fest, falls vorhanden.

1. Ändern von `myname` werden alle Iteratoren ungültig Elemente im `myname`.

## <a name="make_preferred"></a> Path:: make_preferred

Konvertiert jedes Trennzeichen, um eine `preferred_separator` je nach Bedarf.

```cpp
path& make_preferred();
```

## <a name="native"></a> Path::native

Gibt `myname`zurück.

```cpp
const string_type& native() const noexcept;
```

## <a name="op_as"></a> Path:: =

Ersetzt die Elemente des Pfads mit einer Kopie einen anderen Pfad an.

```cpp
path& operator=(const path& right);
path& operator=(path&& right) noexcept;

template <class Source>
path& operator=(const Source& source);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Die [Pfad](../standard-library/path-class.md) kopiert wird, in der `path`.

*source*<br/>
Der Quellpfad.

### <a name="remarks"></a>Hinweise

Die erste Member-Operator Kopien `right.myname` zu `myname`. Der zweite Memberoperator verschiebt `right.myname` zu `myname`. Der dritte Memberoperator verhält sich wie `*this = path(source)`.

## <a name="op_add"></a> Path:: Operator +=

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

*right*<br/>
Die hinzugefügten Pfad.

*str*<br/>
Die hinzugefügte Zeichenfolge.

*ptr*<br/>
Der hinzugefügte Zeiger.

*Elem*<br/>
Die hinzugefügte `value_type` oder `Elem`.

*source*<br/>
Die hinzugefügten Quelle.

### <a name="remarks"></a>Hinweise

Die Memberfunktionen verhalten sich wie die folgenden entsprechenden Ausdrücke:

1. `concat(right);`

1. `concat(path(str));`

1. `concat(ptr);`

1. `concat(string_type(1, elem));`

1. `concat(source);`

1. `concat(path(basic_string<Elem>(1, elem)));`

## <a name="op_divide"></a> Path:: Operator / =

Verschiedene `append` Ausdrücke.

```cpp
path& operator/=(const path& right);

template <class Source>
path& operator/=(const Source& source);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Die hinzugefügten Pfad.

*source*<br/>
Die hinzugefügten Quelle.

### <a name="remarks"></a>Hinweise

Die Memberfunktionen verhalten sich wie die folgenden entsprechenden Ausdrücke:

1. `append(right);`

1. `append(source);`

## <a name="op_string"></a> Path:: Operator string_type

Gibt `myname`zurück.

```cpp
operator string_type() const;
```

## <a name="parent_path"></a> Path:: parent_path

Gibt die übergeordnete Pfadkomponente von `myname`.

```cpp
path parent_path() const;
```

### <a name="remarks"></a>Hinweise

Gibt die übergeordnete Pfadkomponente von `myname`, insbesondere das Präfix des `myname` nach dem Entfernen `filename().native()` und aller unmittelbar vorangehenden Verzeichnistrennzeichen. (Gleich aus, wenn `begin() != end()`, es ist die Kombination aller Elemente im Bereich von `[begin(), --end())` übergegangenen `operator/=`.) Die Komponente kann leer sein.

## <a name="path"></a> Path:: Path

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

*right*<br/>
Der Pfad, den der konstruierte Pfad ist eine Kopie.

*source*<br/>
Die Quelle, von der der erstellte Pfad, die Kopie ist.

*Loc*<br/>
Das angegebene Gebietsschema.

*Erste*<br/>
Die Position des ersten zu kopierenden Elements.

*last*<br/>
Die Position des letzten Elements kopiert werden soll.

### <a name="remarks"></a>Hinweise

Die Konstruktoren alle erstellen `myname` auf verschiedene Weise:

Für `path()` ist `myname()`.

Für `path(const path& right`) ist `myname(right.myname)`.

Für `path(path&& right)` ist `myname(right.myname)`.

Für `template<class Source> path(const Source& source)` ist `myname(source)`.

Für `template<class Source> path(const Source& source, const locale& loc)` ist `myname(source)`, wobei alle erforderlichen Codecvt-Facets von `loc`.

Für `template<class InIt> path(InIt first, InIt last)` ist `myname(first, last)`.

Für `template<class InIt> path(InIt first, InIt last, const locale& loc)` ist `myname(first, last)`, wobei alle erforderlichen Codecvt-Facets von `loc`.

## <a name="preferred_separator"></a> Path::preferred_separator

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

## <a name="relative_path"></a> Path:: RELATIVE_PATH

Gibt die relative Pfadkomponente von `myname`.

```cpp
path relative_path() const;
```

### <a name="remarks"></a>Hinweise

Gibt die relative Pfadkomponente von `myname`, insbesondere das Suffix von `myname` nach dem Entfernen `root_path().native()` und aller unmittelbar nachfolgenden redundanten Verzeichnistrennzeichen. Die Komponente kann leer sein.

## <a name="remove_filename"></a> Path:: remove_filename

Entfernt den Dateinamen an.

```cpp
path& remove_filename();
```

## <a name="replace_extension"></a> Path:: replace_extension

Ersetzt die Erweiterung der `myname`.

```cpp
path& replace_extension(const path& newext = path());
```

### <a name="parameters"></a>Parameter

*"newext"*<br/>
Die neue Erweiterung.

### <a name="remarks"></a>Hinweise

Entfernt zuerst das Suffix `extension().native()` aus `myname`. Dann, wenn `!newext.empty() && newext[0] != dot` (wobei `dot` ist `*path(".").c_str()`), klicken Sie dann `dot` wird angefügt `myname`. Klicken Sie dann *"newext"* wird angefügt `myname`.

## <a name="replace_filename"></a> Path:: replace_filename

Ersetzt den Dateinamen an.

```cpp
path& replace_filename(const path& pval);
```

### <a name="parameters"></a>Parameter

*"pval"*<br/>
Der Pfad des Dateinamens.

### <a name="remarks"></a>Hinweise

Die Memberfunktion führt Folgendes aus:

```cpp
remove_filename();

*this /= pval;
return (*this);
```

## <a name="root_directory"></a> Path:: root_directory

Gibt die stammverzeichniskomponente von `myname`.

```cpp
path root_directory() const;
```

### <a name="remarks"></a>Hinweise

Die Komponente kann leer sein.

## <a name="root_name"></a> Path:: root_name

Gibt die stammnamenkomponente von `myname`.

```cpp
path root_name() const;
```

### <a name="remarks"></a>Hinweise

Die Komponente kann leer sein.

## <a name="root_path"></a> Path:: root_path

Gibt die stammpfadkomponente von `myname`.

```cpp
path root_path() const;
```

### <a name="remarks"></a>Hinweise

Gibt die stammpfadkomponente von `myname`, insbesondere `root_name()`  /  `root_directory`. Die Komponente kann leer sein.

## <a name="stem"></a> Path:: stem

Gibt die `stem` -Komponente `myname`.

```cpp
path stem() const;
```

### <a name="remarks"></a>Hinweise

Gibt die `stem` -Komponente `myname`, insbesondere `filename().native()` mit jedem nachfolgenden `extension().native()` entfernt. Die Komponente kann leer sein.

## <a name="string"></a> Path:: String

Konvertiert die Sequenz, die in gespeicherten `mypath`.

```cpp
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const;
string string() const;
```

### <a name="remarks"></a>Hinweise

Die erste (Vorlagen-) Memberfunktion konvertiert die Sequenz, die in gespeicherten `mypath` die gleiche Weise wie:

1. `string()` für `string<char, Traits, Alloc>()`

1. `wstring()` für `string<wchar_t, Traits, Alloc>()`

1. `u16string()` für `string<char16_t, Traits, Alloc>()`

1. `u32string()` für `string<char32_t, Traits, Alloc>()`

Die zweite Memberfunktion konvertiert die Sequenz, die in gespeicherten `mypath` in die Codierung, die vom Hostsystem für bevorzugt eine **Char** Sequenz und gibt es in ein Objekt des Typs gespeichert `string`.

## <a name="string_type"></a> Path::string_type

Der Typ ist ein Synonym für `basic_string<value_type>`.

```cpp
typedef basic_string<value_type> string_type;
```

## <a name="swap"></a> Path:: Swap

Führt `swap(mypath, right.mypath)`.

```cpp
void swap(path& right) noexcept;
```

## <a name="u16string"></a> Path::u16string

Konvertiert die Sequenz, die in gespeicherten `mypath` UTF-16 und gibt es in ein Objekt des Typs gespeichert `u16string`.

```cpp
u16string u16string() const;
```

## <a name="u32string"></a> Path::u32string

Konvertiert die Sequenz, die in gespeicherten `mypath` UTF-32 und gibt es in ein Objekt des Typs gespeichert `u32string`.

```cpp
u32string u32string() const;
```

## <a name="u8string"></a> Path::u8string

Konvertiert die Sequenz, die in gespeicherten `mypath` UTF-8 und gibt es in ein Objekt des Typs gespeichert `u8string`.

```cpp
string u8string() const;
```

## <a name="value_type"></a> Path::value_type

Der Typ beschreibt die `path` Elemente, die vom Hostbetriebssystem bevorzugt wird.

```cpp
#if _WIN32_C_LIB
typedef wchar_t value_type;
#else // assume Posix
typedef char value_type;
#endif // filesystem model now defined
```

## <a name="wstring"></a> Path::wstring

Konvertiert die Sequenz, die in gespeicherten `mypath` in die Codierung, die vom Hostsystem für bevorzugt eine **"wchar_t"** Sequenz und gibt es in ein Objekt des Typs gespeichert `wstring`.

```cpp
wstring wstring() const;
```

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
