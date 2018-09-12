---
title: file_status-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::file_status
- filesystem/std::experimental::filesystem::file_status::operator=
- filesystem/std::experimental::filesystem::file_status::type
- filesystem/std::experimental::filesystem::file_status::permissions
dev_langs:
- C++
ms.assetid: 9781840e-ad22-44dd-ad79-0fabaa94bac4
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::experimental::filesystem::file_status
- std::experimental::filesystem::file_status::operator=
- std::experimental::filesystem::file_status::type
- std::experimental::filesystem::file_status::permissions
ms.workload:
- cplusplus
ms.openlocfilehash: cc45e785b6a3aeefd9e2cf5d0539b5d387af7143
ms.sourcegitcommit: fb9448eb96c6351a77df04af16ec5c0fb9457d9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2018
ms.locfileid: "44691665"
---
# <a name="filestatus-class"></a>file_status-Klasse

Umschließt [file_type](../standard-library/filesystem-enumerations.md#file_type) und Datei-[perms](../standard-library/filesystem-enumerations.md#perms)

## <a name="syntax"></a>Syntax

```cpp
class file_status;
```

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[file_status](#file_status)|Konstruiert einen Wrapper für [File_type](../standard-library/filesystem-enumerations.md#file_type) und [Perms](../standard-library/filesystem-enumerations.md#perms).|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[Typ](#type)|Ruft den `file_type` ab oder legt diesen fest.|
|[permissions](#permissions)|Ruft die Dateiberechtigungen ab oder legt sie fest.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator=](#op_as)|Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.|

## <a name="requirements"></a>Anforderungen

**Header:** \<Filesystem >

**Namespace:** Std::experimental::filesystem, Std::experimental::filesystem

## <a name="file_status"></a> file_status:: file_status

Konstruiert einen Wrapper für [File_type](../standard-library/filesystem-enumerations.md#file_type) und [Perms](../standard-library/filesystem-enumerations.md#perms).

```cpp
explicit file_status(
   file_type ftype = file_type::none,
   perms mask = perms::unknown) noexcept;

file_status(const file_status&) noexcept = default;

file_status(file_status&&) noexcept = default;

~file_status() noexcept = default;
```

### <a name="parameters"></a>Parameter

*ftype*<br/>
Angegebene `file_type`, standardmäßig `file_type::none`.

*Maske*<br/>
Angegebene Datei `perms`, standardmäßig `perms::unknown`.

*file_status*<br/>
Das gespeicherte Objekt.

## <a name="op_as"></a> file_status::Operator =

Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.

```cpp
file_status& operator=(const file_status&) noexcept = default;
file_status& operator=(file_status&&) nexcept = default;
```

### <a name="parameters"></a>Parameter

*file_status*<br/>
Die [File_status](../standard-library/file-status-class.md) kopiert wird, in der `file_status`.

## <a name="type"></a> Typ

Ruft den `file_type` ab oder legt diesen fest.

```cpp
file_type type() const noexcept
void type(file_type ftype) noexcept
```

### <a name="parameters"></a>Parameter

*ftype*<br/>
Angabe `file_type`.

## <a name="permissions"></a> Berechtigungen

Ruft die Dateiberechtigungen ab oder legt sie fest.

Verwenden Sie den Setter, stellen eine Datei `readonly` oder entfernen Sie die `readonly` Attribut.

```cpp
perms permissions() const noexcept
void permissions(perms mask) noexcept
```

### <a name="parameters"></a>Parameter

*Maske*<br/>
Angabe `perms`.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[path-Klasse](../standard-library/path-class.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
