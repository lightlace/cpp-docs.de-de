---
title: '&lt;hash_set&gt;'
ms.date: 11/04/2016
f1_keywords:
- <hash_set>
- std::<hash_set>
helpviewer_keywords:
- hash_set header
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
ms.openlocfilehash: 00ca476816213d38b3c50c64e0978e65ac1a5ea1
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687947"
---
# <a name="lthash_setgt"></a>&lt;hash_set&gt;

> [!NOTE]
> Dieser Header ist veraltet. Die Alternative ist [unordered_map-Klasse](../standard-library/unordered-set.md).

Definiert die Containerklassen Vorlagen hash_set und hash_multiset sowie deren unterstützende Vorlagen.

## <a name="syntax"></a>Syntax

```cpp
#include <hash_set>
```

## <a name="remarks"></a>Hinweise

### <a name="operators"></a>Operatoren

|Hash_set-Version|Hash_multiset-Version|Beschreibung|
|-----------------------|----------------------------|-----------------|
|[operator!= (hash_set)](../standard-library/hash-set-operators.md#op_neq)|[operator!= (hash_multiset)](../standard-library/hash-set-operators.md#op_neq)|Überprüft, ob das hash_set- oder hash_multiset-Objekt links vom Operator ungleich dem hash_set- oder hash_multiset-Objekt rechts vom Operator ist.|
|[operator== (hash_set)](../standard-library/hash-set-operators.md#op_eq_eq)|[operator== (hash_multiset)](../standard-library/hash-set-operators.md#op_eq_eq)|Überprüft, ob das hash_set- oder hash_multiset-Objekt links vom Operator gleich dem hash_set- oder hash_multiset-Objekt rechts vom Operator ist.|

### <a name="specialized-template-functions"></a>Spezialisierte Vorlagenfunktionen

|Hash_set-Version|Hash_multiset-Version|Beschreibung|
|-----------------------|----------------------------|-----------------|
|[swap (hash_set)](../standard-library/hash-set-functions.md#swap)|[swap (hash_multiset)](../standard-library/hash-set-functions.md#swap_hash_multiset)|Tauscht die Elemente zweier hash_sets oder hash_multisets aus.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[hash_compare-Klasse](../standard-library/hash-compare-class.md)|Beschreibt ein Objekt, das von jedem Hash assoziativen Container – hash_map, hash_multimap, hash_set oder Hash_multiset – als standardmäßiges `Traits` Parameter Objekt verwendet werden kann, um die darin enthaltenen Elemente zu sortieren und zu hashen.|
|[hash_set-Klasse](../standard-library/hash-set-class.md)|Wird zum Speichern und schnellen Abrufen von Daten aus einer Auflistung verwendet, in der die Werte der enthaltenen Elemente eindeutig sind und als Schlüsselwerte dienen.|
|[hash_multiset-Klasse](../standard-library/hash-multiset-class.md)|Wird zum Speichern und schnellen Abrufen von Daten aus einer Auflistung verwendet, in der die Werte der enthaltenen Elemente eindeutig sind und als Schlüsselwerte dienen.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)
