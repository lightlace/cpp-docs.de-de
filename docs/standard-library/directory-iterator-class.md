---
title: directory_iterator-Klasse.
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::directory_iterator
- filesystem/std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::increment
- filesystem/std::experimental::filesystem::directory_iterator::operator=
- filesystem/std::experimental::filesystem::directory_iterator::operator==
- filesystem/std::experimental::filesystem::directory_iterator::operator!=
- filesystem/std::experimental::filesystem::directory_iterator::operator*
- filesystem/std::experimental::filesystem::directory_iterator::operator-&gt;
- filesystem/std::experimental::filesystem::directory_iterator::operator++
ms.assetid: dca2ecf8-3e69-4644-a83d-705061e10cc8
helpviewer_keywords:
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::directory_iterator::directory_iterator
- std::experimental::filesystem::directory_iterator::increment
- std::experimental::filesystem::directory_iterator::operator=
- std::experimental::filesystem::directory_iterator::operator==
- std::experimental::filesystem::directory_iterator::operator!=
- std::experimental::filesystem::directory_iterator::operator*
- std::experimental::filesystem::directory_iterator::operator-&gt;
- std::experimental::filesystem::directory_iterator::operator++
ms.openlocfilehash: 8c6dcce3de32c7e25d2489cb508454dff500a1a6
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454424"
---
# <a name="directoryiterator-class"></a>directory_iterator-Klasse.

Beschreibt einen Eingabeiterator, der alle Dateinamen in einem Verzeichnis durchläuft. Bei einem Iterator `X`wertet der Ausdruck `*X` zu einem Objekt der Klasse `directory_entry` aus, das den Dateinamen umschließt, und alles, was über den Status bekannt ist.

Die Klasse speichert ein Objekt vom Typ `path`, das `mydir` hier zur Veranschaulichung aufgerufen wird, das den Namen des Verzeichnisses darstellt, das sequenziert werden soll, und ein Objekt des `directory_entry` Typs `myentry` , das hier aufgerufen wird, das den aktuellen darstellt. Dateiname in der Verzeichnis Sequenz. Ein konstruiertes Standard Objekt vom `directory_entry` Typ weist einen `mydir` leeren Pfadnamen auf und stellt den Sequenz Ende-Iterator dar.

Wenn z. b. das `abc` Verzeichnis mit `def` Einträgen `ghi`und ist, lautet der folgende Code:

`for (directory_iterator next(path("abc")), end; next != end; ++next)     visit(next->path());`

Ruft `visit` mit den Argumenten `path("abc/def")` und `path("abc/ghi")`auf.

Weitere Informationen und Codebeispiele finden Sie unter [Dateisystemnavigation (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Syntax

```cpp
class directory_iterator;
```

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[directory_iterator](#directory_iterator)|Erstellt einen eingabeiterator, der die Dateinamen in einem Verzeichnis durchläuft.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[Inkrement](#increment)|Versucht, mit dem nächsten Dateinamen im Verzeichnis fortzufahren.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[Operator!=](#op_neq)|Gibt `!(*this == right)`zurück.|
|[operator=](#op_as)|Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.|
|[operator==](#op_eq)|Gibt nur **dann true** zurück `*this` , wenn sowohl als auch *right* Sequenz Ende-Iteratoren sind oder beide keine Sequenz Ende-Iteratoren sind.|
|[operator*](#op_star)|Gibt `myentry`zurück.|
|[operator->](#op_cast)|Gibt `&**this`zurück.|
|[operator++](#op_increment)|Ruft `increment()`auf, gibt `*this`dann zurück oder erstellt eine Kopie des-Objekts, `increment()`Ruft auf und gibt dann die Kopie zurück.|

## <a name="requirements"></a>Anforderungen

**Header:** \<experimental/filesystem>

**Namespace:** std::experimental::filesystem

## <a name="directory_iterator"></a>directory_iterator::d irectory_iterator

Der erste Konstruktor erzeugt einen Sequenzende-Iterator. Mit dem zweiten und dritten Konstruktoren wird *PVal* in `mydir`gespeichert. Anschließend wird versucht, `mydir` das Verzeichnis zu öffnen und als Verzeichnis zu lesen. Bei erfolgreicher Ausführung speichern Sie den ersten Dateinamen im Verzeichnis in `myentry`; andernfalls wird ein Sequenz Ende-Iterator erzeugt.

Die als Standard festgelegten Konstruktoren verhalten sich wie erwartet.

```cpp
directory_iterator() noexcept;
explicit directory_iterator(const path& pval);

directory_iterator(const path& pval, error_code& ec) noexcept;
directory_iterator(const directory_iterator&) = default;
directory_iterator(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Parameter

*PVAL*\
Der gespeicherte Dateiname-Pfad.

*EC*\
Der Status Fehlercode.

*directory_iterator*\
Das gespeicherte-Objekt.

## <a name="increment"></a>directory_iterator:: Increment

Die Funktion versucht, zum nächsten Dateinamen im Verzeichnis zu gelangen. Bei erfolgreicher Ausführung speichert Sie diesen Dateinamen `myentry`in; andernfalls erzeugt Sie einen Sequenz Ende-Iterator.

```cpp
directory_iterator& increment(error_code& ec) noexcept;
```

## <a name="op_neq"></a>directory_iterator:: Operator! =

Der Memberoperator gibt `!(*this == right)`zurück.

```cpp
bool operator!=(const directory_iterator& right) const;
```

### <a name="parameters"></a>Parameter

*Richting*\
Der [directory_iterator](../standard-library/directory-iterator-class.md) , der mit dem `directory_iterator`verglichen wird.

## <a name="op_as"></a>directory_iterator:: Operator =

Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.

```cpp
directory_iterator& operator=(const directory_iterator&) = default;
directory_iterator& operator=(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Parameter

*Richting*\
Das [directory_iterator](../standard-library/directory-iterator-class.md) , das in das `directory_iterator`kopiert wird.

## <a name="op_eq"></a>directory_iterator:: Operator = =

Der Member-Operator gibt nur **dann true** zurück, wenn sowohl `*this` als auch *right* Sequenz Ende-Iteratoren sind oder beide keine Sequenz Ende-Iteratoren sind.

```cpp
bool operator==(const directory_iterator& right) const;
```

### <a name="parameters"></a>Parameter

*Richting*\
Der [directory_iterator](../standard-library/directory-iterator-class.md) , der mit dem `directory_iterator`verglichen wird.

## <a name="op_star"></a>directory_iterator:: Operator *

Der Memberoperator gibt `myentry`zurück.

```cpp
const directory_entry& operator*() const;
```

## <a name="op_cast"></a>directory_iterator:: Operator->

Die Memberfunktion gibt `&**this`zurück.

```cpp
const directory_entry * operator->() const;
```

## <a name="op_increment"></a>directory_iterator:: Operator + +

Die erste Member-Funktion `increment()`Ruft auf und `*this`gibt dann zurück. Die zweite Member-Funktion erstellt eine Kopie des-Objekts, `increment()`Ruft auf und gibt dann die Kopie zurück.

```cpp
directory_iterator& operator++();
directory_iterator& operator++(int);
```

### <a name="parameters"></a>Parameter

*wartenden*\
Die Anzahl der Inkremente.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem>](../standard-library/filesystem.md)\
[Dateisystemnavigation (C++)](../standard-library/file-system-navigation.md)
