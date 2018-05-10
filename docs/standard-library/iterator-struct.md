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
ms.openlocfilehash: e9cd414e2e6f23cb2fe44e6de4b5f53b33ef3555
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="iterator-struct"></a>iterator-Struktur

Eine leere Basisstruktur wird verwendet, um sicherzustellen, dass eine benutzerdefinierte Iteratorklasse ordnungsgemäß mit **iterator_trait**s funktioniert.

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

- `value_type` ( ein Synonym für den Vorlagenparameter **Type**).

- `difference_type` (ein Synonym für den Vorlagenparameter `Distance`).

- `distance_type` (ein Synonym für den Vorlagenparameter `Distance`).

- `pointer` (ein Synonym für den Vorlagenparameter `Pointer`).

- `reference` (ein Synonym für den Vorlagenparameter `Reference`).

Beachten Sie, dass `value_type` kein konstanter Typ sein darf, auch wenn der **Zeiger** auf ein Objekt vom const-**Type** verweist und der Verweis ein Objekt vom const-**Type** kennzeichnet.

## <a name="example"></a>Beispiel

Unter [iterator_traits](../standard-library/iterator-traits-struct.md) finden Sie ein Beispiel für das Deklarieren und Verwenden von Typen in der Iterator-Basisklasse.

## <a name="requirements"></a>Anforderungen

**Header:** \<iterator>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[\<iterator>](../standard-library/iterator.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
