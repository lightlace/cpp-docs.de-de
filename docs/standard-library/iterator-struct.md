---
title: iterator-Struktur
ms.date: 11/04/2016
f1_keywords:
- xutility/std::iterator
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
ms.openlocfilehash: 64c9be76cb92d818e40714dd141ded3a8cc17c8a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455621"
---
# <a name="iterator-struct"></a>iterator-Struktur

Eine leere Basis Struktur, mit der sichergestellt wird, dass eine benutzerdefinierte iteratorklasse `iterator_trait`ordnungsgemäß mit s funktioniert.

## <a name="syntax"></a>Syntax

```cpp
struct iterator {
   typedef Category iterator_category;
   typedef Type value_type;
   typedef Distance difference_type;
   typedef Distance distance_type;
   typedef Pointer pointer;
   typedef Reference reference;
   };
```

## <a name="remarks"></a>Hinweise

Die Vorlagenstruktur wird als Basistyp für alle Iteratoren verwendet. Definiert den Membertypen

- `iterator_category` (ein Synonym für den Vorlagenparameter `Category`).

- `value_type` (ein Synonym für den Vorlagenparameter `Type`).

- `difference_type` (ein Synonym für den Vorlagenparameter `Distance`).

- `distance_type` (ein Synonym für den Vorlagenparameter `Distance`).

- `pointer` (ein Synonym für den Vorlagenparameter `Pointer`).

- `reference` (ein Synonym für den Vorlagenparameter `Reference`).

Beachten Sie `value_type` , dass kein konstanter Typ sein sollte, `pointer` auch wenn Punkte an `Type` einem Objekt von "Konstanten **" und "** Reference" ein Objekt von  `Type`"Konstanten" bezeichnen.

## <a name="example"></a>Beispiel

Unter [iterator_traits](../standard-library/iterator-traits-struct.md) finden Sie ein Beispiel für das Deklarieren und Verwenden von Typen in der Iterator-Basisklasse.

## <a name="requirements"></a>Anforderungen

**Header:** \<iterator>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[\<iterator>](../standard-library/iterator.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)
