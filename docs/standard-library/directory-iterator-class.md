---
title: directory_iterator-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: dca2ecf8-3e69-4644-a83d-705061e10cc8
author: corob-msft
ms.author: corob
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
ms.workload:
- cplusplus
ms.openlocfilehash: dd5fedb8869533755546089bdee903403f30dcea
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726374"
---
# <a name="directoryiterator-class"></a>directory_iterator-Klasse.

Beschreibt einen Eingabeiterator, der alle Dateinamen in einem Verzeichnis durchläuft. Für einen Iterator `X`, den Ausdruck `*X` ergibt ein Objekt der Klasse `directory_entry` , umschließt den Dateinamen und alles, was zu dessen Status bekannt.

Die Klasse speichert ein Objekt des Typs `path`namens `mydir` hier zum Zweck der Darstellung, die den Namen der zu sequenzierenden Verzeichnisses darstellt, und ein Objekt des Typs `directory_entry` namens `myentry` hier steht die aktuelle Dateiname in der verzeichnissequenz. Ein standardmäßig erstelltes Objekt des Typs `directory_entry` verfügt über eine leere `mydir` Pfadnamen und den Sequenzende Iterator darstellt.

Angenommen, das Verzeichnis `abc` Einträge `def` und `ghi`, den Code:

`for (directory_iterator next(path("abc")), end; next != end; ++next)     visit(next->path());`

Ruft `visit` mit den Argumenten `path("abc/def")` und `path("abc/ghi")`.

Weitere Informationen und Codebeispiele finden Sie unter [Dateisystemnavigation (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Syntax

```cpp
class directory_iterator;
```

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[directory_iterator](#directory_iterator)|Erstellt einen Eingabe-Iterator, der den Dateinamen in einem Verzeichnis durchläuft.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[Inkrement](#increment)|Versucht, gelangen zum nächsten Dateinamen im Verzeichnis.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator!=](#op_neq)|Gibt `!(*this == right)`zurück.|
|[operator=](#op_as)|Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.|
|[operator==](#op_eq)|Gibt **"true"** nur dann, wenn beide `*this` und *rechten* Sequenzende Iteratoren oder beide sind nicht Ende-des-Sequenzende-Iteratoren.|
|[operator*](#op_star)|Gibt `myentry`zurück.|
|[operator->](#op_cast)|Gibt `&**this`zurück.|
|[operator++](#op_increment)|Aufrufe `increment()`, dann gibt `*this`, oder erstellt eine Kopie des Objekts aufrufen `increment()`, klicken Sie dann die Kopie zurück.|

## <a name="requirements"></a>Anforderungen

**Header:** \<experimental/filesystem>

**Namespace:** std::experimental::filesystem

## <a name="directory_iterator"></a> directory_iterator::directory_iterator

Der erste Konstruktor erzeugt einen Sequenzende-Iterator. Im zweiten und dritten Konstruktoren Store *"pval"* in `mydir`, dann öffnen und Lesen `mydir` als Verzeichnis. Wenn erfolgreich, sie den ersten Dateinamen im Verzeichnis in speichern `myentry`; andernfalls erstellen Sie einen Sequenzende Iterator.

Die als Standard festgelegten Konstruktoren verhalten sich wie erwartet.

```cpp
directory_iterator() noexcept;
explicit directory_iterator(const path& pval);

directory_iterator(const path& pval, error_code& ec) noexcept;
directory_iterator(const directory_iterator&) = default;
directory_iterator(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Parameter

*"pval"*<br/>
Der gespeicherte Dateinamenpfad.

*EC*<br/>
Der Statuscode Fehler.

*directory_iterator*<br/>
Das gespeicherte Objekt.

## <a name="increment"></a> directory_iterator:: Increment

Die Funktion versucht, zum nächsten Dateinamen im Verzeichnis zu gelangen. Wenn der Erfolg dieser Dateiname in speichert `myentry`; andernfalls erstellt Sie einen Sequenzende Iterator.

```cpp
directory_iterator& increment(error_code& ec) noexcept;
```

## <a name="op_neq"></a> directory_iterator::! =

Der Memberoperator gibt `!(*this == right)`zurück.

```cpp
bool operator!=(const directory_iterator& right) const;
```

### <a name="parameters"></a>Parameter

*right*<br/>
Die [Directory_iterator](../standard-library/directory-iterator-class.md) wird im Vergleich zu den `directory_iterator`.

## <a name="op_as"></a> directory_iterator:: =

Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.

```cpp
directory_iterator& operator=(const directory_iterator&) = default;
directory_iterator& operator=(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Parameter

*right*<br/>
Die [Directory_iterator](../standard-library/directory-iterator-class.md) kopiert wird, in der `directory_iterator`.

## <a name="op_eq"></a> directory_iterator:: ==

Der Memberoperator gibt **"true"** nur dann, wenn beide `*this` und *rechten* Sequenzende Iteratoren oder beide sind nicht Ende-des-Sequenzende-Iteratoren.

```cpp
bool operator==(const directory_iterator& right) const;
```

### <a name="parameters"></a>Parameter

*right*<br/>
Die [Directory_iterator](../standard-library/directory-iterator-class.md) wird im Vergleich zu den `directory_iterator`.

## <a name="op_star"></a> directory_iterator:: *

Der Memberoperator gibt `myentry`zurück.

```cpp
const directory_entry& operator*() const;
```

## <a name="op_cast"></a> directory_iterator:: ->

Die Memberfunktion gibt `&**this`zurück.

```cpp
const directory_entry * operator->() const;
```

## <a name="op_increment"></a> directory_iterator:: Operator++-

Ruft die erste Memberfunktion `increment()`, dann gibt `*this`. Die zweite Memberfunktion erstellt eine Kopie des Objekts aufrufen `increment()`, klicken Sie dann die Kopie zurück.

```cpp
directory_iterator& operator++();
directory_iterator& operator++(int);
```

### <a name="parameters"></a>Parameter

*int*<br/>
Die Anzahl der Schritte.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[Dateisystemnavigation (C++)](../standard-library/file-system-navigation.md)<br/>
