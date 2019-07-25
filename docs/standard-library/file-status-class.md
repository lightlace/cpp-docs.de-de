---
title: file_status-Klasse
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::file_status
- filesystem/std::experimental::filesystem::file_status::operator=
- filesystem/std::experimental::filesystem::file_status::type
- filesystem/std::experimental::filesystem::file_status::permissions
ms.assetid: 9781840e-ad22-44dd-ad79-0fabaa94bac4
helpviewer_keywords:
- std::experimental::filesystem::file_status
- std::experimental::filesystem::file_status::operator=
- std::experimental::filesystem::file_status::type
- std::experimental::filesystem::file_status::permissions
ms.openlocfilehash: 60ced1f60c811f585928f47c6cfd5e695d0c4085
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457751"
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
|[file_status](#file_status)|Erstellt einen Wrapper für [file_type](../standard-library/filesystem-enumerations.md#file_type) und Datei- [perms](../standard-library/filesystem-enumerations.md#perms).|

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

**Header:** \<Dateisystem >

**Namespace:** Std:: experimental:: File System, Std:: experimental:: File System

## <a name="file_status"></a>file_status::file_status

Erstellt einen Wrapper für [file_type](../standard-library/filesystem-enumerations.md#file_type) und Datei- [perms](../standard-library/filesystem-enumerations.md#perms).

```cpp
explicit file_status(
   file_type ftype = file_type::none,
   perms mask = perms::unknown) noexcept;

file_status(const file_status&) noexcept = default;

file_status(file_status&&) noexcept = default;

~file_status() noexcept = default;
```

### <a name="parameters"></a>Parameter

*FTYPE*\
Angegeben `file_type`, der `file_type::none`Standardwert ist.

*chel*\
Angegebene Datei `perms` `perms::unknown`. der Standardwert ist.

*file_status*\
Das gespeicherte-Objekt.

## <a name="op_as"></a>file_status:: Operator =

Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.

```cpp
file_status& operator=(const file_status&) noexcept = default;
file_status& operator=(file_status&&) nexcept = default;
```

### <a name="parameters"></a>Parameter

*file_status*\
Das [file_status](../standard-library/file-status-class.md) , das in das `file_status`kopiert wird.

## <a name="type"></a>Sorte

Ruft den `file_type` ab oder legt diesen fest.

```cpp
file_type type() const noexcept
void type(file_type ftype) noexcept
```

### <a name="parameters"></a>Parameter

*FTYPE*\
Angabe `file_type`.

## <a name="permissions"></a>Griff

Ruft die Dateiberechtigungen ab oder legt sie fest.

Verwenden Sie den Setter, um eine `readonly` Datei zu erstellen `readonly` oder das Attribut zu entfernen.

```cpp
perms permissions() const noexcept
void permissions(perms mask) noexcept
```

### <a name="parameters"></a>Parameter

*chel*\
Angabe `perms`.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Path-Klasse](../standard-library/path-class.md)\
[\<filesystem>](../standard-library/filesystem.md)
