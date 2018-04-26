---
title: '&lt;filesystem&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
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
ms.openlocfilehash: 93304322359b7f0d5e16c2a5452eefc5a839c2b4
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
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


## <a name=""></a>  <a name="absolute"></a> absolute

```cpp
path absolute(const path& pval, const path& base = current_path());
```

Die Funktion gibt den absoluten Pfadnamen, der `pval` entspricht, relativ zum Pfadnamen `base` zurück:

1. Bei „pval.has_root_name() && pval.has_root_directory()“ gibt die Funktion „pval“ zurück.

1. Bei „pval.has_root_name() && !pval.has_root_directory()“ gibt die Funktion „pval.root_name() / absolute(base).root_directory() / absolute(base).relative_path() / pval.relative_path()“ zurück.

1. Bei „!pval.has_root_name() && pval.has_root_directory()“ gibt die Funktion „absolute(base).root_name() / pval“ zurück.

1. Bei „!pval.has_root_name() && !pval.has_root_directory()“ gibt die Funktion „absolute(base) / pval“ zurück.

## <a name="begin"></a> begin

```cpp
const directory_iterator& begin(const directory_iterator& iter) noexcept;
const recursive_directory_iterator&
    begin(const recursive_directory_iterator& iter) noexcept;
```

Beide Funktionen geben `iter` zurück.

## <a name="canonical"></a> canonical

```cpp
path canonical(const path& pval, const path& base = current_path());
path canonical(const path& pval, error_code& ec);
path canonical(const path& pval, const path& base, error_code& ec);
```

Die Funktionen bilden einen absoluten Pfadnamen „pabs = absolute(pval, base) (oder pabs = absolute(pval) für die Überladung ohne Basisparameter), und reduzieren ihn dann in der folgenden Schrittfolge auf eine kanonische Form:

1. Jede Komponente X, für die „is_symlink(X)“ „true“ ergibt, wird durch „read_symlink(X)“ ersetzt.

1. Jede Pfadkomponente „.“ („Punkt“ ist das durch die vorherigen Pfadkomponenten angegebene Verzeichnis) wird entfernt.

1. Jedes Paar von Pfadkomponenten „X/..“ („Punkt-Punkt“ ist das durch die vorherigen Pfadkomponenten angegebene übergeordnete Verzeichnis) wird entfernt.

Die Funktion gibt dann „pabs“ zurück.

## <a name="copy"></a> copy

```cpp
void copy(const path& from, const path& to);
void copy(const path& from, const path& to, error_code& ec) noexcept;
void copy(const path& from, const path& to, copy_options opts);
void copy(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

Die Funktionen kopieren oder verknüpfen alle möglicherweise eine oder mehrere Dateien unter der Kontrolle von `opts` von `from` zu `to`, das für die Überladungen ohne `opts`-Parameter als „copy_options::none“ übernommen wird. `opts` muss mindestens eine der folgenden Optionen enthalten:

- skip_existing, overwrite_existing oder update_existing

- copy_symlinks oder skip_symlinks

- directories_only, create_symlinks oder create_hard_links

Die Funktionen bestimmen zunächst die file_status-Werte „f“ für `from` und „t“ für `to`:

- Bei „opts & (copy_options::create_symlinks &#124; copy_options::skip_symlinks)“ durch den Aufruf von „symlink_status“

- andernfalls durch den Aufruf von „status“

- andernfalls wird ein Fehler gemeldet

Bei „!exists(f) &#124;&#124; equivalent(f, t) &#124;&#124; is_other(f) &#124;&#124; is_other(t) &#124;&#124; is_directory(f)&& is_regular_file(t)“ wird dann ein Fehler gemeldet (und kein anderer Schritt ausgeführt).

Andernfalls, wenn „is_symlink(f)“ gilt:

- Bei „options & copy_options::skip_symlinks“ keinen weiteren Schritt ausführen.

- Andernfalls gilt bei „!!exists(t)&& options & copy_options::copy_symlinks“ dann „copy_symlink(from, to, opts)“.

- Andernfalls wird ein Fehler gemeldet.

Andernfalls gilt bei „is_regular_file(f)“ dann:

- Bei „opts & copy_options::directories_only“ keinen weiteren Schritt ausführen.

- Andernfalls gilt bei „opts & copy_options::create_symlinks“ dann „create_symlink(to, from)“.

- Andernfalls gilt bei „opts & copy_options::create_hard_links“ dann „create_hard_link(to, from)“.

- Andernfalls gilt bei „is_directory(f)“ dann „copy_file(from, to / from.filename(), opts)“.

- Andernfalls gilt „copy_file(from, to, opts)“.

Andernfalls gilt bei „is_directory(f) && (opts & copy_options::recursive &#124;&#124; !opts)“:

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

## <a name="opy_file"></a> copy_file

```cpp
bool copy_file(const path& from, const path& to);
bool copy_file(const path& from, const path& to, error_code& ec) noexcept;
bool copy_file(const path& from, const path& to, copy_options opts);
bool copy_file(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

Die Funktionen kopieren alle möglicherweise eine Datei unter der Kontrolle von `opts` von `from` zu `to`, das für die Überladungen ohne `opts`-Parameter als „copy_options::none“ übernommen wird. `opts` darf höchstens entweder skip_existing, overwrite_existing oder update_existing enthalten.

Bei „exists\(to\) && \!\(opts & \(copy_options::skip_existing &#124; copy_options::overwrite_existing &#124; copy_options::update_existing\)\)“ wird ein Fehler gemeldet, dass die Datei bereits vorhanden ist.

Andernfalls wird bei „\!exists\(to\) &#124;&#124; opts & copy_options::overwrite_existing &#124;&#124; opts & copy_options::update_existing&& last_write_time\(to\) \< last_write_time\(from\) &#124;&#124; \!\(opts & \(copy_options::skip_existing &#124; copy_options::overwrite_existing &#124; copy_options:update_existing\)\)“ versucht, die Inhalte und Attribute der Datei <Quelle> zur Datei <Ziel> zu kopieren. Wenn beim Kopierversuch ein Fehler auftritt, diesen dann melden.

Die Funktionen geben „true“ zurück, wenn die Kopie versucht und erfolgreich abgeschlossen wird, andernfalls wird „false“ zurückgegeben.

## <a name="copy_symlink "></a> copy_symlink

```cpp
void copy_symlink(const path& from, const path& to);
void copy_symlink(const path& from, const path& to, error_code& ec) noexcept;
```

Bei is_directory\(from\) ruft die Funktion create_directory_symlink\(from, to\) auf. Andernfalls ruft sie create_symlink\(from, to\) auf.

## <a name="create_directories"></a> create_directories

```cpp
bool create_directories(const path& pval);
bool create_directories(const path& pval, error_code& ec) noexcept;
```

Für einen Pfadnamen wie „a\/b\/c“ erstellt die Funktion bei Bedarf die Verzeichnisse „a“ und „a\/b“, damit sie bei Bedarf das Verzeichnis „a\/b\/c“ erstellen kann. Sie gibt nur TRUE zurück, wenn das Verzeichnis `pval` erstellt wird.

## <a name="create_directory"></a> create_directory

```cpp
bool create_directory(const path& pval);

bool create_directory(const path& pval, error_code& ec) noexcept;
bool create_directory(const path& pval, const path& attr);
bool create_directory(const path& pval, const path& attr, error_code& ec) noexcept;
```

Die Funktion erstellt das Verzeichnis `pval` bei Bedarf. Sie gibt nur dann TRUE zurück, wenn sie das Verzeichnis `pval` tatsächlich erstellt. In diesem Fall kopiert sie die Berechtigungen aus der vorhandenen Datei `attr` oder verwendet „perms::all“ für die Überladungen ohne `attr`-Parameter.

## <a name="create_directory_symlink "></a> create_directory_symlink

```cpp
void create_directory_symlink(const path& to, const path& link);
void create_directory_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

Die Funktion erstellt „link“ als eine symbolische Verknüpfung für das Verzeichnis `to`.

## <a name="create_hard_link"></a> create_hard_link

```cpp
void create_hard_link(const path& to,  const path& link);
void create_hard_link(const path& to, const path& link, error_code& ec) noexcept;
```

Die Funktion erstellt „link“ als festen Link für das Verzeichnis oder die Datei `to`.

## <a name="create_symlink "></a> create_symlink

```cpp
void create_symlink(const path& to,  const path& link);

void create_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

Die Funktion erstellt `link` als symbolische Verknüpfung für die Datei `to`.

## <a name="current_path"></a> current_path

```cpp
path current_path();
path current_path(error_code& ec);
void current_path(const path& pval);
void current_path(const path& pval, error_code& ec) noexcept;
```

Die Funktionen ohne den Parameter `pval` geben den Pfadnamen für das aktuelle Verzeichnis zurück. Die übrigen Funktionen legen das aktuelle Verzeichnis auf `pval` fest.

## <a name="end"></a>  end

```cpp
directory_iterator& end(const directory_iterator& iter) noexcept;
recursive_directory_iterator& end(const recursive_directory_iterator& iter) noexcept;
```

Die erste Funktion gibt directory_iterator\(\) und die zweite Funktion recursive_directory_iterator\(\) zurück.

## <a name="equivalent"></a> equivalent

```cpp
bool equivalent(const path& left, const path& right);
bool equivalent(const path& left, const path& right, error_code& ec) noexcept;
```

Die Funktionen geben nur TRUE zurück, wenn `left` und `right` dieselbe Dateisystementität festgelegt wird.

## <a name="exists"></a> exists

```cpp
bool exists(file_status stat) noexcept;
bool exists(const path& pval);
bool exists(const path& pval, error_code& ec) noexcept;
```

Die erste Funktion gibt „status_known && stat.type\(\) \!\= file_not_found“ zurück. Die zweite und dritte Funktion geben „exists\(status\(pval\)\)“ zurück.

## <a name="file_size"></a> file_size

```cpp
uintmax_t file_size(const path& pval);
uintmax_t file_size(const path& pval, error_code& ec) noexcept;
```

Die Funktionen geben die Größe der von `pval` angegebenen Datei in Bytes zurück, wenn „exists\(pval\) && is_regular_file\(pval\)“ gilt und die Dateigröße bestimmt werden kann. Andernfalls wird ein Fehler gemeldet und „uintmax_t\(\-1\)“ zurückgegeben.

## <a name="hard_link_count"></a> hard_link_count

```cpp
uintmax_t hard_link_count(const path& pval);
uintmax_t hard_link_count(const path& pval, error_code& ec) noexcept;
```

Die Funktion gibt die Anzahl der festen Links für `pval` oder \-1 zurück, wenn ein Fehler auftritt.

## <a name="hash_value"></a> hash_value

```cpp
size_t hash_value(const path& pval) noexcept;
```

Die Funktion gibt einen Hashwert für pval.native\(\) zurück.

## <a name="is_block_file"></a> is_block_file

```cpp
bool is_block_file(file_status stat) noexcept;
bool is_block_file(const path& pval);
bool is_block_file(const path& pval, error_code& ec) noexcept;
```

Die erste Funktion gibt „stat.type\(\) \=\= file_type::block“ zurück. Die übrigen Funktionen geben „is_block_file\(status\(pval\)\)“ zurück.

## <a name="is_character_file"></a> is_character_file

```cpp
bool is_character_file(file_status stat) noexcept;
bool is_character_file(const path& pval);
bool is_character_file(const path& pval, error_code& ec) noexcept;
```

Die erste Funktion gibt „stat.type\(\) \=\= file_type::character“ zurück. Die übrigen Funktionen geben „is_character_file\(status\(pval\)\)“ zurück.

## <a name="is_directory "></a> is_directory

```cpp
bool is_directory(file_status stat) noexcept;
bool is_directory(const path& pval);
bool is_directory(const path& pval, error_code& ec) noexcept;
```

Die erste Funktion gibt „stat.type\(\) \=\= file_type::directory“ zurück. Die übrigen Funktionen geben „is_directory_file\(status\(pval\)\)“ zurück.

## <a name="is_empty"></a> is_empty

```cpp
bool is_empty(file_status stat) noexcept;
bool is_empty(const path& pval);
bool is_empty(const path& pval, error_code& ec) noexcept;
```

Bei „is_directory\(pval\)“ gibt die Funktion dann „directory_iterator\(pval\) \=\= directory_iterator\(\)“ zurück. Andernfalls wird „file_size\(pval\) \=\= 0“ zurückgegeben.

## <a name="is_fifo"></a> is_fifo

```cpp
bool is_fifo(file_status stat) noexcept;
bool is_fifo(const path& pval);
bool is_fifo(const path& pval, error_code& ec) noexcept;
```

Die erste Funktion gibt „stat.type\(\) \=\= file_type::fifo“ zurück. Die übrigen Funktionen geben „is_fifo\(status\(pval\)\)“ zurück.

## <a name="is_other"></a> is_other

```cpp
bool is_other(file_status stat) noexcept;
bool is_other(const path& pval);
bool is_other(const path& pval, error_code& ec) noexcept;
```

Die erste Funktion gibt „stat.type\(\) \=\= file_type::other“ zurück. Die übrigen Funktionen geben „is_other\(status\(pval\)\)“ zurück.

## <a name="s_regular_file"></a> is_regular_file

```cpp
bool is_regular_file(file_status stat) noexcept;
bool is_regular_file(const path& pval);
bool is_regular_file(const path& pval, error_code& ec) noexcept;
```

Die erste Funktion gibt „stat.type\(\) \=\= file_type::regular“ zurück. Die übrigen Funktionen geben „is_regular_file\(status\(pval\)\)“ zurück.

## <a name="is_socket"></a> is_socket

```cpp
bool is_socket(file_status stat) noexcept;
bool is_socket(const path& pval);
bool is_socket(const path& pval, error_code& ec) noexcept;
```

Die erste Funktion gibt „stat.type\(\) \=\= file_type::socket“ zurück. Die übrigen Funktionen geben „is_socket\(status\(pval\)\)“ zurück.

## <a name="is_symlink"></a> is_symlink

```cpp
bool is_symlink(file_status stat) noexcept;
bool is_symlink(const path& pval);
bool is_symlink(const path& pval, error_code& ec) noexcept;
```

Die erste Funktion gibt „stat.type\(\) \=\= file_type::symlink“ zurück. Die übrigen Funktionen geben „is_symlink\(status\(pval\)\)“ zurück.

## <a name="last_write_time"></a> last_write_time

```cpp
file_time_type last_write_time(const path& pval);
file_time_type last_write_time(const path& pval, error_code& ec) noexcept;
void last_write_time(const path& pval, file_time_type new_time);
void last_write_time(const path& pval, file_time_type new_time, error_code& ec) noexcept;
```

Die ersten beiden Funktionen geben den Zeitpunkt der letzten Datenänderung für `pval` oder „file_time_type\(\-1\)“ zurück, wenn ein Fehler auftritt. Die letzten beiden Funktionen legen die Uhrzeit der letzten Datenänderung für `pval` auf new_time fest.

## <a name="permissions"></a> permissions

```cpp
void permissions(const path& pval, perms mask);
void permissions(const path& pval, perms mask, error_code& ec) noexcept;
```

Die Funktionen legen die Berechtigungen für den durch `pval` auf „mask & perms::mask under control of perms & \(perms::add_perms &#124; perms::remove_perms\)“ festgelegten Pfadnamen fest. „mask“ darf höchstens ein „perms::add_perms“ oder „perms::remove_perms“ enthalten.

Bei „mask & perms::add_perms“ legen die Funktionen die Berechtigungen auf „status\(pval\).permissions\(\) &#124; mask & perms::mask“ fest. Andernfalls legen die Funktionen bei „mask & perms::remove_perms“ die Berechtigungen auf „status\(pval\).permissions\(\) & ~\(mask & perms::mask\)“ fest. Andernfalls legen die Funktionen die Berechtigungen auf „mask & perms::mask“ fest.

## <a name="read_symlink"></a> read_symlink

```cpp
path read_symlink(const path& pval);
path read_symlink(const path& pval, error_code& ec);
```

Die Funktionen melden einen Fehler und geben „path()“ zurück, wenn „path\(\) if \!is_symlink\(pval\)“ gilt. Andernfalls geben die Funktionen ein Objekt vom Typ `path` zurück, das die symbolische Verknüpfung enthält.

## <a name="remove"></a> remove

```cpp
bool remove(const path& pval);
bool remove(const path& pval, error_code& ec) noexcept;
```

Die Funktionen geben nur TRUE zurück, wenn „exists\(symlink_status\(pval\)\)“ gilt und die Datei erfolgreich entfernt wurde. Die symbolische Verknüpfung selbst wird entfernt und nicht die von ihr bestimmte Datei.

## <a name="remove_all"></a> remove_all

```cpp
uintmax_t remove_all(const path& pval);
uintmax_t remove_all(const path& pval, error_code& ec) noexcept;
```

Wenn `pval` ein Verzeichnis ist, entfernen die Funktionen alle Verzeichniseinträge rekursiv und dann den Eintrag selbst. Andernfalls rufen die Funktionen „remove“ auf. Sie geben die Anzahl aller Elemente zurück, die erfolgreich entfernt wurden.

## <a name="rename"></a> rename

```cpp
void rename(const path& from,  const path& to);
void rename(const path& from,  const path& to, error_code& ec) noexcept;
```

Die Funktionen benennen `from` in `to` um. Die symbolische Verknüpfung selbst wird umbenannt und nicht die von ihr bestimmte Datei.

## <a name="resize_file"></a> resize_file

```cpp
void resize(const path& pval, uintmax_t size);
void resize(const path& pval, uintmax_t size, error_code& ec) noexcept;
```

Die Funktionen ändern die Größe der Datei so, dass „file_size\(pval\) \=\= -Größe“.

## <a name="space"></a> space

```cpp
space_info space(const path& pval);
space_info space(const path& pval, error_code& ec) noexcept;
```

Die Funktion gibt Informationen zum von `pval` bezeichneten Volume in einer Struktur vom Typ `space_info` zurück. Die Struktur enthält „uintmax_t\(\-1\)“ für jeden Wert, der nicht bestimmt werden kann.

## <a name="status"></a> status

```cpp
file_status status(const path& pval);
file_status status(const path& pval, error_code& ec) noexcept;
```

Die Funktionen geben den Status des Pfadnamens, den Dateityp und die Berechtigungen zurück, die `pval` zugeordnet sind. Die symbolische Verknüpfung selbst wird nicht getestet, dafür aber die von ihr bestimmte Datei.

## <a name="status_known"></a> status_known

```cpp
bool status_known(file_status stat) noexcept;
```

Die Funktion gibt „stat.type\(\) \!\= file_type::none“ zurück.

## <a name="swap"></a>  swap

```cpp
void swap(path& left, path& right) noexcept;
```

Die Funktion vertauscht die Inhalte von `left` und `right`.

## <a name="symlink_status"></a> symlink_status

```cpp
file_status symlink_status(const path& pval);
file_status symlink_status(const path& pval, erroxr_code& ec) noexcept;
```

Die Funktionen geben den Status des Pfadnamens der symbolischen Verknüpfung, den Dateityp und die Berechtigungen zurück, die `pval` zugeordnet sind. Die Funktionen verhalten sich wie „status\(pval\)“, mit der Ausnahme, dass die symbolische Verknüpfung selbst getestet wird und nicht die von ihr bezeichnete Datei.

## <a name="system_complete"></a> system_complete

```cpp
path system_complete(const path& pval);
path system_complete(const path& pval, error_code& ec);
```

Die Funktionen geben einen absoluten Pfadnamen zurück, der bei Bedarf das aktuelle Verzeichnis berücksichtigt, das seinem Stammnamen zugeordnet ist. \(Für POSIX geben die Funktionen „absolute\(pval\)“ zurück.\)

## <a name="temp_directory_path"></a> temp_directory_path

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

Die erste Funktion verhält sich wie „path(source)“ und die zweite Funktion verhält sich wie „path(first, last)“ mit der Ausnahme, dass die angegebene Quelle in beiden Fällen als Sequenz von „char“-Elementen übernommen wird, die unabhängig vom Dateisystem als UTF-8 codiert ist.


