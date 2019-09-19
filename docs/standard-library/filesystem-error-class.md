---
title: filesystem_error-Klasse
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::filesystem_error
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
ms.openlocfilehash: 7bd6b2d3d716ba25999388d44e7bd5a8d0750eb5
ms.sourcegitcommit: 76cc69b482ada8ebf0837e8cdfd4459661f996dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71127198"
---
# <a name="filesystem_error-class"></a>filesystem_error-Klasse

Eine Basisklasse für alle Ausnahmen, die ausgelöst werden, um einen Systemüberlauf auf niedriger Ebene zu melden.

## <a name="syntax"></a>Syntax

```cpp
class filesystem_error    : public system_error;
```

## <a name="remarks"></a>Hinweise

Die Klasse fungiert als Basisklasse für alle Ausnahmen, die ausgelöst werden, um einen Fehler in \<filesystem>-Funktionen zu melden. Sie speichert ein Objekt vom Typ `string`, das `mymesg` hier zur Veranschaulichung aufgerufen wird. Außerdem werden zwei Objekte vom Typ `path`gespeichert, die als und `mypval2`bezeichnet `mypval1` werden.

## <a name="members"></a>Member

### <a name="constructors"></a>Konstruktoren

|||
|-|-|
|[filesystem_error](#filesystem_error)|Erstellt eine `filesystem_error` Meldung.|

### <a name="functions"></a>Funktionen

|||
|-|-|
|[path1](#path1)|Gibt `mypval1` zurück.|
|[path2](#path2)|Gibt `mypval2` zurück.|
|[worüber](#what)|Gibt einen Zeiger auf ein `NTBS` zurück.|

## <a name="requirements"></a>Anforderungen

**Header:** \<Dateisystem >

**Namespace:** std::experimental::filesystem

## <a name="filesystem_error"></a>filesystem_error

Der erste Konstruktor erstellt seine Nachricht aus *what_arg* und *EC*. Der zweite Konstruktor erstellt auch seine Nachricht aus *"pval1"* , die in `mypval1`gespeichert wird. Der dritte Konstruktor erstellt seine Nachricht auch aus *"pval1"* , die er in `mypval1`speichert, und aus *"pval2"* , die er in `mypval2`speichert.

```cpp
filesystem_error(const string& what_arg,
    error_code ec);

filesystem_error(const string& what_arg,
    const path& pval1,
    error_code ec);

filesystem_error(const string& what_arg,
    const path& pval1,
    const path& pval2,
    error_code ec);
```

### <a name="parameters"></a>Parameter

*what_arg*\
Angegebene Meldung.

*EC*\
Der angegebene Fehlercode.

*"mypval1"* \
Weiterer angegebener Nachrichten Parameter.

*"mypval2"* \
Weiterer angegebener Nachrichten Parameter.

## <a name="path1"></a>path1

Die Memberfunktion gibt `mypval1` zurück.

```cpp
const path& path1() const noexcept;
```

## <a name="path2"></a>path2

Die Memberfunktion gibt `mypval2` zurück.

```cpp
const path& path2() const noexcept;
```

## <a name="what"></a>worüber

Die Member-Funktion gibt einen Zeiger auf `NTBS`einen zurück, der `runtime_error::what()`Vorzugs `system_error::what()`Weise `mymesg`aus `mypval1.native_string()`,, `mypval2.native_string()`, und besteht.

```cpp
const char *what() const noexcept;
```
