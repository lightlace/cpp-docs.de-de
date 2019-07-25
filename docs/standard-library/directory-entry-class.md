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
ms.openlocfilehash: 35b0dc55bf5db2f799d9ade28cd5968ceab3332b
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458961"
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
|[directory_entry](#directory_entry)|Die als Standard festgelegten Konstruktoren verhalten sich wie erwartet. Der vierte Konstruktor initialisiert `mypath` zu *PVal*, `mystat` *stat_arg*und `mysymstat` *symstat_arg*.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[assign](#assign)|Die Member-Funktion weist *PVal* `mypath`to, *stat* to `mystat`und *"symstat"* zu `mysymstat`.|
|[path](#path)|Die Memberfunktion gibt `mypath`zurück.|
|[replace_filename](#replace_filename)|Die Member-Funktion `mypath` ersetzt `mypath.parent_path()`  / durch *PVal*, `mystat` durch *stat_arg*und `mysymstat` durch *symstat_arg* .|
|[Status](#status)|Beide Member-Funktionen `mystat` geben möglicherweise zuerst eine Änderung zurück.|
|[symlink_status](#symlink_status)|Beide Member-Funktionen `mysymstat` geben möglicherweise zuerst eine Änderung zurück.|

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
|[Operator Konstanten path_type &](#path_type)|Gibt `mypath`zurück.|

## <a name="requirements"></a>Anforderungen

**Header:** \<experimentell/Dateisystem&gt;

**Namespace:** std::experimental::filesystem

## <a name="assign"></a>einräumen

Die Member-Funktion weist " *PVal* to `mypath`" `mystat`, " *stat_arg* to `mysymstat`" und " *symstat_arg* " zu.

```cpp
void assign(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>Parameter

*PVAL*\
Der gespeicherte Dateiname-Pfad.

*stat_arg*\
Der Status des gespeicherten Datei namens.

*symstat_arg*\
Der symbolische Verknüpfungs Status des gespeicherten Datei namens.

## <a name="directory_entry"></a>directory_entry

Die als Standard festgelegten Konstruktoren verhalten sich wie erwartet. Der vierte Konstruktor initialisiert `mypath` zu *PVal*, `mystat` *stat_arg*und `mysymstat` *symstat_arg*.

```cpp
directory_entry() = default;
directory_entry(const directory_entry&) = default;
directory_entry(directory_entry&&) noexcept = default;
explicit directory_entry(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>Parameter

*PVAL*\
Der gespeicherte Dateiname-Pfad.

*stat_arg*\
Der Status des gespeicherten Datei namens.

*symstat_arg*\
Der symbolische Verknüpfungs Status des gespeicherten Datei namens.

## <a name="op_neq"></a>Operator! =

Die Memberfunktion gibt `!(*this == right)`zurück.

```cpp
bool operator!=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parameter

*Richting*\
Der [directory_entry](../standard-library/directory-entry-class.md) , der mit dem `directory_entry`verglichen wird.

## <a name="op_as"></a>Operator =

Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.

```cpp
directory_entry& operator=(const directory_entry&) = default;
directory_entry& operator=(directory_entry&&) noexcept = default;
```

### <a name="parameters"></a>Parameter

*Richting*\
Das [directory_entry](../standard-library/directory-entry-class.md) , das in das `directory_entry`kopiert wird.

## <a name="op_eq"></a>Operator = =

Die Memberfunktion gibt `mypath == right.mypath`zurück.

```cpp
bool operator==(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parameter

*Richting*\
Der [directory_entry](../standard-library/directory-entry-class.md) , der mit dem `directory_entry`verglichen wird.

## <a name="op_lt"></a>-Operator&lt;

Die Memberfunktion gibt `mypath < right.mypath`zurück.

```cpp
bool operator<(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parameter

*Richting*\
Der [directory_entry](../standard-library/directory-entry-class.md) , der mit dem `directory_entry`verglichen wird.

## <a name="op_lteq"></a>KOM&lt;=

Die Memberfunktion gibt `!(right < *this)`zurück.

```cpp
bool operator&lt;=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parameter

*Richting*\
Der [directory_entry](../standard-library/directory-entry-class.md) , der mit dem `directory_entry`verglichen wird.

## <a name="op_gt"></a>-Operator&gt;

Die Memberfunktion gibt `right < *this`zurück.

```cpp
bool operator&gt;(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parameter

*Richting*\
Der [directory_entry](../standard-library/directory-entry-class.md) , der mit dem `directory_entry`verglichen wird.

## <a name="op_gteq"></a>KOM&gt;=

Die Memberfunktion gibt `!(*this < right)`zurück.

```cpp
bool operator&gt;=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parameter

*Richting*\
Der [directory_entry](../standard-library/directory-entry-class.md) , der mit dem `directory_entry`verglichen wird.

## <a name="path_type"></a>Operator Konstanten path_type &

Der Memberoperator gibt `mypath`zurück.

```cpp
operator const std::experimental::filesystem::path&() const;
```

## <a name="path"></a>ADS

Die Memberfunktion gibt `mypath`zurück.

```cpp
const std::experimental::filesystem::path& path() const noexcept;
```

## <a name="replace_filename"></a>replace_filename

Die Member-Funktion `mypath` ersetzt `mypath.parent_path()`  / durch *PVal*, `mystat` durch *stat_arg*und `mysymstat` durch *symstat_arg* .

```cpp
void replace_filename(
    const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>Parameter

*PVAL*\
Der gespeicherte Dateiname-Pfad.

*stat_arg*\
Der Status des gespeicherten Datei namens.

*symstat_arg*\
Der symbolische Verknüpfungs Status des gespeicherten Datei namens.

## <a name="status"></a>Stands

Beide Member-Funktionen `mystat` geben möglicherweise zuerst wie folgt zurück:

1. Wenn `status_known(mystat)` Sie dann nichts tun.

1. `!status_known(mysymstat) && !is_symlink(mysymstat)` Andernfalls .`mystat = mysymstat`

```cpp
file_status status() const;
file_status status(error_code& ec) const noexcept;
```

### <a name="parameters"></a>Parameter

*EC*\
Der Status Fehlercode.

## <a name="symlink_status"></a> symlink_status

Beide Member-Funktionen `mysymstat` geben möglicherweise zuerst wie folgt zurück: Wenn `status_known(mysymstat)` Sie dann nichts tun. Andernfalls `mysymstat = symlink_status(mypval)`.

```cpp
file_status symlink_status() const;
file_status symlink_status(error_code& ec) const noexcept;
```

### <a name="parameters"></a>Parameter

*EC*\
Der Status Fehlercode.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[\<verwendet&gt;](../standard-library/filesystem.md)
