---
title: directory_entry-Klasse
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- filesystem/std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- filesystem/std::experimental::filesystem::directory_entry::directory_entry
- filesystem/std::experimental::filesystem::directory_entry::operator=
- filesystem/std::experimental::filesystem::directory_entry::assign
- filesystem/std::experimental::filesystem::directory_entry::replace_filename
- filesystem/std::experimental::filesystem::directory_entry::path
- filesystem/std::experimental::filesystem::directory_entry::status
- filesystem/std::experimental::filesystem::directory_entry::symlink_status
- filesystem/std::experimental::filesystem::directory_entry::operator&lt;
- filesystem/std::experimental::filesystem::directory_entry::operator==
- filesystem/std::experimental::filesystem::directory_entry::operator!=
- filesystem/std::experimental::filesystem::directory_entry::operator&lt;=
- filesystem/std::experimental::filesystem::directory_entry::operator&gt;
- filesystem/std::experimental::filesystem::directory_entry::operator&gt;=
ms.assetid: 1827c67b-4137-4548-adb0-f955f7acaf08
helpviewer_keywords:
- std::experimental::filesystem::directory_entry
- std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- std::experimental::filesystem::directory_entry::directory_entry
- std::experimental::filesystem::directory_entry::operator=
- std::experimental::filesystem::directory_entry::assign
- std::experimental::filesystem::directory_entry::replace_filename
- std::experimental::filesystem::directory_entry::path
- std::experimental::filesystem::directory_entry::status
- std::experimental::filesystem::directory_entry::symlink_status
- std::experimental::filesystem::directory_entry::operator&lt;
- std::experimental::filesystem::directory_entry::operator==
- std::experimental::filesystem::directory_entry::operator!=
- std::experimental::filesystem::directory_entry::operator&lt;=
- std::experimental::filesystem::directory_entry::operator&gt;
- std::experimental::filesystem::directory_entry::operator&gt;=
ms.openlocfilehash: c1b68aefd44d8f0ac60c36307dee93333d801bb9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533821"
---
# <a name="directoryentry-class"></a>directory_entry-Klasse

Beschreibt ein Objekt, das durch `*X` zurückgegeben wird, wobei *X* ein [directory_iterator](../standard-library/directory-iterator-class.md) oder ein [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) ist.

## <a name="syntax"></a>Syntax

```cpp
class directory_entry;
```

## <a name="remarks"></a>Hinweise

Die Klasse speichert ein Objekt vom Typ [path](../standard-library/path-class.md). Bei dem gespeicherten `path`-Objekt kann es sich um eine Instanz der [path-Klasse](../standard-library/path-class.md) oder um einen von `path` abgeleiteten Typ handeln. Die Klasse speichert zudem zwei [file_type](../standard-library/filesystem-enumerations.md#file_type)-Werte. Einer davon repräsentiert das, was über den Status des gespeicherten Dateinamens bekannt ist. Der andere repräsentiert das, was über den symbolischen Linkstatus des Dateinamens bekannt ist.

Weitere Informationen und Codebeispiele finden Sie unter [Dateisystemnavigation (C++)](../standard-library/file-system-navigation.md).

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|["directory_entry"](#directory_entry)|Die als Standard festgelegten Konstruktoren verhalten sich wie erwartet. Der vierte Konstruktor initialisiert `mypath` zu *"pval"*, `mystat` zu *Stat_arg*, und `mysymstat` zu *"symstat_arg"*.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[assign](#assign)|Die Memberfunktion weist *"pval"* zu `mypath`, *Stat* zu `mystat`, und *"symstat"* zu `mysymstat`.|
|[path](#path)|Die Memberfunktion gibt `mypath`zurück.|
|[replace_filename](#replace_filename)|Die Memberfunktion ersetzt `mypath` mit `mypath.parent_path()`  /  *"pval"*, `mystat` mit *Stat_arg*, und `mysymstat` mit *"symstat_arg"*|
|[Status](#status)|Beide Memberfunktionen geben `mystat` möglicherweise zuerst geändert.|
|[symlink_status](#symlink_status)|Beide Memberfunktionen geben `mysymstat` möglicherweise zuerst geändert.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[Operator!=](#op_neq)|Ersetzt die Elemente der Liste mit einer Kopie einer anderen Liste.|
|[operator=](#op_as)|Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.|
|[operator==](#op_eq)|Gibt `mypath == right.mypath`zurück.|
|[operator<](#op_lt)|Gibt `mypath < right.mypath`zurück.|
|[operator<=](#op_lteq)|Gibt `!(right < *this)`zurück.|
|[operator>](#op_gt)|Gibt `right < *this`zurück.|
|[operator>=](#op_gteq)|Gibt `!(*this < right)`zurück.|
|[Operator const Path_type &](#path_type)|Gibt `mypath`zurück.|

## <a name="requirements"></a>Anforderungen

**Header:** \<experimental/Filesystem&gt;

**Namespace:** std::experimental::filesystem

## <a name="assign"></a> Weisen Sie

Die Memberfunktion weist *"pval"* zu `mypath`, *Stat_arg* zu `mystat`, und *"symstat_arg"* zu `mysymstat`.

```cpp
void assign(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>Parameter

*"pval"*<br/>
Der gespeicherte Dateinamenpfad.

*stat_arg*<br/>
Der Status des gespeicherten Dateinamens.

*"symstat_arg"*<br/>
Den symbolischen Linkstatus des gespeicherten Dateinamens.

## <a name="directory_entry"></a> "directory_entry"

Die als Standard festgelegten Konstruktoren verhalten sich wie erwartet. Der vierte Konstruktor initialisiert `mypath` zu *"pval"*, `mystat` zu *Stat_arg*, und `mysymstat` zu *"symstat_arg"*.

```cpp
directory_entry() = default;
directory_entry(const directory_entry&) = default;
directory_entry(directory_entry&&) noexcept = default;
explicit directory_entry(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>Parameter

*"pval"*<br/>
Der gespeicherte Dateinamenpfad.

*stat_arg*<br/>
Der Status des gespeicherten Dateinamens.

*"symstat_arg"*<br/>
Den symbolischen Linkstatus des gespeicherten Dateinamens.

## <a name="op_neq"></a> Operator! =

Die Memberfunktion gibt `!(*this == right)`zurück.

```cpp
bool operator!=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parameter

*right*<br/>
Die ["directory_entry"](../standard-library/directory-entry-class.md) wird im Vergleich zu den `directory_entry`.

## <a name="op_as"></a> Operator =

Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.

```cpp
directory_entry& operator=(const directory_entry&) = default;
directory_entry& operator=(directory_entry&&) noexcept = default;
```

### <a name="parameters"></a>Parameter

*right*<br/>
Die ["directory_entry"](../standard-library/directory-entry-class.md) kopiert wird, in der `directory_entry`.

## <a name="op_eq"></a> Operator ==

Die Memberfunktion gibt `mypath == right.mypath`zurück.

```cpp
bool operator==(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parameter

*right*<br/>
Die ["directory_entry"](../standard-library/directory-entry-class.md) wird im Vergleich zu den `directory_entry`.

## <a name="op_lt"></a> Operator&lt;

Die Memberfunktion gibt `mypath < right.mypath`zurück.

```cpp
bool operator<(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parameter

*right*<br/>
Die ["directory_entry"](../standard-library/directory-entry-class.md) wird im Vergleich zu den `directory_entry`.

## <a name="op_lteq"></a> Operator&lt;=

Die Memberfunktion gibt `!(right < *this)`zurück.

```cpp
bool operator&lt;=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parameter

*right*<br/>
Die ["directory_entry"](../standard-library/directory-entry-class.md) wird im Vergleich zu den `directory_entry`.

## <a name="op_gt"></a> Operator&gt;

Die Memberfunktion gibt `right < *this`zurück.

```cpp
bool operator&gt;(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parameter

*right*<br/>
Die ["directory_entry"](../standard-library/directory-entry-class.md) wird im Vergleich zu den `directory_entry`.

## <a name="op_gteq"></a> Operator&gt;=

Die Memberfunktion gibt `!(*this < right)`zurück.

```cpp
bool operator&gt;=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parameter

*right*<br/>
Die ["directory_entry"](../standard-library/directory-entry-class.md) wird im Vergleich zu den `directory_entry`.

## <a name="path_type"></a> Operator const Path_type &

Der Memberoperator gibt `mypath`zurück.

```cpp
operator const std::experimental::filesystem::path&() const;
```

## <a name="path"></a> Pfad

Die Memberfunktion gibt `mypath`zurück.

```cpp
const std::experimental::filesystem::path& path() const noexcept;
```

## <a name="replace_filename"></a> replace_filename

Die Memberfunktion ersetzt `mypath` mit `mypath.parent_path()`  /  *"pval"*, `mystat` mit *Stat_arg*, und `mysymstat` mit *"symstat_arg"*

```cpp
void replace_filename(
    const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>Parameter

*"pval"*<br/>
Der gespeicherte Dateinamenpfad.

*stat_arg*<br/>
Der Status des gespeicherten Dateinamens.

*"symstat_arg"*<br/>
Den symbolischen Linkstatus des gespeicherten Dateinamens.

## <a name="status"></a> Status

Beide Memberfunktionen geben `mystat` möglicherweise zunächst wie folgt geändert:

1. Wenn `status_known(mystat)` keinen weiteren Schritt ausführen.

1. Andernfalls gilt: Wenn `!status_known(mysymstat) && !is_symlink(mysymstat)` dann `mystat = mysymstat`.

```cpp
file_status status() const;
file_status status(error_code& ec) const noexcept;
```

### <a name="parameters"></a>Parameter

*EC*<br/>
Der Statuscode Fehler.

## <a name="symlink_status"></a> "symlink_status"

Beide Memberfunktionen geben `mysymstat` möglicherweise zunächst wie folgt geändert: Wenn `status_known(mysymstat)` keinen weiteren Schritt ausführen. Andernfalls `mysymstat = symlink_status(mypval)`.

```cpp
file_status symlink_status() const;
file_status symlink_status(error_code& ec) const noexcept;
```

### <a name="parameters"></a>Parameter

*EC*<br/>
Der Statuscode Fehler.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<Dateisystem&gt;](../standard-library/filesystem.md)<br/>
