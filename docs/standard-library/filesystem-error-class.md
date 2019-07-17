---
title: filesystem_error-Klasse
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::filesystem_error
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
ms.openlocfilehash: c3dbfc080f0a1494950016f42189d932be05b0f1
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240742"
---
# <a name="filesystemerror-class"></a>filesystem_error-Klasse

Eine Basisklasse für alle Ausnahmen, die ausgelöst werden, um einen Systemüberlauf auf niedriger Ebene zu melden.

## <a name="syntax"></a>Syntax

```cpp
class filesystem_error    : public system_error;
```

## <a name="remarks"></a>Hinweise

Die Klasse fungiert als Basisklasse für alle Ausnahmen, die ausgelöst werden, um einen Fehler in \<filesystem>-Funktionen zu melden. Sie speichert ein Objekt des Typs `string`namens `mymesg` hier, um den Zweck der Darstellung. Es speichert zudem zwei Objekte des Typs `path`namens `mypval1` und `mypval2`.

## <a name="members"></a>Member

### <a name="constructors"></a>Konstruktoren

|||
|-|-|
|[filesystem_error](#filesystem_error)|Erstellt eine `filesystem_error` Nachricht.|

### <a name="functions"></a>Funktionen

|||
|-|-|
|[path1](#path1)|Gibt `mypval1` zurück.|
|[path2](#path2)|Gibt `mypval2` zurück.|
|[Was](#what)|Gibt einen Zeiger auf ein `NTBS` zurück.|

## <a name="requirements"></a>Anforderungen

**Header:** \<Filesystem >

**Namespace:** std::experimental::filesystem

## <a name="filesystem_error"></a> filesystem_error

Der erste Konstruktor erstellt die Meldung aus *"what_arg"* und *Ec*. Der zweite Konstruktor erstellt auch die Meldung aus *"pval1"* , die in gespeichert `mypval1`. Der dritte Konstruktor erstellt auch die Meldung aus *"pval1"* , die in gespeichert `mypval1`, und von *pval2*, die in gespeichert `mypval2`.

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

*"what_arg"* \
Angegebene Nachricht.

*EC*\
Angegebene Fehlercode.

*"mypval1"* \
Weitere angegebenen Meldungsparameter.

*"mypval2"* \
Weitere Nachricht der angegebenen Parameter.

## <a name="path1"></a> path1

Die Memberfunktion gibt `mypval1` zurück.

```cpp
const path& path1() const noexcept;
```

## <a name="path2"></a> path2

Die Memberfunktion gibt `mypval2` zurück.

```cpp
const path& path2() const noexcept;
```

## <a name="what"></a> Was

Die Memberfunktion gibt einen Zeiger auf ein `NTBS`vorzugsweise aus besteht aus `runtime_error::what()`, `system_error::what()`, `mymesg`, `mypval1.native_string()`, und `mypval2.native_string()`.

```cpp
const char *what() const noexcept;
```
