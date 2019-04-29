---
title: '&lt;map&gt;'
ms.date: 11/04/2016
f1_keywords:
- <map>
helpviewer_keywords:
- map header
ms.assetid: bbf76680-7362-456e-88fa-ecda93561b6a
ms.openlocfilehash: 0ea47a28599df543987831ee13a2c645f72a0113
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412994"
---
# <a name="ltmapgt"></a>&lt;map&gt;

Definiert die Containervorlagenklassen "map" und "multimap" und deren unterstützende Vorlagen.

## <a name="syntax"></a>Syntax

```cpp
#include <map>
```

## <a name="members"></a>Member

### <a name="operators"></a>Operatoren

|map-Version|multimap-Version|Beschreibung|
|-----------------|----------------------|-----------------|
|[operator!= (map)](../standard-library/map-operators.md#op_neq)|[operator!= (multimap)](../standard-library/map-operators.md#op_neq)|Überprüft, ob das map- oder multimap-Objekt links vom Operator ungleich dem map- oder multimap-Objekt rechts vom Operator ist.|
|[operator< (map)](../standard-library/map-operators.md#op_eq_eq)|[operator< (multimap)](../standard-library/map-operators.md#op_eq_eq)|Überprüft, ob das map- oder multimap-Objekt links vom Operator kleiner als das map- oder multimap-Objekt rechts vom Operator ist.|
|[operator<= (map)](../standard-library/map-operators.md#op_lt)|[operator\<= (multimap)](../standard-library/map-operators.md#op_lt)|Überprüft, ob das map- oder multimap-Objekt links vom Operator kleiner gleich dem map- oder multimap-Objekt rechts vom Operator ist.|
|[operator== (map)](../standard-library/map-operators.md#op_eq_eq)|[operator== (multimap)](../standard-library/map-operators.md#op_eq_eq_multimap)|Überprüft, ob das map- oder multimap-Objekt links vom Operator gleich dem map- oder multimap-Objekt rechts vom Operator ist.|
|[operator> (map)](../standard-library/map-operators.md#op_gt)|[operator> (multimap)](../standard-library/map-operators.md#op_gt_multimap)|Überprüft, ob das map- oder multimap-Objekt links vom Operator größer als das map- oder multimap-Objekt rechts vom Operator ist.|
|[operator>= (map)](../standard-library/map-operators.md#op_gt_eq)|[operator>= (multimap)](../standard-library/map-operators.md#op_gt_eq_multimap)|Überprüft, ob das map- oder multimap-Objekt links vom Operator größer gleich dem map- oder multimap-Objekt rechts vom Operator ist.|

### <a name="specialized-template-functions"></a>Spezialisierte Vorlagenfunktionen

|map-Version|multimap-Version|Beschreibung|
|-----------------|----------------------|-----------------|
|[swap (map)](../standard-library/map-functions.md#swap)|[swap (multimap)](../standard-library/map-functions.md#swap_multimap)|Tauscht die Elemente zweier map- oder multimap-Objekte aus.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[value_compare-Klasse](../standard-library/value-compare-class-map.md)|Stellt ein Funktionsobjekt bereit, das die Elemente einer Zuordnung vergleichen kann, indem die Werte ihrer Schlüssel verglichen werden, um deren relative Reihenfolge in der Zuordnung zu bestimmen.|
|[map-Klasse](../standard-library/map-class.md)|Wird zum Speichern und Abrufen von Daten aus einer Sammlung verwendet, in der jedes der Elemente einen eindeutigen Schlüssel hat, mit dem die Daten automatisch geordnet werden.|
|[multimap-Klasse](../standard-library/multimap-class.md)|Wird zum Speichern und Abrufen von Daten aus einer Sammlung verwendet, in der jedes der Elemente einen Schlüssel hat, mit dem die Daten automatisch geordnet werden. Die Schlüssel müssen keine eindeutigen Werte haben.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
