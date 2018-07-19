---
title: '&lt;limits&gt; | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- limits/std::<limits>
- <limits>
dev_langs:
- C++
helpviewer_keywords:
- limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66f9401bed0a6c9d0b1ffa09a10f98afa258069d
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964755"
---
# <a name="ltlimitsgt"></a>&lt;limits&gt;

Definiert die Vorlagenklasse `numeric_limits` und zwei Enumerationen zu Gleitkommadarstellungen und zur Rundung.

## <a name="syntax"></a>Syntax

```cpp
#include <limits>

```

## <a name="remarks"></a>Hinweise

Explizite spezialisierungen der `numeric_limits` -Klasse beschreiben viele Eigenschaften der grundlegenden Typen, einschließlich der Zeichen, ganze Zahl und Gleitkomma-Datentypen und **"bool"** , die Implementierung definiert und nicht als unveränderlich sind die Regeln der Programmiersprache C++. In \<limits> beschriebene Eigenschaften umfassen Genauigkeit, Darstellungen minimaler und maximaler Größe, Rundung und Fehler des Signalisierungstyps.

### <a name="enumerations"></a>Enumerationen

|||
|-|-|
|[float_denorm_style](../standard-library/limits-enums.md#float_denorm_style)|Die Enumeration beschreibt die verschiedenen Methoden, die eine Implementierung für die Darstellung eines denormalisierten Gleitkommawerts auswählen kann – für Werte, die zu klein sind, um als normalisierte Werte dargestellt zu werden:|
|[float_round_style](../standard-library/limits-enums.md#float_round_style)|Die Enumeration beschreibt die verschiedenen Methoden, die eine Implementierung für die Rundung eines Gleitkommawerts auf einen ganzzahligen Wert auswählen kann.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[numeric_limits-Klasse](../standard-library/numeric-limits-class.md)|Die Vorlagenklasse beschreibt arithmetische Eigenschaften der integrierten numerischen Typen.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
