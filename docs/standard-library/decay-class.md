---
title: decay-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::decay
dev_langs:
- C++
helpviewer_keywords:
- decay class
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7d3ad5bae067bb9661b6cf475d0831b2b2dfcd2a
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44099524"
---
# <a name="decay-class"></a>decay-Klasse

Erzeugt den Typ bei der Übergabe durch einen Wert. Erzeugt einen Typ ohne Verweis, einen nicht konstanten Typ, einen nicht flüchtigen Typ, oder erstellt aus einer Funktion oder aus einem Arraytyp einen Zeiger auf den Typ.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct decay;

template <class T>
using decay_t = typename decay<T>::type;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der zu ändernde Typ.

## <a name="remarks"></a>Hinweise

Verwenden Sie die decay-Vorlage, um den resultierenden Typ so zu erstellen, als würde er durch einen Wert als Argument übergeben. Der Vorlagenklassenmember typedef `type` enthält einen geänderten Typ, der in den folgenden Phasen definiert wird:

- Der Typ `U` ist als `remove_reference<T>::type` definiert.

- Wenn `is_array<U>::value` wahr ist, lautet der geänderte `type`-Typ `remove_extent<U>::type *`.

- Wenn `is_function<U>::value` wahr ist, lautet der geänderte `type`-Typ `add_pointer<U>::type`.

- Andernfalls lautet der geänderte `type`-Typ `remove_cv<U>::type`.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
