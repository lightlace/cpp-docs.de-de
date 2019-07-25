---
title: ctype&lt;char&gt;-Klasse
ms.date: 11/04/2016
f1_keywords:
- ctype<char>
- locale/std::ctype<char>
helpviewer_keywords:
- ctype<char> class
ms.assetid: ee30acb4-a743-405e-b3d4-13602092da84
ms.openlocfilehash: 7fe1eef32741d63e7b2e2c2320d18f445784c44f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455468"
---
# <a name="ctypeltchargt-class"></a>ctype&lt;char&gt;-Klasse

Die-Klasse ist eine explizite Spezialisierung der Vorlagen `ctype\<CharType>` Klasse für Type **char**, die ein Objekt beschreibt, das als Gebiets Schema Aspekt dienen kann, um verschiedene Eigenschaften eines Zeichens vom Typ **char**zu bezeichnen.

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

Die explizite Spezialisierung unterscheidet sich von der Vorlagenklasse in verschiedenen Punkten:

- Ein Objekt der CType-Klasse `char`< > speichert einen Zeiger auf das erste Element einer CType Mask-Tabelle, ein Array von UCHAR_MAX + 1-Elementen `ctype_base::mask`vom Typ. Darüber hinaus speichert es ein boolesches Objekt, das angibt, ob das Array (mit `operator delete[]`) gelöscht werden soll, wenn das ctype\< **Elem**>-Objekt zerstört wird.

- Mit dem einzigen öffentlichen Konstruktor können Sie `tab`, die CType-Masken Tabelle und `del`das boolesche Objekt angeben, das true ist, wenn das Array gelöscht werden soll, wenn der `char`CType-< > Objekt zerstört wird, sowie der Verweis Zähler. Parameter Verweise.

- Die geschützte Member- `table` Funktion gibt die gespeicherte CType Mask-Tabelle zurück.

- Das statische Member- `table_size` Objekt gibt die Mindestanzahl von Elementen in einer CType Mask-Tabelle an.

- Die geschützte statische Member- `classic_table`Funktion (gibt die CType-Masken Tabelle zurück, die für das Gebiets Schema "C" geeignet ist.

- Die geschützten virtuellen Memberfunktionen [do_is](../standard-library/ctype-class.md#do_is), [do_scan_is](../standard-library/ctype-class.md#do_scan_is) bzw. [do_scan_not](../standard-library/ctype-class.md#do_scan_not) werden nicht verwendet. Die entsprechenden öffentlichen Memberfunktionen führen die jeweiligen Vorgänge selbst aus.

Die Memberfunktionen [do_narrow](../standard-library/ctype-class.md#do_narrow) und [do_widen](../standard-library/ctype-class.md#do_widen) kopieren Elemente unverändert.

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[facet-Klasse](locale-class.md#facet_class)\
[ctype_base-Klasse](../standard-library/ctype-base-class.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
