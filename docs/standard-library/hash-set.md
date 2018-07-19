---
title: '&lt;hash_set&gt; | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <hash_set>
- std::<hash_set>
dev_langs:
- C++
helpviewer_keywords:
- hash_set header
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f163ef7d0e5ec05dd0f41c11ea77c558cfef4919
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38955698"
---
# <a name="lthashsetgt"></a>&lt;hash_set&gt;

> [!NOTE]
> Dieser Header ist veraltet. Die Alternative ist [unordered_map-Klasse](../standard-library/unordered-set.md).

Definiert die Containervorlagenklassen „hash_set“ und „hash_multiset“ und deren unterstützende Vorlagen.

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
|[hash_compare-Klasse](../standard-library/hash-compare-class.md)|Beschreibt ein Objekt, das von jedem hashassoziativen Container verwendet werden kann – Hash_map, Hash_multimap, Hash_set oder Hash_multiset – als standardmäßiges `Traits` Parameterobjekt zu sortieren und zu hashen die darin enthaltenen Elemente.|
|[hash_set-Klasse](../standard-library/hash-set-class.md)|Wird zum Speichern und schnellen Abrufen von Daten aus einer Auflistung verwendet, in der die Werte der enthaltenen Elemente eindeutig sind und als Schlüsselwerte dienen.|
|[hash_multiset-Klasse](../standard-library/hash-multiset-class.md)|Wird zum Speichern und schnellen Abrufen von Daten aus einer Auflistung verwendet, in der die Werte der enthaltenen Elemente eindeutig sind und als Schlüsselwerte dienen.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
