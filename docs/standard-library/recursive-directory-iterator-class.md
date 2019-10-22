---
title: recursive_directory_iterator-Klasse
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
ms.openlocfilehash: a5200c030986ebbcfccb1eba2963e8317c879eb6
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72686802"
---
# <a name="recursive_directory_iterator-class"></a>recursive_directory_iterator-Klasse

Beschreibt einen eingabeiterator, der die Dateinamen in einem Verzeichnis durchläuft und möglicherweise rekursiv in Unterverzeichnisse absteigend ist. Bei einem Iterator-`X` `*X` der Ausdruck zu einem Objekt der Klasse `directory_entry` ausgewertet, das den Dateinamen umschließt, und alles, was über den Status bekannt ist.

Weitere Informationen und Codebeispiele finden Sie unter [File System Navigation (C++) (Dateisystemnavigation (C++))](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Syntax

```cpp
class recursive_directory_iterator;
```

## <a name="remarks"></a>Hinweise

Die Klassen Vorlage speichert Folgendes:

1. ein Objekt vom Typ "`stack<pair<directory_iterator, path>>`", das hier zur Veranschaulichung `mystack` aufgerufen wird, das den Schachteln der Verzeichnisse darstellt, die sequenziert werden sollen.

1. ein Objekt vom Typ `directory_entry` hier `myentry` aufgerufen, das den aktuellen Dateinamen in der Verzeichnis Sequenz darstellt.

1. ein Objekt vom Typ **bool**, das hier `no_push` aufgerufen wird, das aufzeichnet, ob der rekursive Abstieg in die Unterverzeichnisse deaktiviert ist.

1. ein Objekt vom Typ "`directory_options`", das hier `myoptions` aufgerufen wird, das die bei der Konstruktion eingerichteten Optionen aufzeichnet.

Ein konstruiertes Standard Objekt vom Typ `recursive_directory_entry` weist einen Sequenz Ende-Iterator bei `mystack.top().first` auf und stellt den Sequenz Ende-Iterator dar. Wenn beispielsweise das Verzeichnis `abc` mit Einträgen `def` (ein Verzeichnis), `def/ghi` und `jkl` ist, lautet der folgende Code:

```cpp
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)
    visit(next->path());
```

Ruft "Visit" mit den Argumenten `path("abc/def/ghi")` und `path("abc/jkl")` auf. Sie können die Sequenzierung über eine Verzeichnis Unterstruktur auf zwei Arten qualifizieren:

1. Ein Verzeichnis Symlink wird nur gescannt, wenn Sie eine `recursive_directory_iterator` mit einem `directory_options`-Argument erstellen, dessen Wert `directory_options::follow_directory_symlink` ist.

1. Wenn Sie `disable_recursion_pending` aufgerufen wird, wird ein nachfolgendes Verzeichnis, das während eines Inkrements aufgetreten ist, nicht rekursiv gescannt.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[recursive_directory_iterator](#recursive_directory_iterator)|Erstellt ein Objekt vom Typ `recursive_directory_iterator`.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[Eingeh](#depth)|Gibt `mystack.size() - 1` zurück, sodass `pval` die Tiefe 0 (null) aufweist.|
|[disable_recursion_pending](#disable_recursion_pending)|Speichert **true** in `no_push`.|
|[Inkrement](#increment)|Wechselt zum nächsten Dateinamen in der Sequenz.|
|[options](#options)|Gibt `myoptions`zurück.|
|[pop](#pop)|Gibt das nächste-Objekt zurück.|
|[recursion_pending](#recursion_pending)|Gibt `!no_push`zurück.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[Operator!=](#op_neq)|Gibt `!(*this == right)`zurück.|
|[operator=](#op_as)|Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.|
|[operator==](#op_eq)|Gibt nur **dann true** zurück, wenn sowohl `*this` als auch *right* Sequenz Ende-Iteratoren sind oder beide keine Sequenz Ende-Iteratoren sind.|
|[operator*](#op_multiply)|Gibt `myentry`zurück.|
|[operator->](#op_cast)|Gibt `&**this`zurück.|
|[operator++](#op_increment)|Inkremente der `recursive_directory_iterator`.|

## <a name="requirements"></a>Anforderungen

**Header:** \<filesystem >

**Namespace:** std::tr2::sys

## <a name="depth"></a>recursive_directory_iterator::d epth

Gibt `mystack.size() - 1` zurück, sodass `pval` die Tiefe 0 (null) aufweist.

```cpp
int depth() const;
```

## <a name="disable_recursion_pending"></a>recursive_directory_iterator::d isable_recursion_pending

Speichert **true** in `no_push`.

```cpp
void disable_recursion_pending();
```

## <a name="increment"></a>recursive_directory_iterator:: Increment

Wechselt zum nächsten Dateinamen in der Sequenz.

```cpp
recursive_directory_iterator& increment(error_code& ec) noexcept;
```

### <a name="parameters"></a>Parameter

*EC* -\
Der angegebene Fehlercode.

### <a name="remarks"></a>Hinweise

Die Funktion versucht, zum nächsten Dateinamen in der geschachtelten Sequenz zu gelangen. Wenn erfolgreich, speichert Sie diesen Dateinamen in `myentry`; Andernfalls erzeugt Sie einen Sequenz Ende-Iterator.

## <a name="op_neq"></a>recursive_directory_iterator:: Operator! =

Gibt `!(*this == right)`zurück.

```cpp
bool operator!=(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>Parameter

*Rechte* \
Der [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) für den Vergleich.

## <a name="op_as"></a>recursive_directory_iterator:: Operator =

Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.

```cpp
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Parameter

*recursive_directory_iterator* \
Der [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) , der in die `recursive_directory_iterator` kopiert wird.

## <a name="op_eq"></a>recursive_directory_iterator:: Operator = =

Gibt nur **dann true** zurück, wenn sowohl `*this` als auch *right* Sequenz Ende-Iteratoren sind oder beide keine Sequenz Ende-Iteratoren sind.

```cpp
bool operator==(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>Parameter

*Rechte* \
Der [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) für den Vergleich.

## <a name="op_multiply"></a>recursive_directory_iterator:: Operator *

Gibt `myentry`zurück.

```cpp
const directory_entry& operator*() const;
```

## <a name="op_cast"></a>recursive_directory_iterator:: Operator->

Gibt `&**this`zurück.

```cpp
const directory_entry * operator->() const;
```

## <a name="op_increment"></a>recursive_directory_iterator:: Operator + +

Inkremente der `recursive_directory_iterator`.

```cpp
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```

### <a name="parameters"></a>Parameter

*int* -\
Das angegebene Inkrement.

### <a name="remarks"></a>Hinweise

Die erste Member-Funktion ruft `increment()` auf und gibt dann `*this` zurück. Die zweite Member-Funktion erstellt eine Kopie des-Objekts, ruft `increment()` auf und gibt dann die Kopie zurück.

## <a name="options"></a>recursive_directory_iterator:: Options

Gibt `myoptions`zurück.

```cpp
directory_options options() const;
```

## <a name="pop"></a>recursive_directory_iterator::p op

Gibt das nächste-Objekt zurück.

```cpp
void pop();
```

### <a name="remarks"></a>Hinweise

Wenn `depth() == 0`, wird das-Objekt zu einem Sequenz Ende-Iterator. Andernfalls beendet die Memberfunktion das Durchsuchen des aktuellen (tiefsten) Verzeichnisses und setzt das Durchsuchen auf der nächstniedrigeren Tiefe fort.

## <a name="recursion_pending"></a>recursive_directory_iterator::recursion_pending

Gibt `!no_push`zurück.

```cpp
bool recursion_pending() const;
```

## <a name="recursive_directory_iterator"></a>recursive_directory_iterator::recursive_directory_iterator

Erstellt ein Objekt vom Typ `recursive_directory_iterator`.

```cpp
recursive_directory_iterator() noexcept;
explicit recursive_directory_iterator(const path& pval);

recursive_directory_iterator(const path& pval,
    error_code& ec) noexcept;
recursive_directory_iterator(const path& pval,
    directory_options opts);

recursive_directory_iterator(const path& pval,
    directory_options opts,
    error_code& ec) noexcept;
recursive_directory_iterator(const recursive_directory_iterator&) = default;
recursive_directory_iterator(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Parameter

*PVal* -\
Der angegebene Pfad.

*error_code* \
Der angegebene Fehlercode.

*OPTS* \
Die angegebenen Verzeichnis Optionen.

*recursive_directory_iterator* \
Das `recursive_directory_iterator`-Element, von dem das erstellte `recursive_directory_iterator`-Element eine Kopie sein soll.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor erzeugt einen Sequenzende-Iterator. Der zweite und dritte Konstruktoren speichern **false** in `no_push` und `directory_options::none` in `myoptions`. Anschließend wird versucht, *PVal* als Verzeichnis zu öffnen und zu lesen. Bei erfolgreicher Initialisierung initialisieren Sie `mystack` und `myentry`, um den ersten nicht-Verzeichnis Dateinamen in der geschachtelte-Sequenz festzulegen. Andernfalls wird ein Sequenz Ende-Iterator erzeugt.

Der vierte und fünfte Konstruktoren Verhalten sich identisch mit dem zweiten und dritten, mit dem Unterschied, dass Sie zuerst *OPTS* in `myoptions` speichern. Die als Standard festgelegten Konstruktoren verhalten sich wie erwartet.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem>](../standard-library/filesystem.md)\
[Dateisystemnavigation (C++)](../standard-library/file-system-navigation.md)
