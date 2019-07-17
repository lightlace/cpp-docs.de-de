---
title: "\"high_resolution_clock\" Struct | Microsoft-Dokumentation"
ms.custom: ''
ms.date: 05/22/2018
ms.technology: cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::high_resolution_clock
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b00b20e7cea4fa24b37ad33d5536eb9844e6953
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269122"
---
# <a name="steadyclock-struct"></a>steady_clock-Struktur

Stellt eine *High_resolution* Uhr.

## <a name="syntax"></a>Syntax

```cpp
class high_resolution_clock
```

## <a name="members"></a>Member

### <a name="typedefs"></a>Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`duration`|Ein Synonym für `nanoseconds`, definiert in \<Chrono >.|
|`period`|Ein Synonym für `nano`, definiert in \<Ratio >.|
|`rep`|Ein Synonym für **lange** **lange**, der Typ, der verwendet wird, zum Darstellen der Anzahl von Zeiteinheiten in der enthaltenden Instanziierung von `duration`.|
|`time_point`|Ein Synonym für `chrono::time_point<high_resolution_clock>`.|

## <a name="functions"></a>Funktionen

|||
|-|-|
|`now`|Gibt die aktuelle Uhrzeit als eine `time_point` Wert.|

## <a name="constants"></a>Konstanten

|Name|Beschreibung|
|----------|-----------------|
|`is_steady`|Enthält **"true"** . Eine `high_resolution_clock` ist *gleichmäßig*.|
