---
title: '&lt;set&gt; | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <set>
dev_langs:
- C++
helpviewer_keywords:
- set header
ms.assetid: 43cb1ab2-6383-48cf-8bdc-2b96d7203596
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aacfbda591755af86857da6c7d0b7891d2e72ebb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857050"
---
# <a name="ltsetgt"></a>&lt;set&gt;

Definiert die Containervorlagenklassen "set" und "multiset" und deren unterstützende Vorlagen.

## <a name="syntax"></a>Syntax

```cpp
#include <set>

```

## <a name="members"></a>Member

### <a name="operators"></a>Operatoren

|set-Version|multiset-Version|Beschreibung|
|-----------------|----------------------|-----------------|
|[operator!= (set)](../standard-library/set-operators.md#op_neq)|[operator!= (multiset)](../standard-library/set-operators.md#op_neq)|Überprüft, ob das set- oder multiset-Objekt links vom Operator ungleich dem set- oder multiset-Objekt rechts vom Operator ist.|
|[operator< (set)](../standard-library/set-operators.md#op_lt)|[operator< (multiset)](../standard-library/set-operators.md#op_lt_multiset)|Überprüft, ob das set- oder multiset-Objekt links vom Operator kleiner als das set- oder multiset-Objekt rechts vom Operator ist.|
|[operator<= (set)](../standard-library/set-operators.md#op_lt_eq)|[operator\<= (multiset)](../standard-library/set-operators.md#op_lt_eq_multiset)|Überprüft, ob das set- oder multiset-Objekt links vom Operator kleiner gleich dem set- oder multiset-Objekt rechts vom Operator ist.|
|[operator== (set)](../standard-library/set-operators.md#op_eq_eq)|[operator== (multiset)](../standard-library/set-operators.md#op_eq_eq_multiset)|Überprüft, ob das set- oder multiset-Objekt links vom Operator gleich dem set- oder multiset-Objekt rechts vom Operator ist.|
|[operator> (set)](../standard-library/set-operators.md#op_gt)|[operator> (multiset)](../standard-library/set-operators.md#op_gt_multiset)|Überprüft, ob das set- oder multiset-Objekt links vom Operator größer als das set- oder multiset-Objekt rechts vom Operator ist.|
|[operator>= (set)](../standard-library/set-operators.md#op_gt_eq)|[operator>= (multiset)](../standard-library/set-operators.md#op_gt_eq_multiset)|Überprüft, ob das set- oder multiset-Objekt links vom Operator größer gleich dem set- oder multiset-Objekt rechts vom Operator ist.|

### <a name="specialized-template-functions"></a>Spezialisierte Vorlagenfunktionen

|set-Version|multiset-Version|Beschreibung|
|-----------------|----------------------|-----------------|
|[swap](../standard-library/set-functions.md#swap)|[swap (multiset)](../standard-library/set-functions.md#swap_multiset)|Tauscht die Elemente von zwei set- oder multiset-Objekten aus.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[set-Klasse](../standard-library/set-class.md)|Wird zum Speichern und Abrufen von Daten aus einer Sammlung verwendet, in der die Werte der enthaltenen Elemente eindeutig sind und als Schlüsselwerte dienen, entsprechend denen die Daten automatisch geordnet werden.|
|[multiset-Klasse](../standard-library/multiset-class.md)|Wird zum Speichern von Daten in und zum Abrufen von Daten aus einer Sammlung verwendet, in der die Werte der enthaltenen Elemente nicht eindeutig sein müssen und als Schlüsselwerte dienen, entsprechend denen die Daten automatisch geordnet werden.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
