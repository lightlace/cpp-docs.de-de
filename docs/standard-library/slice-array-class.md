---
title: slice_array-Klasse
ms.date: 11/04/2016
f1_keywords:
- valarray/std::slice_array
helpviewer_keywords:
- slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
ms.openlocfilehash: 9577447b2201c1c9e53192b99abad1979f45d15f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412539"
---
# <a name="slicearray-class"></a>slice_array-Klasse

Eine interne zusätzliche Vorlagenklasse, die slice-Objekte (Segmente) unterstützt, indem sie Vorgänge zwischen Teilmengenarrays bereitstellt, die durch das Segment eines valarray-Objekts definiert sind.

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

Die Klasse beschreibt ein Objekt, das einen Verweis auf ein Objekt der Klasse [valarray](../standard-library/valarray-class.md)**\<Type>** zusammen mit einem Objekt der Klasse [slice](../standard-library/slice-class.md) speichert, das die Reihenfolge der Elemente beschreibt, die im **valarray\<Type>**-Objekt ausgewählt werden sollen.

Die Vorlagenklasse wird indirekt durch bestimmte valarray-Operationen erstellt und kann nicht direkt in der Anwendung verwendet werden. Eine interne auxiliary-Vorlagenklasse, die von dem Segment-Indexoperator verwendet wird:

`slice_array`\<**Type**> `valarray`< **Type**:: `operator[]` ( `slice`).

Sie erstellen eine `slice_array<Type>` -Objekt nur, indem Sie das Schreiben eines Ausdrucks des Formulars [va&#91;sl&#93;](../standard-library/valarray-class.md#op_at), für einen Slice `sl` valarray-Objekts `va`. Die Memberfunktionen der Slice_array-Klasse Verhalten sich dann wie die entsprechenden Funktionssignaturen für definiert `valarray<Type>`, außer dass nur die Reihenfolge der ausgewählten Elemente betroffen ist. Die Sequenz, die vom slice_array gesteuert wird, wird durch die drei Parameter des Segmentkonstruktors, den Index des ersten Elements im Segment und die Anzahl von Elementen und den Abstand zwischen den Elementen definiert. Ein slice_array-Element, das aus valarray-Objekt ausgeschnitten `va` deklariert, indem **va**[ `slice`(2, 3, 5)] wählt Elemente mit Indizes, 2, 5, 8, 11 und 14 von `va`. Die Indizes müssen für die Prozedur gültig sein, um gültig zu sein.

## <a name="example"></a>Beispiel

Im Beispiel für [slice::slice](../standard-library/slice-class.md#slice) wird verdeutlicht, wie ein slice_array deklariert und verwendet wird.

## <a name="requirements"></a>Anforderungen

**Header:** \<valarray>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
