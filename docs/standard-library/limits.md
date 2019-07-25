---
title: '&lt;limits&gt;'
ms.date: 11/04/2016
f1_keywords:
- limits/std::<limits>
- <limits>
helpviewer_keywords:
- limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
ms.openlocfilehash: de8f815cd59b84a1e63c231e18e4882d0b5d6f09
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447569"
---
# <a name="ltlimitsgt"></a>&lt;limits&gt;

Definiert die Vorlagenklasse `numeric_limits` und zwei Enumerationen zu Gleitkommadarstellungen und zur Rundung.

## <a name="requirements"></a>Anforderungen

**Header:** \<limits>

**Namespace:** std

## <a name="remarks"></a>Hinweise

Explizite Spezialisierungs spezizierungen `numeric_limits` der-Klasse beschreiben viele Eigenschaften der grundlegenden Typen, einschließlich der Zeichen-, ganzzahligen und Gleit Komma Typen sowie boolescher Wert, die implementiert werden, anstatt durch die Regeln des  C++Sprache. In \<limits> beschriebene Eigenschaften umfassen Genauigkeit, Darstellungen minimaler und maximaler Größe, Rundung und Fehler des Signalisierungstyps.

## <a name="members"></a>Member

### <a name="enumerations"></a>Enumerationen

|||
|-|-|
|[float_denorm_style](../standard-library/limits-enums.md#float_denorm_style)|Die Enumeration beschreibt die verschiedenen Methoden, die eine Implementierung für die Darstellung eines denormalisierten Gleitkommawerts auswählen kann – für Werte, die zu klein sind, um als normalisierte Werte dargestellt zu werden:|
|[float_round_style](../standard-library/limits-enums.md#float_round_style)|Die Enumeration beschreibt die verschiedenen Methoden, die eine Implementierung für die Rundung eines Gleitkommawerts auf einen ganzzahligen Wert auswählen kann.|

### <a name="classes"></a>Klassen

|||
|-|-|
|[numeric_limits-Klasse](../standard-library/numeric-limits-class.md)|Die Vorlagenklasse beschreibt arithmetische Eigenschaften der integrierten numerischen Typen.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
