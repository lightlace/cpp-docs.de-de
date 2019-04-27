---
title: hash-Struktur
ms.date: 11/04/2016
f1_keywords:
- typeindex/std::hash
ms.assetid: e5a41202-ef3b-45d0-b3a7-4c2dbdc0487a
ms.openlocfilehash: ba05d70692b2f85c1a14f319fb1e92dcadc0ccce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62158780"
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
