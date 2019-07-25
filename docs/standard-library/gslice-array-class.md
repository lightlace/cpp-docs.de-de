---
title: gslice_array-Klasse
ms.date: 11/04/2016
f1_keywords:
- valarray/std::gslice_array
helpviewer_keywords:
- gslice_array class
ms.assetid: ad1b4514-b14a-4baf-a293-d5a8e8674c75
ms.openlocfilehash: 37c54d09fdfe920c832c4baa7984fee4e090d04a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448917"
---
# <a name="gslicearray-class"></a>gslice_array-Klasse

Eine interne zusätzliche Vorlagenklasse, die allgemeine slice-Objekte (Segmente) unterstützt, indem sie Vorgänge zwischen Teilmengenarrays bereitstellt, die durch das allgemeine Segment eines valarray-Objekts definiert sind.

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

Die Klasse beschreibt ein Objekt, das einen Verweis auf ein Objekt `va` der Klasse [Valarray](../standard-library/valarray-class.md) **\<Type >** speichert, zusammen mit einem `gs` Objekt der Klasse [gslice](../standard-library/gslice-class.md) , das die Reihenfolge der Elemente beschreibt, aus denen Sie auswählen können. Das `valarray<Type>` -Objekt.

Sie erstellen ein `gslice_array<Type>` -Objekt nur, indem Sie einen Ausdruck der [Form&#91;VA&#93;GS](../standard-library/valarray-class.md#op_at)schreiben. Die Member-Funktionen der-Klasse Gslice_array Verhalten sich dann wie die entsprechenden Funktions `valarray<Type>`Signaturen, die für definiert sind, mit dem Unterschied, dass nur die Sequenz ausgewählter Elemente betroffen ist.

Die Vorlagenklasse wird indirekt durch bestimmte valarray-Operationen erstellt und kann nicht direkt in der Anwendung verwendet werden. Eine interne auxiliary-Vorlagenklasse wird stattdessen von dem Segment-Indexoperator verwendet:

`gslice_array`\< **Type**> `valarray`\< **Type**>:: `operator[]` (**constgslice&** ).

Sie erstellen ein `gslice_array<Type>` -Objekt nur, indem Sie einen Ausdruck des `va[gsl]`Formulars für einen Slice `gsl` eines Valarray `va`-Objekts schreiben. Die Member-Funktionen der-Klasse Gslice_array Verhalten sich dann wie die entsprechenden Funktions `valarray<Type>`Signaturen, die für definiert sind, mit dem Unterschied, dass nur die Sequenz ausgewählter Elemente betroffen ist. Die Sequenz, die vom gslice_array gesteuert wird, wird durch die drei Parameter des Segmentkonstruktors, den Index des ersten Elements im ersten Segment und die Anzahl der Elemente in jedem Segment und den Abstand zwischen den Elementen in jedem Segment definiert.

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

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
