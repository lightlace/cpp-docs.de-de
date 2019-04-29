---
title: Grundlegende Typen (C++/CX)
ms.date: 01/22/2017
ms.assetid: c9f82907-25f2-440b-91d6-afb8dbd46ea6
ms.openlocfilehash: 2bd5be01b868fd3086c2064edfd4ca343db425be
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301450"
---
# <a name="fundamental-types-ccx"></a>Grundlegende Typen (C++/CX)

Zusätzlich zu den standard C++ integrierte Typen, C++ / CX unterstützt das System der Typen, die von der Windows-Runtime-Architektur definiert ist, durch die Bereitstellung von Typdefinitionen für die grundlegende Windows-Runtime-, die C++-Standardtypen zugeordnet Typen... C++ / CX implementiert boolesche Ausdrücke, Zeichen und grundlegende numerische Typen. Dieser Typdefinitionen werden im `default` -Namespace definiert, der nicht explizit angegeben werden muss. Darüber hinaus C++ / CX stellt Wrapper und konkrete Implementierungen für bestimmte Windows-Runtime-Typen und Schnittstellen bereit.

## <a name="boolean-and-character-types"></a>Boolesche und Zeichentypen

Die folgende Tabelle enthält die integrierten booleschen und Zeichentypen sowie deren C++-Standardentsprechungen.

|Namespace|C++ / CX-Name|Definition|C++-Standardname|Wertebereich|
|---------------|-----------------------------------------------------------------------|----------------|-------------------------|---------------------|
|Plattform|Boolesch|Ein 8-Bit-boolescher Wert.|bool|**"true"** (ungleich null) und **"false"** (null)|
|default|char16|Ein nicht numerischer 16-Bit-Wert, der einen Unicode-Codepunkt (UTF-16) darstellt.|wchar_t<br /><br /> - oder - <br /><br /> L'c'|(Angegeben durch den Unicode-Standard)|

## <a name="numeric-types"></a>Numerische Typen

In der folgenden Tabelle sind die integrierten numerischen Typen aufgeführt. Die numerischen Typen sind im `default` -Namespace deklariert und stellen Typdefinitionen für den entsprechenden integrierten C++-Typ dar. Nicht alle integrierte C++-Typen (long, z. B.) werden in der Windows-Runtime unterstützt. Hinsichtlich Konsistenz und Übersichtlichkeit, sollten Sie C++ / CX-Namen.

|C++ / CX-Name|Definition|C++-Standardname|Wertebereich|
|-----------------------------------------------------------------------|----------------|-------------------------|---------------------|
|int8|Eine numerischer 8-Bit-Wert mit Vorzeichen.|char mit Vorzeichen|-128 und 127.|
|uint8|Eine numerischer 8-Bit-Wert ohne Vorzeichen.|unsigned char|0 bis 255|
|int16|Eine 16-Bit-Ganzzahl mit Vorzeichen.|short|32.768 bis 32.767|
|uint16|Eine 16-Bit-Ganzzahl ohne Vorzeichen.|unsigned short|0 bis 65.535|
|int32|Eine 32-Bit-Ganzzahl mit Vorzeichen.|int|2.147.483.648 bis 2.147.483.647|
|uint32|Eine 32-Bit-Ganzzahl ohne Vorzeichen.|unsigned int|0 bis 4.294.967.295|
|int64|Eine 64-Bit-Ganzzahl mit Vorzeichen.|long Long - oder - __int64|-9,223,372,036,854, 775,808 bis 9.223.372.036.854.775.807|
|uint64|Eine 64-Bit-Ganzzahl ohne Vorzeichen.|ein lange long - oder - unsigned __int64 ohne Vorzeichen|0 bis 18.446.744.073.709.551.615|
|float32|Eine 32-Bit-IEEE 754-Gleitkommazahl.|float|3.4E +/- 38 (7 Stellen)|
|float64|Eine 64-Bit-IEEE 754-Gleitkommazahl.|double|1.7E +/- 308 (15 Stellen)|

## <a name="windows-runtime-types"></a>Windows-Runtime-Typen

Die folgende Tabelle enthält einige weiteren Typen, die von der Windows-Runtime-Architektur definiert und sind in C++ integriert c++ / CX. „Object“ und „String“ sind Referenztypen. Die anderen sind Werttypen. Alle diese Typen werden im `Platform` -Namespace deklariert. Eine vollständige Liste finden Sie unter [Platform namespace](../cppcx/platform-namespace-c-cx.md).

|-Name|Definition|
|----------|----------------|
|Object|Alle Windows-Runtime-Typ darstellt.|
|Zeichenfolge|Eine Reihe von Zeichen, die Text darstellen.|
|Rect|Eine Gruppe von vier Gleitkommazahlen, die die Position und Größe eines Rechtecks angeben.|
|SizeT|Ein geordnetes Paar von Gleitkommazahlen, die eine Höhe und Breite angeben.|
|Punkt|Ein geordnetes Paar von Gleitkommazahlen für x- und y-Koordinaten, die einen Punkt in einer zweidimensionalen Ebene definieren.|
|GUID|Ein nicht numerischer 128-Bit-Wert, der als eindeutiger Bezeichner verwendet wird.|
|UIntPtr|(Nur für interne Verwendung.) Ein 64-Bit-Wert ohne Vorzeichen, der als Zeiger verwendet wird.|
|IntPtr|(Nur für interne Verwendung.)  Ein 64-Bit-Wert mit Vorzeichen, der als Zeiger verwendet wird.|

## <a name="see-also"></a>Siehe auch

[Typsystem](../cppcx/type-system-c-cx.md)
