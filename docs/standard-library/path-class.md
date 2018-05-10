---
title: path-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 8ea20d43e2679addc10465cfc549a64fc210274f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="path-class"></a>path-Klasse

Die **path**-Klasse speichert ein Objekt vom Typ string\_type namens „myname“. Dies erfolgt hier zum Zweck der Darstellung, die zur Verwendung als Pfadname geeignet ist. string\_type ist ein Synonym für basic\_string\<value_type>, wobei value\_type unter Windows ein Synonym für char oder unter Posix ein Synonym für wchar_t ist.

Weitere Informationen und Codebeispiele finden Sie unter [Datei System Navigation (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Syntax

```cpp
class path;
```

## <a name="pathappend"></a>path::append

```cpp
template <class Source>
path& append(const Source& source);

template <class InIt>
path& append(InIt first, InIt last);
```

Die Memberfunktionen fügen die angegebene (und bei Bedarf konvertierte) Sequenz an „mypath“ an und fügen bei Bedarf ein „preferred_separator“ ein.

## <a name="pathassign"></a>path::assign

```cpp
template <class Source>
path& assign(const Source& source);

template <class InIt>
path& assign(InIt first, InIt last);
```

Die Memberfunktionen ersetzen „mypath“ durch die angegebene Sequenz, die bei Bedarf konvertiert wird.

## <a name="pathbegin"></a>path::begin

```cpp
iterator begin() const;
```

Gibt ein „path::iterator“ zurück, das das erste Pfadelement im Pfadnamen bezeichnet, sofern dieses vorhanden ist.

## <a name="pathcstr"></a>path::c_str

```cpp
const value_type& *c_str() const noexcept;
```

Gibt einen Zeiger auf das erste Zeichen in „mypath“ zurück.

## <a name="pathclear"></a>path::clear

```cpp
void clear() noexcept;
```

Die Memberfunktion führt „mypath.clear()“ aus.

## <a name="pathcompare"></a>path::compare

```cpp
int compare(const path& pval) const noexcept;
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```

Die erste Funktion gibt „mypath.compare(pval.native())“ zurück. Die zweite Funktion gibt „mypath.compare(str)“ zurück. Die dritte Funktion gibt „mypath.compare(ptr)“ zurück.

## <a name="pathconcat"></a>path::concat

```cpp
template <class Source>
path& concat(const Source& source);

template <class InIt>
path& concat(InIt first, InIt last);
```

Die Memberfunktionen fügen die angegebene und bei Bedarf konvertierte Sequenz an „mypath“ an (aber fügen kein Trennzeichen ein).

## <a name="pathconstiterator"></a>path::const_iterator

```cpp
typedef iterator const_iterator;
```

Der Typ ist ein Synonym für Iterator.

## <a name="pathempty"></a>path::empty

```cpp
bool empty() const noexcept;
```

Gibt „mypath.empty()“ zurück.

## <a name="pathend"></a>path::end

```cpp
iterator end() const;
```

Gibt einen Sequenzende-Iterator vom Typ „iterator“ zurück.

## <a name="pathextension"></a>path::extension

```cpp
path extension() const;
```

Gibt das Suffix von „filename() X“ zurück. Beispiel:

Wenn X== == path(".") &#124;&#124; X == path("..") oder wenn X keinen Punkt enthält, ist das Suffix leer.

Andernfalls beginnt das Suffix mit dem rechten Punkt (und umfasst diesen).

## <a name="pathfilename"></a>path::filename

```cpp
path filename() const;
```

Gibt die Stammverzeichniskomponente von „myname“ zurück, insbesondere `empty()  path() : *--end()`. Die Komponente kann leer sein.

## <a name="pathgenericstring"></a>path::generic_string

```cpp
template <class Elem,
    class Traits = char_traits<Elem>,
    class Alloc = allocator<Elem>>
  basic_string<Elem, Traits, Alloc>
    generic_string(const Alloc& al = Alloc()) const;

string generic_string() const;
```

Gibt `this->string<Elem, Traits, Alloc>(al)` zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird (unter Windows).

## <a name="pathgenericu16string"></a>path::generic_u16string

```cpp
u16string generic_u16string() const;
```

Gibt „u16string()“ zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird (unter Windows).

## <a name="pathgenericu32string"></a>path::generic_u32string

```cpp
u32string generic_u32string() const;
```

Gibt „u32string()“ zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird (unter Windows).

## <a name="pathgenericu8string"></a>path::generic_u8string

```cpp
string generic_u8string() const;
```

Gibt „u8string()“ zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird (unter Windows).

## <a name="pathgenericwstring"></a>path::generic_wstring

```cpp
wstring generic_wstring() const;
```

Gibt „wstring()“ zurück, wobei jeder umgekehrte Schrägstrich in einen Schrägstrich konvertiert wird (unter Windows).

## <a name="pathhasextension"></a>path::has_extension

```cpp
bool has_extension() const;
```

Gibt „!extension().empty()“ zurück.

## <a name="pathhasfilename"></a>path::has_filename

```cpp
bool has_filename() const;
```

Gibt „!filename().empty()“ zurück.

## <a name="pathhasparentpath"></a>path::has_parent_path

```cpp
bool has_parent_path() const;
```

Gibt „!parent_path().empty()“ zurück.

## <a name="pathhasrelativepath"></a>path::has_relative_path

```cpp
bool has_relative_path() const;
```

Gibt „!relative_path().empty()“ zurück.

## <a name="pathhasrootdirectory"></a>path::has_root_directory

```cpp
bool has_root_directory() const;
```

Gibt „!root_directory().empty()“ zurück.

## <a name="pathhasrootname"></a>path::has_root_name

```cpp
bool has_root_name() const;
```

Gibt „!root_name().empty()“ zurück.

## <a name="pathhasrootpath"></a>path::has_root_path

```cpp
bool has_root_path() const;
```

Gibt „!root_path().empty()“ zurück.

## <a name="pathhasstem"></a>path::has_stem

```cpp
bool has_stem() const;
```

Gibt „!stem().empty()“ zurück.

## <a name="pathisabsolute"></a>path::is_absolute

```cpp
bool is_absolute() const;
```

Für Windows gibt die Funktion „has_root_name() && has_root_directory()“ zurück. Für Posix gibt die Funktion „has_root_directory()“ zurück.

## <a name="pathisrelative"></a>path::is_relative

```cpp
bool is_relative() const;
```

Gibt „!is_absolute()“ zurück.

## <a name="pathiterator"></a>path::iterator

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

Die Klasse beschreibt einen bidirektionalen konstanten Iterator, der die Pfadkomponenten von „myname“ in der Sequenz bezeichnet:

1. den Stammnamen, falls vorhanden

1. das Stammverzeichnis, falls vorhanden

1. die übrigen Verzeichniselemente des übergeordneten Pfads, falls vorhanden, die mit dem Dateinamen enden, falls vorhanden

Für „pval“ ein Objekt vom Typ „path“:

1. „path::iterator X = pval.begin()“ bezeichnet das erste Pfadelement im Pfadnamen, falls vorhanden.

1. „X == pval.end()“ ist „true“, wenn „X“ nur hinter das Ende der Sequenz der Komponenten zeigt.

3. „*X“ gibt eine Zeichenfolge zurück, die mit der aktuellen Komponente übereinstimmt.

1. „++X“ legt die nächste Komponente in der Sequenz fest, falls vorhanden.

1. „--X“ legt die vorhergehende Komponente in der Sequenz fest, falls vorhanden.

1. Durch die Änderung von „myname“ werden alle Iteratoren ungültig, die Elemente in „myname“ bezeichnen.

## <a name="pathmakepreferred"></a>path::make_preferred

```cpp
path& make_preferred();
```

Die Memberfunktion konvertiert bei Bedarf jedes Trennzeichen in ein „preferred_separator“.

## <a name="pathnative"></a>path::native

```cpp
const string_type& native() const noexcept;
```

Gibt „myname“ zurück.

## <a name="pathoperator"></a>path::operator=

```cpp
path& operator=(const path& right);
path& operator=(path&& right) noexcept;

template <class Source>
path& operator=(const Source& source);
```

Der erste Memberoperator kopiert „right.myname“ zu „myname“. Der zweite Memberoperator verschiebt „right.myname“ zu „myname“. Die dritte Memberoperator verhält sich wie „*this = path(source)“.

## <a name="pathoperator"></a>path::operator+=

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

Die Memberfunktionen verhalten sich wie die folgenden entsprechenden Ausdrücke:

1. concat(right);

1. concat(path(str));

1. concat(ptr);

1. concat(string_type(1, elem));

1. concat(source);

1. concat(path(basic_string\<Elem>(1, elem)));

## <a name="pathoperator"></a>path::operator/=

```cpp
path& operator/=(const path& right);

template <class Source>
path& operator/=(const Source& source);
```

Die Memberfunktionen verhalten sich wie die folgenden entsprechenden Ausdrücke:

1. append(right);

1. append(source);

## <a name="pathoperator-stringtype"></a>path::operator string_type

```cpp
operator string_type() const;
```

Der Memberoperator gibt „myname“ zurück.

## <a name="pathparentpath"></a>path::parent_path

```cpp
path parent_path() const;
```

Gibt die übergeordnete Pfadkomponente von „myname“ zurück, insbesondere das Präfix von „myname“ nach dem Entfernen von „filename().native()“ und aller unmittelbar vorangehenden Verzeichnistrennzeichen. (Bei „begin() != end()“ werden gleichermaßen alle Elemente im Bereich „[begin(), --end())“ kombiniert, indem „operator/=“ fortlaufend angewendet wird.) Die Komponente kann leer sein.

## <a name="pathpath"></a>path::path

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

Die Konstruktoren erstellen „myname“ alle auf verschiedene Weise:

Für „path()“ ist es „myname()“.

Für „path(const path& right)“ ist es „myname(right.myname)“.

Für „path(path&& right)“ ist es „myname(right.myname)“.

Für template\<class Source> path(const Source& source) ist es myname(source).

Für template\<class Source> path(const Source& source, const locale& loc) ist es myname(source), wobei alle erforderlichen codecvt-Facets von loc abgerufen werden.

Für template\<class InIt> path(InIt first, InIt last) ist es myname(first, last).

Für template\<class InIt> path(InIt first, InIt last, const locale& loc) ist es myname(first, last), wobei alle erforderlichen codecvt-Facets von loc abgerufen werden.

## <a name="pathpreferredseparator"></a>path::preferred_separator

```cpp
#if _WIN32_C_LIB
static constexpr value_type preferred_separator == L'\\';
#else // assume Posix
static constexpr value_type preferred_separator == '/';
#endif // filesystem model now defined
```

Das konstante Objekt gibt je nach Betriebssystem des Hosts das bevorzugte Zeichen zum Trennen von Pfadkomponenten zurück. Beachten Sie, dass es in den meisten Kontexten unter Windows gleichermaßen zulässig ist, an dieser Stelle „L'/'“ zu verwenden.

## <a name="pathrelativepath"></a>path::relative_path

```cpp
path relative_path() const;
```

Gibt die relative Pfadkomponente von „myname“ zurück, insbesondere das Suffix von „myname“ nach dem Entfernen von „root_path().native()“ und aller unmittelbar nachfolgenden redundanten Verzeichnistrennzeichen. Die Komponente kann leer sein.

## <a name="pathremovefilename"></a>path::remove_filename

```cpp
path& remove_filename();
```

## <a name="pathreplaceextension"></a>path::replace_extension

```cpp
path& replace_extension(const path& newext = path());
```

Die Memberfunktion entfernt zuerst das Suffix „extension().native()“ aus „myname“. Dann wird bei „!newext.empty() && newext[0] != dot“ (wobei „dot“ dem Wert „*path(".").c_str()“ entspricht) „dot“ an „myname“ angehängt. Dann wird „newext“ an „myname“ angefügt.

## <a name="pathreplacefilename"></a>path::replace_filename

```cpp
path& replace_filename(const path& pval);
```

Die Memberfunktion führt Folgendes aus:

```cpp
remove_filename();

*this /= pval;
return (*this);
```

## <a name="pathrootdirectory"></a>path::root_directory

```cpp
path root_directory() const;
```

Gibt die Stammverzeichniskomponente von „myname“ zurück. Die Komponente kann leer sein.

## <a name="pathrootname"></a>path::root_name

```cpp
path root_name() const;
```

Gibt die Stammnamenkomponente von „myname“ zurück. Die Komponente kann leer sein.

## <a name="pathrootpath"></a>path::root_path

```cpp
path root_path() const;
```

Gibt die Stammpfadkomponente von „myname“ zurück, insbesondere „root_name() / root_directory“. Die Komponente kann leer sein.

## <a name="pathstem"></a>path::stem

```cpp
path stem() const;
```

Gibt die Stammkomponente von „myname“ zurück, insbesondere „filename().native()“, wobei jedes nachfolgende „extension().native()“ entfernt wird. Die Komponente kann leer sein.

## <a name="pathstring"></a>path::string

```cpp
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const;
string string() const;
```

Die erste (Vorlagen-) Memberfunktion konvertiert die in „mypath“ gespeicherte Sequenz genauso wie:

1. string() für string\<char, Traits, Alloc>()

1. wstring() für string\<wchar_t, Traits, Alloc>()

1. u16string() für string\<char16_t, Traits, Alloc>()

1. u32string() für string\<char32_t, Traits, Alloc>()

Die zweite Memberfunktion konvertiert die in „mypath“ gespeicherte Sequenz in die Codierung, die vom Hostsystem für eine char-Sequenz bevorzugt wird, und gibt diese in einem Objekt vom Typ „string“ gespeichert zurück.

## <a name="pathstringtype"></a>path::string_type

```cpp
typedef basic_string<value_type> string_type;
```

Der Typ ist ein Synonym für „basic_string<value_type>“.

## <a name="pathswap"></a>path::swap

```cpp
void swap(path& right) noexcept;
```

Führt „swap(mypath, right.mypath)“ aus.

## <a name="pathu16string"></a>path::u16string

```cpp
u16string u16string() const;
```

Die Memberfunktion konvertiert die in „mypath“ gespeicherte Sequenz in UTF-16, und gibt diese in einem Objekt vom Typ „u16string“ gespeichert zurück.

## <a name="pathu32string"></a>path::u32string

```cpp
u32string u32string() const;
```

Die Memberfunktion konvertiert die in „mypath“ gespeicherte Sequenz in UTF-32, und gibt diese in einem Objekt vom Typ „u32string“ gespeichert zurück.

## <a name="pathu8string"></a>path::u8string

```cpp
string u8string() const;
```

Die Memberfunktion konvertiert die in „mypath“ gespeicherte Sequenz in UTF-8, und gibt diese in einem Objekt vom Typ „u8string“ gespeichert zurück.

## <a name="pathvaluetype"></a>path::value_type

```cpp
#if _WIN32_C_LIB
typedef wchar_t value_type;
#else // assume Posix
typedef char value_type;
#endif // filesystem model now defined
```

Der Typ beschreibt die Pfadelemente, die vom Hostbetriebssystem bevorzugt werden.

## <a name="pathwstring"></a>path::wstring

```cpp
wstring wstring() const;
```

Konvertiert die in „mypath“ gespeicherte Sequenz in die Codierung, die vom Hostsystem für eine wchar_t-Sequenz bevorzugt wird, und gibt diese in einem Objekt vom Typ „wstring“ gespeichert zurück.

## <a name="requirements"></a>Anforderungen

**Header:** \<Filesystem >

**Namespace:** std::experimental::filesystem

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
