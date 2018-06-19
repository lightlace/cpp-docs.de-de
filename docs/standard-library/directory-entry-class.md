---
title: directory_entry-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: 1827c67b-4137-4548-adb0-f955f7acaf08
author: corob-msft
ms.author: corob
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
ms.workload:
- cplusplus
ms.openlocfilehash: 9a55109683a18415638cacd9cd15dbcaa3164fc8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33846931"
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

## <a name="assign"></a>assign

```cpp
void assign(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

Die Memberfunktion weist „pval“ zu „mypath“, „stat“ zu „mystat“ und „symstat“ zu „mysymstat“ zu.

## <a name="directoryentry"></a>directory_entry

```cpp
directory_entry() = default;
directory_entry(const directory_entry&) = default;
directory_entry(directory_entry&&) noexcept = default;
explicit directory_entry(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

Die als Standard festgelegten Konstruktoren verhalten sich wie erwartet. Der vierte Konstruktor initialisiert „mypath“ für „pval“, „mystat“ für „stat_arg“ und „mysymstat“ für „symstat_arg“.

## <a name="operator"></a>Operator!=

```cpp
bool operator!=(const directory_entry& right) const noexcept;
```

Die Memberfunktion gibt „!(*this == right)“ zurück.

## <a name="operator"></a>operator =

```cpp
directory_entry& operator=(const directory_entry&) = default;
directory_entry& operator=(directory_entry&&) noexcept = default;
```

Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.

## <a name="operator"></a>operator==

```cpp
bool operator==(const directory_entry& right) const noexcept;
```

Die Memberfunktion gibt „mypath == right.mypath“ zurück.

## <a name="operatorlt"></a>Operator&lt;

```cpp
bool operator<(const directory_entry& right) const noexcept;
```

Die Memberfunktion gibt "myPath" &lt; right.mypath.

## <a name="operatorlt"></a>operator&lt;=

```cpp
bool operator&lt;=(const directory_entry& right) const noexcept;
```

Die Memberfunktion gibt „!(right \< *this)“ zurück.

## <a name="operatorgt"></a>Operator&gt;

```cpp
bool operator&gt;(const directory_entry& right) const noexcept;
```

Die Memberfunktion gibt „right \< *this“ zurück.

## <a name="operatorgt"></a>operator&gt;=

```cpp
bool operator&gt;=(const directory_entry& right) const noexcept;
```

Die Memberfunktion gibt! (* dies \< rechten).

## <a name="operator-const-pathtype"></a>operator const path_type&

```cpp
operator const std::experimental::filesystem::path&() const;
```

Der Memberoperator gibt „mypath“ zurück.

## <a name="path"></a>path

```cpp
const std::experimental::filesystem::path& path() const noexcept;
```

Die Memberfunktion gibt „mypath“ zurück.

## <a name="replacefilename"></a>replace_filename

```cpp
void replace_filename(
    const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

Die Memberfunktion ersetzt „mypath“ durch „mypath.parent_path() / pval“, „mystat“ durch „stat_arg“ und „mysymstat“ durch „symstat_arg“.

## <a name="status"></a>Status

```cpp
file_status status() const;
file_status status(error_code& ec) const noexcept;
```

Beide Memberfunktionen geben „mystat“ möglicherweise zunächst wie folgt geändert zurück:

1. Bei „status_known(mystat)“ keinen weiteren Schritt ausführen.

1. Andernfalls gilt bei „!status_known(mysymstat) && !is_symlink(mysymstat)“ dann „mystat = mysymstat“.

## <a name="symlinkstatus"></a>symlink_status

```cpp
file_status symlink_status() const;
file_status symlink_status(error_code& ec) const noexcept;
```

Beide Memberfunktionen geben „mysymstat“ möglicherweise zunächst wie folgt geändert zurück: Bei „status_known(mysymstat)“ keinen weiteren Schritt ausführen. Andernfalls gilt „mysymstat = symlink_status(mypval)“.

## <a name="requirements"></a>Anforderungen

**Header:** \<experimentellen/Filesystem&gt;

**Namespace:** std::experimental::filesystem

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<Dateisystem&gt;](../standard-library/filesystem.md)<br/>
