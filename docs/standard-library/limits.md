---
title: '&lt;limits&gt;'
ms.date: 11/04/2016
f1_keywords:
- limits/std::<limits>
- <limits>
helpviewer_keywords:
- limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
ms.openlocfilehash: 3ad740975cfff4f65f9e1c800a709cfaca3367db
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687812"
---
# <a name="ltlimitsgt"></a>&lt;limits&gt;

Definiert die Klassen Vorlagen `numeric_limits` und zwei Enumerationen zu Gleit Komma Darstellungen und-Rundungen.

## <a name="requirements"></a>Anforderungen

**Header:** \<limits>

**Namespace:** std

## <a name="remarks"></a>Hinweise

Explizite Spezialisierungs Eigenschaften der `numeric_limits`-Klasse beschreiben viele Eigenschaften der grundlegenden Typen, einschließlich der Zeichen-, ganzzahligen und Gleit Komma Typen sowie **boolescher** Wert, die implementiert werden, anstatt durch die C++ Regeln des Kurse. In \<limits> beschriebene Eigenschaften umfassen Genauigkeit, Darstellungen minimaler und maximaler Größe, Rundung und Fehler des Signalisierungstyps.

## <a name="members"></a>Member

### <a name="enumerations"></a>Enumerationen

|||
|-|-|
|[float_denorm_style](../standard-library/limits-enums.md#float_denorm_style)|Die Enumeration beschreibt die verschiedenen Methoden, die eine Implementierung für die Darstellung eines denormalisierten Gleitkommawerts auswählen kann – für Werte, die zu klein sind, um als normalisierte Werte dargestellt zu werden:|
|[float_round_style](../standard-library/limits-enums.md#float_round_style)|Die Enumeration beschreibt die verschiedenen Methoden, die eine Implementierung für die Rundung eines Gleitkommawerts auf einen ganzzahligen Wert auswählen kann.|

### <a name="classes"></a>Klassen

|||
|-|-|
|[numeric_limits-Klasse](../standard-library/numeric-limits-class.md)|Die Klassen Vorlage beschreibt arithmetische Eigenschaften integrierter numerischer Typen.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)
