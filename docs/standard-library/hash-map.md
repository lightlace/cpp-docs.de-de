---
title: '&lt;hash_map&gt;'
ms.date: 01/18/2018
f1_keywords:
- <hash_map>
- std::<hash_map>
helpviewer_keywords:
- hash_map header
ms.openlocfilehash: cca38386892ce4df6bf9863e0cbac3dc16106d35
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448662"
---
# <a name="lthashmapgt"></a>&lt;hash_map&gt;

> [!NOTE]
> Dieser Header ist veraltet. Die Alternative ist [ \<unordered_map >](unordered-map.md).

Definiert die Containervorlagenklassen „hash_map“ und „hash_multimap“ und deren unterstützende Vorlagen.

## <a name="syntax"></a>Syntax

```
#include <hash_map>
```

### <a name="operators"></a>Operatoren

|Hash_map-Version|Hash_multimap-Version|Beschreibung|
|-----------------------|----------------------------|-----------------|
|[operator!= (hash_map)](hash-map-operators.md#op_neq)|[operator!=(hash_multimap)](hash-map-operators.md#op_neq_mm)|Überprüft, ob das hash_map- oder hash_multimap-Objekt links vom Operator ungleich dem hash_map- oder hash_multimap-Objekt rechts vom Operator ist.|
|[operator== (hash_map)](hash-map-operators.md#op_eq_eq)|[operator== (hash_multimap)](hash-map-operators.md#op_eq_eq_mm)|Überprüft, ob das hash_map- oder hash_multimap-Objekt links vom Operator gleich dem hash_map- oder hash_multimap-Objekt rechts vom Operator ist.|

### <a name="specialized-template-functions"></a>Spezialisierte Vorlagenfunktionen

|Hash_map-Version|Hash_multimap-Version|Beschreibung|
|-----------------------|----------------------------|-----------------|
|[swap (hash_map)](hash-map-class.md#swap)|[swap (hash_multimap)](hash-multimap-class.md#swap)|Tauscht die Elemente zweier hash_map- oder hash_multimap-Objekte aus.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[hash_compare-Klasse](hash-compare-class.md)|Beschreibt ein Objekt, das von jedem Hash assoziativen Container – hash_map, hash_multimap, hash_set oder Hash_multiset – als Standard `Traits` Parameter Objekt verwendet werden kann, um die darin enthaltenen Elemente zu sortieren und zu hashen.|
|[value_compare-Klasse](value-compare-class.md)|Stellt ein Funktionsobjekt bereit, das die Elemente einer hash_map vergleichen kann, indem die Werte ihrer Schlüssel verglichen werden, um deren relative Reihenfolge in der hash_map zu bestimmen.|
|[hash_map-Klasse](hash-map-class.md)|Speichert Daten und ruft sie schnell aus einer Auflistung ab, in der jedes Element ein Paar ist, das einen Sortierschlüssel mit eindeutigem Wert und einen zugeordneten Datenwert aufweist.|
|[hash_multimap-Klasse](hash-multimap-class.md)|Speichert Daten und ruft sie schnell aus einer Auflistung ab, in der jedes Element ein Paar ist, das einen Sortierschlüssel, dessen Wert nicht eindeutig sein muss, und einen zugeordneten Datenwert aufweist.|

## <a name="requirements"></a>Anforderungen

**Header:** \<hash_map>

**Namespace:** stdext

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](cpp-standard-library-header-files.md)\
[Threadsicherheit in der C++-Standardbibliothek](thread-safety-in-the-cpp-standard-library.md)\
[C++-Standardbibliotheksreferenz](cpp-standard-library-reference.md)
