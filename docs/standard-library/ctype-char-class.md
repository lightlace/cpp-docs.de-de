---
title: ctype&lt;char&gt;-Klasse
ms.date: 11/04/2016
f1_keywords:
- ctype<char>
- locale/std::ctype<char>
helpviewer_keywords:
- ctype<char> class
ms.assetid: ee30acb4-a743-405e-b3d4-13602092da84
ms.openlocfilehash: 08bf2c5c814eaed7b409295fcf50c66577f6a5d9
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688149"
---
# <a name="ctypeltchargt-class"></a>ctype&lt;char&gt;-Klasse

Bei der-Klasse handelt es sich um eine explizite Spezialisierung der Klassen Vorlagen `ctype\<CharType>` für den Typ **char**, der ein Objekt beschreibt, das als Gebiets Schema Aspekt dienen kann, um verschiedene Eigenschaften eines Zeichens vom Typ **char**zu charakterisieren.

## <a name="syntax"></a>Syntax

```cpp
template <>
class ctype<char>
: public ctype_base
{
public:
    typedef char _Elem;
    typedef _Elem char_type;
    bool is(
    mask _Maskval,
    _Elem _Ch) const;

    const _Elem* is(
    const _Elem* first,
    const _Elem* last,
    mask* dest) const;

    const _Elem* scan_is(
    mask _Maskval,
    const _Elem* first,
    const _Elem* last) const;

    const _Elem* scan_not(
    mask _Maskval,
    const _Elem* first,
    const _Elem* last) const;

    _Elem tolower(
    _Elem _Ch) const;

    const _Elem* tolower(
    _Elem* first,
    const _Elem* last) const;

    _Elem toupper(
    _Elem _Ch) const;

    const _Elem* toupper(
    _Elem* first,
    const _Elem* last) const;

    _Elem widen(
    char _Byte) const;

    const _Elem* widen(
    const char* first,
    const char* last,
    _Elem* dest) const;

    const _Elem* _Widen_s(
    const char* first,
    const char* last,
    _Elem* dest,
    size_t dest_size) const;

    _Elem narrow(
    _Elem _Ch,
    char _Dflt = '\0') const;

    const _Elem* narrow(
    const _Elem* first,
    const _Elem* last,
    char _Dflt,
    char* dest) const;

    const _Elem* _Narrow_s(
    const _Elem* first,
    const _Elem* last,
    char _Dflt,
    char* dest,
    size_t dest_size) const;

    static locale::id& id;
    explicit ctype(
    const mask* _Table = 0,
    bool _Deletetable = false,
    size_t _Refs = 0);

protected:
    virtual ~ctype();
//other protected members
};
```

## <a name="remarks"></a>Hinweise

Die explizite Spezialisierung unterscheidet sich auf verschiedene Arten von der Klassen Vorlage:

- Ein Objekt der Klasse CType < `char` > einen Zeiger auf das erste Element einer CType Mask-Tabelle speichert, ein Array von UCHAR_MAX + 1-Elementen vom Typ `ctype_base::mask`. Darüber hinaus speichert es ein boolesches Objekt, das angibt, ob das Array (mit `operator delete[]`) gelöscht werden soll, wenn das ctype\< **Elem**>-Objekt zerstört wird.

- Der einzige öffentliche Konstruktor ermöglicht das Angeben von `tab`, der CType Mask-Tabelle und `del`, das boolesche Objekt, das true ist, wenn das Array gelöscht werden soll, wenn der CType < `char` > Objekt zerstört wird, sowie der Verweis Zähler Parameter refs.

- Die geschützte Member-Funktion `table` gibt die gespeicherte CType Mask-Tabelle zurück.

- Das statische Member-Objekt `table_size` das die Mindestanzahl von Elementen in einer CType-Masken Tabelle angibt.

- Die geschützte statische Member-Funktion `classic_table` (gibt die CType-Masken Tabelle zurück, die für das Gebiets Schema "C" geeignet ist.

- Die geschützten virtuellen Memberfunktionen [do_is](../standard-library/ctype-class.md#do_is), [do_scan_is](../standard-library/ctype-class.md#do_scan_is) bzw. [do_scan_not](../standard-library/ctype-class.md#do_scan_not) werden nicht verwendet. Die entsprechenden öffentlichen Memberfunktionen führen die jeweiligen Vorgänge selbst aus.

Die Memberfunktionen [do_narrow](../standard-library/ctype-class.md#do_narrow) und [do_widen](../standard-library/ctype-class.md#do_widen) kopieren Elemente unverändert.

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[facet-Klasse](locale-class.md#facet_class)\
[ctype_base-Klasse](../standard-library/ctype-base-class.md)\
[Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)
