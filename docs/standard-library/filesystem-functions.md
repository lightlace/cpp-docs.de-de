---
title: '&lt;filesystem&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 09/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- FILESYSTEM/std::experimental::filesystem::absolute
- FILESYSTEM/std::experimental::filesystem::canonical
- FILESYSTEM/std::experimental::filesystem::copy
- FILESYSTEM/std::experimental::filesystem::copy_file
- FILESYSTEM/std::experimental::filesystem::copy_symlink
- FILESYSTEM/std::experimental::filesystem::create_directories
- FILESYSTEM/std::experimental::filesystem::create_directory
- FILESYSTEM/std::experimental::filesystem::create_directory_symlink
- FILESYSTEM/std::experimental::filesystem::create_hard_link
- FILESYSTEM/std::experimental::filesystem::create_symlink
- FILESYSTEM/std::experimental::filesystem::current_path
- FILESYSTEM/std::experimental::filesystem::equivalent
- FILESYSTEM/std::experimental::filesystem::exists
- FILESYSTEM/std::experimental::filesystem::file_size
- FILESYSTEM/std::experimental::filesystem::hard_link_count
- FILESYSTEM/std::experimental::filesystem::hash_value
- FILESYSTEM/std::experimental::filesystem::is_block_file
- FILESYSTEM/std::experimental::filesystem::is_character_file
- FILESYSTEM/std::experimental::filesystem::is_directory
- FILESYSTEM/std::experimental::filesystem::is_empty
- FILESYSTEM/std::experimental::filesystem::is_fifo
- FILESYSTEM/std::experimental::filesystem::is_other
- FILESYSTEM/std::experimental::filesystem::is_regular_file
- FILESYSTEM/std::experimental::filesystem::is_socket
- FILESYSTEM/std::experimental::filesystem::is_symlink
- FILESYSTEM/std::experimental::filesystem::last_write_time
- FILESYSTEM/std::experimental::filesystem::permissions
- FILESYSTEM/std::experimental::filesystem::read_symlink
- FILESYSTEM/std::experimental::filesystem::remove
- FILESYSTEM/std::experimental::filesystem::remove_all
- FILESYSTEM/std::experimental::filesystem::rename
- FILESYSTEM/std::experimental::filesystem::resize_file
- FILESYSTEM/std::experimental::filesystem::space
- FILESYSTEM/std::experimental::filesystem::status
- FILESYSTEM/std::experimental::filesystem::status_known
- FILESYSTEM/std::experimental::filesystem::swap
- FILESYSTEM/std::experimental::filesystem::symlink_status
- FILESYSTEM/std::experimental::filesystem::system_complete
- FILESYSTEM/std::experimental::filesystem::temp_directory_path
- FILESYSTEM/std::experimental::filesystem::u8path
dev_langs:
- C++
ms.assetid: be3cb821-4728-4d47-ab78-858fa8aa5045
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::experimental::filesystem::absolute
- std::experimental::filesystem::canonical
- std::experimental::filesystem::copy
- std::experimental::filesystem::copy_file
- std::experimental::filesystem::copy_symlink
- std::experimental::filesystem::create_directories
- std::experimental::filesystem::create_directory
- std::experimental::filesystem::create_directory_symlink
- std::experimental::filesystem::create_hard_link
- std::experimental::filesystem::create_symlink
- std::experimental::filesystem::current_path
- std::experimental::filesystem::equivalent
- std::experimental::filesystem::exists
- std::experimental::filesystem::file_size
- std::experimental::filesystem::hard_link_count
- std::experimental::filesystem::hash_value
- std::experimental::filesystem::is_block_file
- std::experimental::filesystem::is_character_file
- std::experimental::filesystem::is_directory
- std::experimental::filesystem::is_empty
- std::experimental::filesystem::is_fifo
- std::experimental::filesystem::is_other
- std::experimental::filesystem::is_regular_file
- std::experimental::filesystem::is_socket
- std::experimental::filesystem::is_symlink
- std::experimental::filesystem::last_write_time
- std::experimental::filesystem::permissions
- std::experimental::filesystem::read_symlink
- std::experimental::filesystem::remove
- std::experimental::filesystem::remove_all
- std::experimental::filesystem::rename
- std::experimental::filesystem::resize_file
- std::experimental::filesystem::space
- std::experimental::filesystem::status
- std::experimental::filesystem::status_known
- std::experimental::filesystem::swap
- std::experimental::filesystem::symlink_status
- std::experimental::filesystem::system_complete
- std::experimental::filesystem::temp_directory_path
- std::experimental::filesystem::u8path
ms.workload:
- cplusplus
ms.openlocfilehash: 8fcf7260b6bb10e317a3244ee11b4a92658daf45
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063301"
---
# <a name="ltfilesystemgt-functions"></a>&lt;filesystem&gt;-Funktionen

Diese freien Funktionen im [\<filesystem>](../standard-library/filesystem.md)-Header führen Änderungs- und Abfragevorgänge für Pfade, Dateien, symbolische Verknüpfungen, Verzeichnisse und Volumes durch. Weitere Informationen und Codebeispiele finden Sie unter [Dateisystemnavigation](../standard-library/file-system-navigation.md).
||||
|-|-|-|
|[absolute](#absolute)|[begin](#begin)|[canonical](#canonical)|
|[copy](#copy)|[copy_file](#copy_file)|[copy_symlink](#copy_symlink)|
|[create_directories-Funktion](#create_directories)|[create_directory](#create_directory)|[create_directory_symlink](#create_directory_symlink)|
|[create_hard_link](#create_hard_link)|[create_symlink](#create_symlink)|[current_path](#current_path)|
|[end](#end)|[equivalent](#equivalent)|[exists](#exists)|
|[file_size](#file_size)|[hard_link_count](#hard_link_count)|[hash_value](#hash_value)|
|[is_block_file](#is_block_file)|[is_character_file](#is_character_file)|[is_directory](#is_directory)|
|[is_empty](#is_empty)|[is_fifo](#is_fifo)|[is_other](#is_other)|
|[is_regular_file](#is_regular_file)|[is_socket](#is_socket)|[is_symlink](#is_symlink)|
|[last_write_time](#last_write_time)|[permissions](#permissions)|[read_symlink](#read_symlink)|
|[remove](#remove)|[remove_all](#remove_all)|[rename](#rename)|
|[resize_file](#resize_file)|[space](#space)|[Status](#status)|
|[status_known](#status_known)|[swap](#swap)|[symlink_status](#symlink_status)|
|[system_complete](#system_complete)|[temp_directory_path](#temp_directory_path)|[u8path](#u8path)|

## <a name="absolute"></a> absolute

```cpp
path absolute(const path& pval, const path& base = current_path());
```

Die Funktion gibt den absoluten Pfadnamen entspricht *"pval"* relativ zum Pfadnamen `base`:

1. Wenn `pval.has_root_name() && pval.has_root_directory()` die Funktion gibt *"pval"*.

1. Wenn `pval.has_root_name() && !pval.has_root_directory()` die Funktion gibt `pval.root_name()`  /  `absolute(base).root_directory()`  /  `absolute(base).relative_path()`  /  `pval.relative_path()`.

1. Wenn `!pval.has_root_name() && pval.has_root_directory()` die Funktion gibt `absolute(base).root_name()`  /  *"pval"*.

1. Wenn `!pval.has_root_name() && !pval.has_root_directory()` die Funktion gibt `absolute(base)`  /  *"pval"*.

## <a name="begin"></a>  begin

```cpp
const directory_iterator& begin(const directory_iterator& iter) noexcept;
const recursive_directory_iterator&
    begin(const recursive_directory_iterator& iter) noexcept;
```

Beide Funktionen geben *Iter*.

## <a name="canonical"></a>  canonical

```cpp
path canonical(const path& pval, const path& base = current_path());
path canonical(const path& pval, error_code& ec);
path canonical(const path& pval, const path& base, error_code& ec);
```

Die Funktionen bilden einen absoluten Pfadnamen `pabs = absolute(pval, base)` (oder `pabs = absolute(pval)` für die Überladung ohne basisparameter), und reduzieren ihn dann auf eine kanonische Form in der folgenden Reihenfolge der Schritte aus:

1. Jede Pfadkomponente `X` für die `is_symlink(X)` ist **"true"** Fassung `read_symlink(X)`.

1. Jede Pfadkomponente `.` (Punkt ist das aktuelle Verzeichnis hergestellt, indem die vorherigen Pfadkomponenten) wird entfernt.

1. Jedes Paar von Pfadkomponenten `X` / `..` (Punkt-Punkt ist das übergeordnete Verzeichnis hergestellt, indem die vorherigen Pfadkomponenten) wird entfernt.

Die Funktion gibt dann zurück `pabs`.

## <a name="copy"></a>  copy

```cpp
void copy(const path& from, const path& to);
void copy(const path& from, const path& to, error_code& ec) noexcept;
void copy(const path& from, const path& to, copy_options opts);
void copy(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

Die Funktionen kopieren oder verknüpfen Sie eine oder mehrere Dateien auf alle möglicherweise *aus* zu *zu* unter Kontrolle des *"OPTS"*, die als genommen wird `copy_options::none` für die Überladungen ohne *"OPTS"* Parameter. *"OPTS"* darf höchstens ein enthalten:

- `skip_existing`, `overwrite_existing`oder `update_existing`

- `copy_symlinks` oder `skip_symlinks`

- `directories_only`, `create_symlinks`oder `create_hard_links`

Die Funktionen bestimmen zunächst die File_status-Werte `f` für *aus* und `t` für *zu*:

- Wenn `opts & (copy_options::create_symlinks | copy_options::skip_symlinks)`, durch den Aufruf `symlink_status`

- andernfalls durch den Aufruf `status`

- Andernfalls wird ein Fehler gemeldet.

Wenn `!exists(f) || equivalent(f, t) || is_other(f) || is_other(t) || is_directory(f)&& is_regular_file(t)`, anschließend ein Fehler gemeldet (und kein).

Andernfalls gilt: Wenn `is_symlink(f)` dann:

- Wenn `options & copy_options::skip_symlinks` keinen weiteren Schritt ausführen.

- Andernfalls gilt: Wenn `!exists(t)&& options & copy_options::copy_symlinks` dann `copy_symlink(from, to, opts)`.

- Andernfalls wird ein Fehler gemeldet.

Andernfalls gilt: Wenn `is_regular_file(f)` dann:

- Wenn `opts & copy_options::directories_only` keinen weiteren Schritt ausführen.

- Andernfalls gilt: Wenn `opts & copy_options::create_symlinks` dann `create_symlink(to, from)`.

- Andernfalls gilt: Wenn `opts & copy_options::create_hard_links` dann `create_hard_link(to, from)`.

- Andernfalls gilt: Wenn `is_directory(f)` dann `copy_file(from, to`  /  `from.filename(), opts)`.

- Andernfalls `copy_file(from, to, opts)`.

Andernfalls gilt: Wenn `is_directory(f) && (opts & copy_options::recursive || !opts)` dann:

```cpp
if (!exists(t))
{  // copy directory contents recursively
    create_directory(to, from, ec);

    for (directory_iterator next(from), end; ec == error_code() && next != end; ++next)
    {
        copy(next->path(), to / next->path().filename(), opts, ec);
    }
}
```

Andernfalls keinen weiteren Schritt ausführen.

## <a name="copy_file"></a>  copy_file

```cpp
bool copy_file(const path& from, const path& to);
bool copy_file(const path& from, const path& to, error_code& ec) noexcept;
bool copy_file(const path& from, const path& to, copy_options opts);
bool copy_file(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

Die Funktionen kopieren alle möglicherweise eine Datei *aus* zu *zu* unter Kontrolle des *"OPTS"*, die als stammt `copy_options::none` für die Überladungen ohne *"OPTS"*  Parameter. *"OPTS"* darf höchstens ein enthalten `skip_existing`, `overwrite_existing`, oder `update_existing`.

Wenn `exists(to) && !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options::update_existing))` klicken Sie dann einen Bericht als einen Fehler, der die Datei bereits vorhanden.

Andernfalls gilt: Wenn `!exists(to) || opts & copy_options::overwrite_existing || opts & copy_options::update_existing&& last_write_time(to) < last_write_time(from) || !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options:update_existing))` dann versuchen, den Inhalt und Attribute der Datei kopieren *aus* in die Datei *zu*. Wenn beim Kopierversuch ein Fehler auftritt, diesen dann melden.

Die Funktionen geben **"true"** , wenn die Kopie versucht und erfolgreich; andernfalls ist **"false"**.

## <a name="copy_symlink "></a>  copy_symlink

```cpp
void copy_symlink(const path& from, const path& to);
void copy_symlink(const path& from, const path& to, error_code& ec) noexcept;
```

Wenn `is_directory(from)` Funktionsaufrufe `create_directory_symlink(from, to)`. Andernfalls ruft sie `create_symlink(from, to)`.

## <a name="create_directories"></a>  create_directories-Funktion

```cpp
bool create_directories(const path& pval);
bool create_directories(const path& pval, error_code& ec) noexcept;
```

Für einen Pfadnamen wie „a\/b\/c“ erstellt die Funktion bei Bedarf die Verzeichnisse „a“ und „a\/b“, damit sie bei Bedarf das Verzeichnis „a\/b\/c“ erstellen kann. Es gibt **"true"** nur dann, wenn es sich tatsächlich um das Verzeichnis erstellt *"pval"*.

## <a name="create_directory"></a>  create_directory

```cpp
bool create_directory(const path& pval);

bool create_directory(const path& pval, error_code& ec) noexcept;
bool create_directory(const path& pval, const path& attr);
bool create_directory(const path& pval, const path& attr, error_code& ec) noexcept;
```

Die Funktion erstellt das Verzeichnis *"pval"* je nach Bedarf. Es gibt nur true zurück, wenn es sich tatsächlich um das Verzeichnis erstellt *"pval"*, in diesem Fall kopiert sie Berechtigungen aus der vorhandenen Datei *Attr*, oder `perms::all` für die Überladungen ohne *Attr*  Parameter.

## <a name="create_directory_symlink "></a>  create_directory_symlink

```cpp
void create_directory_symlink(const path& to, const path& link);
void create_directory_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

Die Funktion erstellt Links als symbolische Verknüpfung zu dem Verzeichnis *zu*.

## <a name="create_hard_link"></a>  create_hard_link

```cpp
void create_hard_link(const path& to,  const path& link);
void create_hard_link(const path& to, const path& link, error_code& ec) noexcept;
```

Die Funktion erstellt eine Verknüpfung als festen Link für das Verzeichnis oder Datei *zu*.

## <a name="create_symlink "></a>  create_symlink

```cpp
void create_symlink(const path& to,  const path& link);

void create_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

Die Funktion erstellt *Link* als eine symbolische Verknüpfung zu der Datei *zu*.

## <a name="current_path"></a>  current_path

```cpp
path current_path();
path current_path(error_code& ec);
void current_path(const path& pval);
void current_path(const path& pval, error_code& ec) noexcept;
```

Die Funktionen ohne Parameter *"pval"* geben den Pfadnamen für das aktuelle Verzeichnis zurück. Die übrigen Funktionen legen das aktuelle Verzeichnis auf *"pval"*.

## <a name="end"></a>  end

```cpp
directory_iterator& end(const directory_iterator& iter) noexcept;
recursive_directory_iterator& end(const recursive_directory_iterator& iter) noexcept;
```

Die erste Funktion gibt `directory_iterator()` und die zweite Funktion zurück `recursive_directory_iterator()`

## <a name="equivalent"></a>  equivalent

```cpp
bool equivalent(const path& left, const path& right);
bool equivalent(const path& left, const path& right, error_code& ec) noexcept;
```

Die Funktionen geben **"true"** nur, wenn *linken* und *rechten* dieselbe dateisystementität festlegen.

## <a name="exists"></a>  exists

```cpp
bool exists(file_status stat) noexcept;
bool exists(const path& pval);
bool exists(const path& pval, error_code& ec) noexcept;
```

Diese erste Funktion gibt `status_known && stat.type() != file_not_found` zurück. Die zweiten und dritten Funktionen geben `exists(status(pval))`.

## <a name="file_size"></a>  file_size

```cpp
uintmax_t file_size(const path& pval);
uintmax_t file_size(const path& pval, error_code& ec) noexcept;
```

Die Funktionen geben die Größe in Bytes der Datei vom angegebenen *"pval"*, wenn `exists(pval) && is_regular_file(pval)` und die Dateigröße bestimmt werden kann. Andernfalls sie einen Fehler melden und zurückgeben `uintmax_t(-1)`.

## <a name="hard_link_count"></a>  hard_link_count

```cpp
uintmax_t hard_link_count(const path& pval);
uintmax_t hard_link_count(const path& pval, error_code& ec) noexcept;
```

Die Funktion gibt die Anzahl der festen Links für *"pval"*, oder \-1, wenn ein Fehler auftritt.

## <a name="hash_value"></a>  hash_value

```cpp
size_t hash_value(const path& pval) noexcept;
```

Die Funktion gibt einen Hashwert für `pval.native()`.

## <a name="is_block_file"></a>  is_block_file

```cpp
bool is_block_file(file_status stat) noexcept;
bool is_block_file(const path& pval);
bool is_block_file(const path& pval, error_code& ec) noexcept;
```

Diese erste Funktion gibt `stat.type() == file_type::block` zurück. Die übrigen Funktionen Rückgabe `is_block_file(status(pval))`.

## <a name="is_character_file"></a>  is_character_file

```cpp
bool is_character_file(file_status stat) noexcept;
bool is_character_file(const path& pval);
bool is_character_file(const path& pval, error_code& ec) noexcept;
```

Diese erste Funktion gibt `stat.type() == file_type::character` zurück. Die übrigen Funktionen Rückgabe `is_character_file(status(pval))`.

## <a name="is_directory "></a>  is_directory

```cpp
bool is_directory(file_status stat) noexcept;
bool is_directory(const path& pval);
bool is_directory(const path& pval, error_code& ec) noexcept;
```

Diese erste Funktion gibt `stat.type() == file_type::directory` zurück. Die übrigen Funktionen Rückgabe `is_directory_file(status(pval))`.

## <a name="is_empty"></a>  is_empty

```cpp
bool is_empty(file_status stat) noexcept;
bool is_empty(const path& pval);
bool is_empty(const path& pval, error_code& ec) noexcept;
```

Wenn `is_directory(pval)` gibt die Funktion `directory_iterator(pval) == directory_iterator()`; andernfalls `file_size(pval) == 0`.

## <a name="is_fifo"></a>  is_fifo

```cpp
bool is_fifo(file_status stat) noexcept;
bool is_fifo(const path& pval);
bool is_fifo(const path& pval, error_code& ec) noexcept;
```

Diese erste Funktion gibt `stat.type() == file_type::fifo` zurück. Die übrigen Funktionen Rückgabe `is_fifo(status(pval))`.

## <a name="is_other"></a>  is_other

```cpp
bool is_other(file_status stat) noexcept;
bool is_other(const path& pval);
bool is_other(const path& pval, error_code& ec) noexcept;
```

Diese erste Funktion gibt `stat.type() == file_type::other` zurück. Die übrigen Funktionen Rückgabe `is_other(status(pval))`.

## <a name="s_regular_file"></a>  is_regular_file

```cpp
bool is_regular_file(file_status stat) noexcept;
bool is_regular_file(const path& pval);
bool is_regular_file(const path& pval, error_code& ec) noexcept;
```

Diese erste Funktion gibt `stat.type() == file_type::regular` zurück. Die übrigen Funktionen Rückgabe `is_regular_file(status(pval))`.

## <a name="is_socket"></a>  is_socket

```cpp
bool is_socket(file_status stat) noexcept;
bool is_socket(const path& pval);
bool is_socket(const path& pval, error_code& ec) noexcept;
```

Diese erste Funktion gibt `stat.type() == file_type::socket` zurück. Die übrigen Funktionen Rückgabe `is_socket(status(pval))`.

## <a name="is_symlink"></a>  is_symlink

```cpp
bool is_symlink(file_status stat) noexcept;
bool is_symlink(const path& pval);
bool is_symlink(const path& pval, error_code& ec) noexcept;
```

Diese erste Funktion gibt `stat.type() == file_type::symlink` zurück. Die übrigen Funktionen Rückgabe `is_symlink(status(pval))`.

## <a name="last_write_time"></a>  last_write_time

```cpp
file_time_type last_write_time(const path& pval);
file_time_type last_write_time(const path& pval, error_code& ec) noexcept;
void last_write_time(const path& pval, file_time_type new_time);
void last_write_time(const path& pval, file_time_type new_time, error_code& ec) noexcept;
```

Die ersten beiden Funktionen geben den Zeitpunkt der letzten Datenänderung für *"pval"*, oder `file_time_type(-1)` Wenn ein Fehler auftritt. Die letzten beiden Funktionen legen die Uhrzeit der letzten Datenänderung für *"pval"* zu *New_time*.

## <a name="permissions"></a>  permissions

```cpp
void permissions(const path& pval, perms mask);
void permissions(const path& pval, perms mask, error_code& ec) noexcept;
```

Die Funktionen legen die Berechtigungen für den Pfadnamen, die vom angegebenen *"pval"* zu `mask & perms::mask` unter Kontrolle des `perms & (perms::add_perms | perms::remove_perms)`. *Maske* darf höchstens ein enthalten `perms::add_perms` und `perms::remove_perms`.

Wenn `mask & perms::add_perms` die Funktionen legen die Berechtigungen auf `status(pval).permissions() | mask & perms::mask`. Andernfalls gilt: Wenn `mask & perms::remove_perms` die Funktionen legen die Berechtigungen auf `status(pval).permissions() & ~(mask & perms::mask)`. Andernfalls die Funktionen legen die Berechtigungen auf `mask & perms::mask`.

## <a name="read_symlink"></a>  read_symlink

```cpp
path read_symlink(const path& pval);
path read_symlink(const path& pval, error_code& ec);
```

Die Funktionen melden einen Fehler und zurückgeben `path()` Wenn `!is_symlink(pval)`. Andernfalls geben die Funktionen ein Objekt vom Typ `path` zurück, das die symbolische Verknüpfung enthält.

## <a name="remove"></a>  remove

```cpp
bool remove(const path& pval);
bool remove(const path& pval, error_code& ec) noexcept;
```

Die Funktionen geben **"true"** nur, wenn `exists(symlink_status(pval))` und die Datei erfolgreich entfernt wurde. Die symbolische Verknüpfung selbst wird entfernt und nicht die von ihr bestimmte Datei.

## <a name="remove_all"></a>  remove_all

```cpp
uintmax_t remove_all(const path& pval);
uintmax_t remove_all(const path& pval, error_code& ec) noexcept;
```

Wenn *"pval"* ist ein Verzeichnis, die rekursiv Funktionen alle Verzeichniseinträge, und klicken Sie dann auf den Eintrag selbst zu entfernen. Rufen Sie andernfalls auf die Funktionen `remove`. Sie geben die Anzahl aller Elemente zurück, die erfolgreich entfernt wurden.

## <a name="rename"></a>  rename

```cpp
void rename(const path& from,  const path& to);
void rename(const path& from,  const path& to, error_code& ec) noexcept;
```

Die Funktionen benennen *aus* zu *zu*. Die symbolische Verknüpfung selbst wird umbenannt und nicht die von ihr bestimmte Datei.

## <a name="resize_file"></a>  resize_file

```cpp
void resize(const path& pval, uintmax_t size);
void resize(const path& pval, uintmax_t size, error_code& ec) noexcept;
```

Die Funktionen ändern die Größe einer Datei, `file_size(pval) == size`

## <a name="space"></a>  space

```cpp
space_info space(const path& pval);
space_info space(const path& pval, error_code& ec) noexcept;
```

Die Funktion gibt Informationen über das Volume, das vom angegebenen *"pval"*, in einer Struktur vom Typ `space_info`. Die Struktur enthält `uintmax_t(-1)` für jeden Wert, der nicht bestimmt werden kann.

## <a name="status"></a>  Status

```cpp
file_status status(const path& pval);
file_status status(const path& pval, error_code& ec) noexcept;
```

Die Funktionen geben den Status des Pfadnamens, den Dateityp und die zugeordneten Berechtigungen *"pval"*. Die symbolische Verknüpfung selbst wird nicht getestet, dafür aber die von ihr bestimmte Datei.

## <a name="status_known"></a>  status_known

```cpp
bool status_known(file_status stat) noexcept;
```

Gibt die Funktion zurück `stat.type() != file_type::none`

## <a name="swap"></a>  swap

```cpp
void swap(path& left, path& right) noexcept;
```

Die Funktion vertauscht den Inhalt der *linken* und *rechten*.

## <a name="symlink_status"></a>  symlink_status

```cpp
file_status symlink_status(const path& pval);
file_status symlink_status(const path& pval, erroxr_code& ec) noexcept;
```

Die Funktionen geben "Symlink" den Status des Pfadnamens, den Dateityp und die zugeordneten Berechtigungen *"pval"*. Die Funktionen verhalten sich identisch zu `status(pval)` mit dem Unterschied, dass eine symbolische Verknüpfung selbst getestet und wird nicht auf die Datei festlegt.

## <a name="system_complete"></a>  system_complete

```cpp
path system_complete(const path& pval);
path system_complete(const path& pval, error_code& ec);
```

Die Funktionen geben einen absoluten Pfadnamen zurück, der bei Bedarf das aktuelle Verzeichnis berücksichtigt, das seinem Stammnamen zugeordnet ist. \(Für Posix geben die Funktionen `absolute(pval)`.\)

## <a name="temp_directory_path"></a>  temp_directory_path

```cpp
path temp_directory_path();
path temp_directory_path(error_code& ec);
```

Die Funktionen geben einen Pfadnamen für ein Verzeichnis zurück, das für die Aufnahme temporärer Dateien geeignet ist.

## <a name="u8path"></a>  u8path

```cpp
template <class Source>
path u8path(const Source& source);

template <class InIt>
path u8path(InIt first, InIt last);
```

Die erste Funktion verhält sich wie `path(source)` und die zweite Funktion verhält sich wie `path(first, last)` mit dem Unterschied, dass die angegebene Quelle in beiden Fällen als Sequenz von Char-Elemente, die als UTF-8 codiert sind, unabhängig vom Dateisystem verwendet wird.
