---
title: ctype&lt;char&gt;-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- ctype<char>
- locale/std::ctype<char>
dev_langs:
- C++
helpviewer_keywords:
- ctype<char> class
ms.assetid: ee30acb4-a743-405e-b3d4-13602092da84
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: edbc96419e68cf584222e4008f58fd96169b2fb9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="ctypeltchargt-class"></a>ctype&lt;char&gt;-Klasse

Die Klasse stellt eine explizite Spezialisierung der Vorlagenklasse **ctype\<CharType**> für den Typ `char` dar und beschreibt ein Objekt, das als Gebietsschemafacet dienen kann, um verschiedene Eigenschaften eines Zeichens vom Typ `char` zu kennzeichnen.

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

- Ein Objekt der Klasse ctype< `char`> speichert einen Zeiger auf das erste Element einer ctype-Maskentabelle. Hierbei handelt es sich um ein Array mit UCHAR_MAX + 1-Elementen vom Typ **ctype_base::mask**. Darüber hinaus speichert es ein boolesches Objekt, das angibt, ob das Array (mit `operator delete[]`) gelöscht werden soll, wenn das ctype\< **Elem**>-Objekt zerstört wird.

- Mit dem zugehörigen einzigen öffentlichen Konstruktor können Sie **tab**, die ctype-Maskentabelle, und **del**, das boolesche Objekt angeben, das wahr ist, wenn das Array beim Zerstören des ctype< `char`>-Objekts gelöscht werden soll. Zudem können Sie den Parameter „refs“ angeben, der als Referenzzähler dient.

- Die geschützte Memberfunktion **table** gibt die gespeicherte ctype-Maskentabelle zurück.

- Das statische Memberobjekt **table_size** gibt die in einer ctype-Maskentabelle mindestens erforderliche Anzahl von Elementen an.

- Die geschützte statische Memberfunktion **classic_table** gibt die dem Gebietsschema „C“ entsprechende ctype-Maskentabelle zurück.

- Die geschützten virtuellen Memberfunktionen [do_is](../standard-library/ctype-class.md#do_is), [do_scan_is](../standard-library/ctype-class.md#do_scan_is) bzw. [do_scan_not](../standard-library/ctype-class.md#do_scan_not) werden nicht verwendet. Die entsprechenden öffentlichen Memberfunktionen führen die jeweiligen Vorgänge selbst aus.

Die Memberfunktionen [do_narrow](../standard-library/ctype-class.md#do_narrow) und [do_widen](../standard-library/ctype-class.md#do_widen) kopieren Elemente unverändert.

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Facet-Klasse](http://msdn.microsoft.com/Library/dd4f12f5-cb1b-457f-af56-2fb204216ec1)<br/>
[ctype_base-Klasse](../standard-library/ctype-base-class.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
