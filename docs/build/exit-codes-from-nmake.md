---
title: Exitcodes von NMAKE
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, exit codes
- exit codes
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
ms.openlocfilehash: 08aceadf107112b446844b09fad24a11fbe7a731
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499592"
---
# <a name="exit-codes-from-nmake"></a>Exitcodes von NMAKE

NMAKE: Gibt die folgenden Exitcodes zurück:

|Code|Bedeutung|
|----------|-------------|
|0|Kein Fehler (möglicherweise eine Warnung)|
|1|Unvollständige Build (wird nur bei der/k ausgegeben)|
|2|Programmfehler, möglicherweise aufgrund einer der folgenden:|
||– Ein Syntaxfehler in das makefile|
||– Ein Code Fehler- oder Beenden eines Befehls|
||-Eine Unterbrechung durch den Benutzer|
|4|Systemfehler: nicht genügend Arbeitsspeicher|
|255|Ziel ist nicht auf dem neuesten Stand (wird nur bei der/q / ausgegeben)|

## <a name="see-also"></a>Siehe auch

[Ausführen von NMAKE](../build/running-nmake.md)