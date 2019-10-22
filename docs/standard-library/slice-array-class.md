---
title: slice_array-Klasse
ms.date: 11/04/2016
f1_keywords:
- valarray/std::slice_array
helpviewer_keywords:
- slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
ms.openlocfilehash: 358348a57b823fcea82cd296967c83778819361d
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688965"
---
# <a name="slice_array-class"></a>slice_array-Klasse

Eine interne Hilfsklassen Vorlage, die Slice-Objekte unterstützt, indem Vorgänge zwischen Teilmengen Arrays bereitgestellt werden, die durch das Slice eines Valarray-Objekts definiert werden.

## <a name="syntax"></a>Syntax

```cpp
template <class Type>
class slice_array : public slice {
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

Die Klasse beschreibt ein Objekt, das einen Verweis auf ein Objekt der Klasse [valarray](../standard-library/valarray-class.md) **\<Type>** zusammen mit einem Objekt der Klasse [slice](../standard-library/slice-class.md) speichert, das die Reihenfolge der Elemente beschreibt, die im **valarray\<Type>** -Objekt ausgewählt werden sollen.

Die Klassen Vorlage wird indirekt von bestimmten Valarray-Vorgängen erstellt und kann nicht direkt im Programm verwendet werden. Eine interne, zusätzliche Klassen Vorlage, die von dem Slice-Index Operator verwendet wird:

`slice_array`\<**Type**> `valarray`< **Type**:: `operator[]` ( `slice`).

Sie erstellen ein `slice_array<Type>` Objekt nur, indem Sie einen Ausdruck in der [Form&#91;"&#93;VA SL](../standard-library/valarray-class.md#op_at)" für einen Slice `sl` der Valarray-`va` schreiben. Die Element Funktionen der Klasse Slice_array Verhalten sich dann wie die entsprechenden Funktions Signaturen, die für `valarray<Type>` definiert sind, mit dem Unterschied, dass nur die Reihenfolge der ausgewählten Elemente betroffen ist. Die Sequenz, die vom slice_array gesteuert wird, wird durch die drei Parameter des Segmentkonstruktors, den Index des ersten Elements im Segment und die Anzahl von Elementen und den Abstand zwischen den Elementen definiert. Ein aus der von **VA**[`slice` (2, 5, 3) [(2, 5, 3)) ausgeschnittener Wert aus Valarray-`va` wählt Elemente mit den Indizes 2, 5, 8, 11 und 14 aus `va` Die Indizes müssen für die Prozedur gültig sein, um gültig zu sein.

## <a name="example"></a>Beispiel

Im Beispiel für [slice::slice](../standard-library/slice-class.md#slice) wird verdeutlicht, wie ein slice_array deklariert und verwendet wird.

## <a name="requirements"></a>Anforderungen

**Header:** \<valarray>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)
