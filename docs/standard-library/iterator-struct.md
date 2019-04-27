---
title: iterator-Struktur
ms.date: 11/04/2016
f1_keywords:
- xutility/std::iterator
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
ms.openlocfilehash: 1dd62a6141e690d3bd4dcad69aa107c126a0f386
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62224102"
---
# <a name="iterator-struct"></a>iterator-Struktur

Eine leere Basisstruktur verwendet, um sicherzustellen, dass eine benutzerdefinierte iteratorklasse ordnungsgemäß mit funktioniert `iterator_trait`s.

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

Beachten Sie, dass `value_type` sollte sich nicht auf eine Konstanten Typs selbst wenn `pointer` verweist auf ein Objekt vom **const** `Type` und Verweis bezieht sich auf ein Objekt des **const** `Type`.

## <a name="example"></a>Beispiel

Unter [iterator_traits](../standard-library/iterator-traits-struct.md) finden Sie ein Beispiel für das Deklarieren und Verwenden von Typen in der Iterator-Basisklasse.

## <a name="requirements"></a>Anforderungen

**Header:** \<iterator>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[\<iterator>](../standard-library/iterator.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
