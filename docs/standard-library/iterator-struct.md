---
title: iterator-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xutility/std::iterator
dev_langs:
- C++
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a399fa8a9f8fc9a73d75605f31245e42a2154b7c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963627"
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
