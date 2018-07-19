---
title: hash-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- typeindex/std::hash
dev_langs:
- C++
ms.assetid: e5a41202-ef3b-45d0-b3a7-4c2dbdc0487a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82684ac8f2dcd0b8e1b76f04ace8d51051681bd0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33843651"
---
# <a name="hash-structure"></a>hash-Struktur

Die Vorlagenklasse definiert die Methode als eine Rückgabe von `val.hash_code()`. Die Methode definiert eine Hashfunktion, die verwendet wird, um einer Verteilung von Indexwerten Werte des Typs [type_index](../standard-library/type-index-class.md) zuzuordnen.

## <a name="syntax"></a>Syntax

```cpp
template <>
struct hash<type_index>
: public unary_function<type_index, size_t>
 { // hashes a typeinfo object
    size_t operator()(type_index val) const;

};
```

## <a name="see-also"></a>Siehe auch

[\<typeindex>](../standard-library/typeindex.md)<br/>
