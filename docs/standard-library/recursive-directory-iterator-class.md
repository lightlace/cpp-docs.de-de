---
title: recursive_directory_iterator-Klasse
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
ms.openlocfilehash: 98eaf2494a3bc17c0f9d11683fc67fed433ba3a5
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451711"
---
# <a name="recursivedirectoryiterator-class"></a>recursive_directory_iterator-Klasse

Beschreibt einen eingabeiterator, der die Dateinamen in einem Verzeichnis durchläuft und möglicherweise rekursiv in Unterverzeichnisse absteigend ist. Bei einem Iterator `X`wertet der Ausdruck `*X` zu einem Objekt der Klasse `directory_entry` aus, das den Dateinamen umschließt, und alles, was über den Status bekannt ist.

Weitere Informationen und Codebeispiele finden Sie unter [Dateisystemnavigation (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Syntax

```cpp
class recursive_directory_iterator;
```

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse speichert Folgendes:

1. ein Objekt vom Typ `stack<pair<directory_iterator, path>>`, das `mystack` hier zum Zweck der Darstellung aufgerufen wird, das den Schachteln der Verzeichnisse darstellt, die sequenziert werden sollen.

1. ein Objekt vom Typ `directory_entry` , `myentry` das hier aufgerufen wird, das den aktuellen Dateinamen in der Verzeichnis Sequenz darstellt.

1. ein Objekt vom Typ **bool**, das `no_push` hier aufgerufen wird, das aufzeichnet, ob der rekursive Abstieg in die Unterverzeichnisse deaktiviert ist.

1. ein Objekt vom Typ `directory_options`, das `myoptions` hier aufgerufen wird und die bei der Konstruktion festgelegte Optionen aufzeichnet.

Ein konstruiertes Standard Objekt vom `recursive_directory_entry` Typ verfügt über einen Sequenz Ende-Iterator bei `mystack.top().first` und stellt den Sequenz Ende-Iterator dar. Wenn das Verzeichnis `abc` z. b. Einträge `def` (ein Verzeichnis), `def/ghi`und `jkl`ist, lautet der folgende Code:

```cpp
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)
    visit(next->path());
```

Ruft "Visit" mit den `path("abc/def/ghi")` Argumenten `path("abc/jkl")`und auf. Sie können die Sequenzierung über eine Verzeichnis Unterstruktur auf zwei Arten qualifizieren:

1. Ein Verzeichnis Symlink wird nur überprüft, wenn Sie einen `recursive_directory_iterator` mit einem `directory_options` -Argument erstellen, dessen `directory_options::follow_directory_symlink`Wert ist.

1. Wenn Sie anrufen `disable_recursion_pending` , wird ein nachfolgendes Verzeichnis, das während eines Inkrements gefunden wurde, nicht rekursiv gescannt.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[recursive_directory_iterator](#recursive_directory_iterator)|Erstellt ein Objekt vom Typ `recursive_directory_iterator`.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[Eingeh](#depth)|Gibt `mystack.size() - 1`zurück, `pval` und ist daher in Tiefe Null.|
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
|[operator==](#op_eq)|Gibt nur **dann true** zurück `*this` , wenn sowohl als auch *right* Sequenz Ende-Iteratoren sind oder beide keine Sequenz Ende-Iteratoren sind.|
|[operator*](#op_multiply)|Gibt `myentry`zurück.|
|[operator->](#op_cast)|Gibt `&**this`zurück.|
|[operator++](#op_increment)|Inkremente `recursive_directory_iterator`.|

## <a name="requirements"></a>Anforderungen

**Header:** \<Dateisystem >

**Namespace:** std::tr2::sys

## <a name="depth"></a>recursive_directory_iterator::d epth

Gibt `mystack.size() - 1`zurück, `pval` und ist daher in Tiefe Null.

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

*EC*\
Der angegebene Fehlercode.

### <a name="remarks"></a>Hinweise

Die Funktion versucht, zum nächsten Dateinamen in der geschachtelten Sequenz zu gelangen. Bei erfolgreicher Ausführung speichert Sie diesen Dateinamen `myentry`in; andernfalls erzeugt Sie einen Sequenz Ende-Iterator.

## <a name="op_neq"></a>recursive_directory_iterator:: Operator! =

Gibt `!(*this == right)`zurück.

```cpp
bool operator!=(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>Parameter

*Richting*\
Der [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) für den Vergleich.

## <a name="op_as"></a>recursive_directory_iterator:: Operator =

Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.

```cpp
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Parameter

*recursive_directory_iterator*\
Das [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) , das in das `recursive_directory_iterator`kopiert wird.

## <a name="op_eq"></a>recursive_directory_iterator:: Operator = =

Gibt nur **dann true** zurück `*this` , wenn sowohl als auch *right* Sequenz Ende-Iteratoren sind oder beide keine Sequenz Ende-Iteratoren sind.

```cpp
bool operator==(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>Parameter

*Richting*\
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

Inkremente `recursive_directory_iterator`.

```cpp
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```

### <a name="parameters"></a>Parameter

*wartenden*\
Das angegebene Inkrement.

### <a name="remarks"></a>Hinweise

Die erste Member-Funktion `increment()`Ruft auf und `*this`gibt dann zurück. Die zweite Member-Funktion erstellt eine Kopie des-Objekts, `increment()`Ruft auf und gibt dann die Kopie zurück.

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

, `depth() == 0` Wenn das Objekt ein Sequenz Ende-Iterator wird. Andernfalls beendet die Memberfunktion das Durchsuchen des aktuellen (tiefsten) Verzeichnisses und setzt das Durchsuchen auf der nächstniedrigeren Tiefe fort.

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

*PVAL*\
Der angegebene Pfad.

*error_code*\
Der angegebene Fehlercode.

*OPTS*\
Die angegebenen Verzeichnis Optionen.

*recursive_directory_iterator*\
Das `recursive_directory_iterator`-Element, von dem das erstellte `recursive_directory_iterator`-Element eine Kopie sein soll.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor erzeugt einen Sequenzende-Iterator. Mit dem zweiten und dritten Konstruktoren  wird in `no_push` und `directory_options::none` in `myoptions`false gespeichert. Anschließend wird versucht, *PVal* als Verzeichnis zu öffnen und zu lesen. Bei erfolgreicher Initialisierung initialisieren `mystack` und `myentry` , um den ersten nicht-Verzeichnis Dateinamen in der geschachtelte Sequence-Sequenz festzulegen. andernfalls wird ein Sequenz Ende-Iterator erzeugt.

Der vierte und fünfte Konstruktoren Verhalten sich identisch mit dem zweiten und dritten, mit dem Unterschied, dass Sie zuerst `myoptions` *OPTS* in speichern. Die als Standard festgelegten Konstruktoren verhalten sich wie erwartet.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem>](../standard-library/filesystem.md)\
[Dateisystemnavigation (C++)](../standard-library/file-system-navigation.md)
