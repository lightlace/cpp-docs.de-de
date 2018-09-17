---
title: Skalare Typen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 07c9195e-b6c7-4083-8ef0-8a93032e4d1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ad0fa75380ca971f7ac2dfa4c370c076f7d552e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700959"
---
# <a name="scalar-types"></a>Skalare Typen

Obwohl der Zugriff auf Daten aus einer Ausrichtung, ergeben kann, empfiehlt es sich, dass die Daten ausgerichtet werden, auf die natürliche Grenze um Leistung verloren gehen (oder ein Mehrfaches davon) zu vermeiden. Enumerationen sind Konstante ganze Zahlen und fungieren als 32-Bit-Ganzzahlen. Die folgende Tabelle beschreibt die Typdefinition und empfohlener Speicher dafür Bezug zur Ausrichtung, die mithilfe der folgenden Ausrichtungswerte:

- Byte - 8-Bit

- Word - 16-Bit

- Doppelwort - 32-Bit

- Quad-Word - 64-Bit

- Octa Word - 128-Bit

|||||
|-|-|-|-|
|Skalaren Typ|C-Datentyp|Speichergröße (in Byte)|Empfohlene Ausrichtung|
|**INT8**|**char**|1|Byte|
|**UINT8**|**unsigned char**|1|Byte|
|**INT16**|**short**|2|Word|
|**UINT16**|**unsigned short**|2|Word|
|**INT32**|**Int**, **lange**|4|Zeigt Doppelwort|
|**UINT32**|**ganze Zahl ohne Vorzeichen, unsigned long**|4|Zeigt Doppelwort|
|**INT64**|**__int64**|8|Vierfachwort|
|**UINT64**|**__int64 ohne Vorzeichen**|8|Vierfachwort|
|**FP32-Vorgänge (einfache Genauigkeit)**|**float**|4|Zeigt Doppelwort|
|**FP64 (doppelte Genauigkeit)**|**double**|8|Vierfachwort|
|**ZEIGER**|<strong>\*</strong>|8|Vierfachwort|
|**__m64**|**Struktur __m64**|8|Vierfachwort|
|**__m128**|**Struktur __m128**|16|Octaword|

## <a name="see-also"></a>Siehe auch

[Typen und Speicher](../build/types-and-storage.md)