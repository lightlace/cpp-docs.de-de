---
title: recursive_directory_iterator-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
dev_langs:
- C++
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82df045c5a41767093e690ec35ffeb3d81032474
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110655"
---
# <a name="recursivedirectoryiterator-class"></a>recursive_directory_iterator-Klasse

Beschreibt einen eingabeiterator, der den Dateinamen in einem Verzeichnis durchläuft möglicherweise rekursiv Unterverzeichnisse Absteigend. Für einen Iterator `X`, den Ausdruck `*X` ergibt ein Objekt der Klasse `directory_entry` , umschließt den Dateinamen und alles, was zu dessen Status bekannt.

Weitere Informationen und Codebeispiele finden Sie unter [Dateisystemnavigation (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Syntax

```cpp
class recursive_directory_iterator;
```

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse speichert Folgendes:

1. ein Objekt des Typs `stack<pair<directory_iterator, path>>`namens `mystack` hier für den Zweck der Darstellung, steht für die Schachtelung von Verzeichnissen, die zu sequenzierende

1. ein Objekt des Typs `directory_entry` namens `myentry` hier den aktuellen Dateinamen in der verzeichnissequenz darstellt

1. ein Objekt des Typs `bool`namens `no_push` hier die aufzeichnet, ob Rekursiver Abstieg in Unterverzeichnissen deaktiviert ist

1. ein Objekt des Typs `directory_options`namens `myoptions` hier an, die die Optionen, die bei der Erstellung eingerichtet aufzeichnet

Ein standardmäßig erstelltes Objekt des Typs `recursive_directory_entry` hat einen Sequenzende Iterator am `mystack.top().first` und den Sequenzende Iterator darstellt. Angenommen, das Verzeichnis `abc` Einträge `def` (ein Verzeichnis), `def/ghi`, und `jkl`, den Code:

```cpp
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)
    visit(next->path());
```

wird mit den Argumenten Aufruf besuchen `path("abc/def/ghi")` und `path("abc/jkl")`. Sie können absteigendes Durchlaufen einer Verzeichnisunterstruktur auf zwei Arten qualifizieren:

1. Ein Verzeichnis-Symlink werden überprüft nur, wenn Sie erstellen eine `recursive_directory_iterator` mit einem `directory_options` Argument, dessen Wert `directory_options::follow_directory_symlink`.

1. Wenn Sie aufrufen `disable_recursion_pending` und dann ein nachfolgendes Verzeichnis während eines Inkrements nicht rekursiv durchsucht werden.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[recursive_directory_iterator](#recursive_directory_iterator)|Erstellt ein Objekt vom Typ `recursive_directory_iterator`.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[Tiefe](#depth)|Gibt `mystack.size() - 1`, sodass `pval` auf Ebene 0 (null) ist.|
|[disable_recursion_pending](#disable_recursion_pending)|Speichert **"true"** in `no_push`.|
|[Inkrement](#increment)|Wechselt zum nächsten Dateinamen in der Sequenz.|
|[options](#options)|Gibt `myoptions`zurück.|
|[pop](#pop)|Gibt das nächste Objekt zurück.|
|[recursion_pending](#recursion_pending)|Gibt `!no_push`zurück.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator!=](#op_neq)|Gibt `!(*this == right)`zurück.|
|[operator=](#op_as)|Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.|
|[operator==](#op_eq)|Gibt **"true"** nur dann, wenn beide `*this` und *rechten* Sequenzende Iteratoren oder beide sind nicht Ende-des-Sequenzende-Iteratoren.|
|[operator*](#op_multiply)|Gibt `myentry`zurück.|
|[operator->](#op_cast)|Gibt `&**this`zurück.|
|[operator++](#op_increment)|Erhöht die `recursive_directory_iterator`.|

## <a name="requirements"></a>Anforderungen

**Header:** \<Filesystem >

**Namespace:** std::tr2::sys

## <a name="depth"></a> recursive_directory_iterator:: Depth

Gibt `mystack.size() - 1`, sodass `pval` auf Ebene 0 (null) ist.

```cpp
int depth() const;
```

## <a name="disable_recursion_pending"></a> recursive_directory_iterator:: disable_recursion_pending

Speichert **"true"** in `no_push`.

```cpp
void disable_recursion_pending();
```

## <a name="increment"></a> recursive_directory_iterator:: Increment

Wechselt zum nächsten Dateinamen in der Sequenz.

```cpp
recursive_directory_iterator& increment(error_code& ec) noexcept;
```

### <a name="parameters"></a>Parameter

*EC*<br/>
Angegebene Fehlercode.

### <a name="remarks"></a>Hinweise

Die Funktion versucht, zum nächsten Dateinamen in der geschachtelten Sequenz zu gelangen. Wenn der Erfolg dieser Dateiname in speichert `myentry`; andernfalls erstellt Sie einen Sequenzende Iterator.

## <a name="op_neq"></a> recursive_directory_iterator::! =

Gibt `!(*this == right)`zurück.

```cpp
bool operator!=(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>Parameter

*right*<br/>
Die [Recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) für den Vergleich.

## <a name="op_as"></a> recursive_directory_iterator:: =

Die als Standard festgelegten Memberzuweisungsoperatoren verhalten sich wie erwartet.

```cpp
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Parameter

*recursive_directory_iterator*<br/>
Die [Recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) kopiert wird, in der `recursive_directory_iterator`.

## <a name="op_eq"></a> recursive_directory_iterator:: ==

Gibt **"true"** nur dann, wenn beide `*this` und *rechten* Sequenzende Iteratoren oder beide sind nicht Ende-des-Sequenzende-Iteratoren.

```cpp
bool operator==(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>Parameter

*right*<br/>
Die [Recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) für den Vergleich.

## <a name="op_multiply"></a> recursive_directory_iterator:: *

Gibt `myentry`zurück.

```cpp
const directory_entry& operator*() const;
```

## <a name="op_cast"></a> recursive_directory_iterator:: ->

Gibt `&**this`zurück.

```cpp
const directory_entry * operator->() const;
```

## <a name="op_increment"></a> recursive_directory_iterator:: Operator++-

Erhöht die `recursive_directory_iterator`.

```cpp
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```

### <a name="parameters"></a>Parameter

*int*<br/>
Das angegebene Inkrement.

### <a name="remarks"></a>Hinweise

Ruft die erste Memberfunktion `increment()`, dann gibt `*this`. Die zweite Memberfunktion erstellt eine Kopie des Objekts aufrufen `increment()`, klicken Sie dann die Kopie zurück.

## <a name="options"></a> recursive_directory_iterator:: Options

Gibt `myoptions`zurück.

```cpp
directory_options options() const;
```

## <a name="pop"></a> recursive_directory_iterator:: POP

Gibt das nächste Objekt zurück.

```cpp
void pop();
```

### <a name="remarks"></a>Hinweise

Wenn `depth() == 0` das Objekt nicht mehr einen Sequenzende Iterator. Andernfalls beendet die Memberfunktion das Durchsuchen des aktuellen (tiefsten) Verzeichnisses und setzt das Durchsuchen auf der nächstniedrigeren Tiefe fort.

## <a name="recursion_pending"></a> recursive_directory_iterator:: recursion_pending

Gibt `!no_push`zurück.

```cpp
bool recursion_pending() const;
```

## <a name="recursive_directory_iterator"></a> recursive_directory_iterator:: recursive_directory_iterator

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

*"pval"*<br/>
Der angegebene Pfad.

*error_code*<br/>
Der angegebene Fehlercode.

*"OPTS"*<br/>
Die Optionen für die angegebene Verzeichnis.

*recursive_directory_iterator*<br/>
Das `recursive_directory_iterator`-Element, von dem das erstellte `recursive_directory_iterator`-Element eine Kopie sein soll.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor erzeugt einen Sequenzende-Iterator. Im zweiten und dritten Konstruktoren Store **"false"** in `no_push` und `directory_options::none` in `myoptions`, dann öffnen und Lesen *"pval"* als Verzeichnis. Wenn erfolgreich, sie initialisieren `mystack` und `myentry` zum Kennzeichnen der ersten nicht-Verzeichnis-Dateinamen in der geschachtelten Sequenz; andernfalls erstellen Sie einen Sequenzende Iterator.

Die vierten und fünften Konstruktoren weisen das gleiche Verhalten als der zweite und dritte, außer dass sie zuerst speichern *"OPTS"* in `myoptions`. Die als Standard festgelegten Konstruktoren verhalten sich wie erwartet.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[Dateisystemnavigation (C++)](../standard-library/file-system-navigation.md)<br/>
