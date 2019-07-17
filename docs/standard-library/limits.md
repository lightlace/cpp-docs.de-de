---
title: '&lt;limits&gt;'
ms.date: 11/04/2016
f1_keywords:
- limits/std::<limits>
- <limits>
helpviewer_keywords:
- limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
ms.openlocfilehash: e23c47b3eaecec92e462af7b2cc47627c5bad86a
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245320"
---
# <a name="ltlimitsgt"></a>&lt;limits&gt;

Definiert die Vorlagenklasse `numeric_limits` und zwei Enumerationen zu Gleitkommadarstellungen und zur Rundung.

## <a name="requirements"></a>Anforderungen

**Header:** \<limits>

**Namespace:** std

## <a name="remarks"></a>Hinweise

Explizite spezialisierungen der `numeric_limits` -Klasse beschreiben viele Eigenschaften der grundlegenden Typen, einschließlich der Zeichen, ganze Zahl und Gleitkomma-Datentypen und **"bool"** , die Implementierung definiert und nicht als unveränderlich sind die Regeln der Programmiersprache C++. In \<limits> beschriebene Eigenschaften umfassen Genauigkeit, Darstellungen minimaler und maximaler Größe, Rundung und Fehler des Signalisierungstyps.

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

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
