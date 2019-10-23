---
title: gslice_array-Klasse
ms.date: 11/04/2016
f1_keywords:
- valarray/std::gslice_array
helpviewer_keywords:
- gslice_array class
ms.assetid: ad1b4514-b14a-4baf-a293-d5a8e8674c75
ms.openlocfilehash: 68ce774128395e941ff80580a02c4ee28a74a4e4
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689595"
---
# <a name="gslice_array-class"></a>gslice_array-Klasse

Eine interne, zusätzliche Klassen Vorlage, die allgemeine Slice-Objekte unterstützt, indem Vorgänge zwischen Teilmengen Arrays bereitgestellt werden, die durch das allgemeine Slice eines Valarray-Objekts definiert werden.

## <a name="syntax"></a>Syntax

```cpp
template <class Type>
class gslice_array : public gsplice {
public:
    typedef Type value_type;
    void operator=(const valarray<Type>& x) const;

    void operator=(const Type& x) const;

    void operator*=(const valarray<Type>& x) const;

    void operator/=(const valarray<Type>& x) const;

    void operator%=(const valarray<Type>& x) const;

    void operator+=(const valarray<Type>& x) const;

    void operator-=(const valarray<Type>& x) const;

    void operator^=(const valarray<Type>& x) const;

    void operator&=(const valarray<Type>& x) const;

    void operator|=(const valarray<Type>& x) const;

    void operator<<=(const valarray<Type>& x) const;

    void operator>>=(const valarray<Type>& x) const;

// The rest is private or implementation defined
}
```

## <a name="remarks"></a>Hinweise

Die Klasse beschreibt ein Objekt, das einen Verweis auf ein Objekt `va` der Klasse [Valarray](../standard-library/valarray-class.md)  **\<Type >** zusammen mit einem Objekt `gs` der Klasse [gslice](../standard-library/gslice-class.md) speichert, das die Reihenfolge der Elemente beschreibt, die aus dem `valarray<Type>` Objekt ausgewählt werden sollen.

Sie erstellen nur dann ein `gslice_array<Type>` Objekt, indem Sie einen Ausdruck der [Form&#91;VA&#93;GS](../standard-library/valarray-class.md#op_at)schreiben. Die Element Funktionen der Klasse Gslice_array Verhalten sich dann wie die entsprechenden Funktions Signaturen, die für `valarray<Type>` definiert sind, mit dem Unterschied, dass nur die Reihenfolge der ausgewählten Elemente betroffen ist.

Die Klassen Vorlage wird indirekt von bestimmten Valarray-Vorgängen erstellt und kann nicht direkt im Programm verwendet werden. Stattdessen wird eine interne Erweiterungs Klassen Vorlage vom Operator "Slice" verwendet:

`gslice_array`\< **Type**> `valarray`\< **Type**>:: `operator[]` (**constgslice&** ).

Sie erstellen nur dann ein `gslice_array<Type>` Objekt, indem Sie einen Ausdruck der Form `va[gsl]` schreiben, für einen Slice `gsl` von Valarray-`va`. Die Element Funktionen der Klasse Gslice_array Verhalten sich dann wie die entsprechenden Funktions Signaturen, die für `valarray<Type>` definiert sind, mit dem Unterschied, dass nur die Reihenfolge der ausgewählten Elemente betroffen ist. Die Sequenz, die vom gslice_array gesteuert wird, wird durch die drei Parameter des Segmentkonstruktors, den Index des ersten Elements im ersten Segment und die Anzahl der Elemente in jedem Segment und den Abstand zwischen den Elementen in jedem Segment definiert.

Im folgenden Beispiel:

```cpp
const size_t lv[] = {2, 3};
const size_t dv[] = {7, 2};
const valarray<size_t> len(lv, 2), str(dv, 2);

// va[gslice(3, len, str)] selects elements with
//   indices 3, 5, 7, 10, 12, 14
```

Die Indizes müssen für die Prozedur gültig sein, um gültig zu sein.

## <a name="example"></a>Beispiel

Im Beispiel für [gslice::gslice](../standard-library/gslice-class.md#gslice) wird verdeutlicht, wie ein slice_array deklariert und verwendet wird.

## <a name="requirements"></a>Anforderungen

**Header:** \<valarray>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)
