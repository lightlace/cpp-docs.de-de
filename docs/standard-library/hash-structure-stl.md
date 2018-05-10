---
title: hash-Struktur (C++ Standardbibliothek)| Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- thread/std::hash
dev_langs:
- C++
ms.assetid: 4a8bf5bc-4334-4070-936b-98585f8a073b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f2e9fdbef911a0160ff42925a9c7984f0211069
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="hash-structure-c-standard-library"></a>Hash-Struktur (C++-Standardbibliothek)

Definiert eine Memberfunktion, die ein Wert zurückgibt, der eindeutig durch `Val` bestimmt wird. Das Funktionsobjekt definiert eine [hash](../standard-library/hash-class.md)-Funktion, die geeignet ist, Werte des Typs `thread::id` einer Verteilung von Indexwerten zuzuordnen.

## <a name="syntax"></a>Syntax

```cpp
template <>
struct hash<thread::id> :
    public unary_function<thread::id, size_t>
{
    size_t operator()(thread::id Val) const;


};
```

## <a name="requirements"></a>Anforderungen

**Header:** \<thread>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<thread>](../standard-library/thread.md)<br/>
[unary_function-Struktur](../standard-library/unary-function-struct.md)<br/>
