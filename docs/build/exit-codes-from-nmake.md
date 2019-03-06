---
title: Exitcodes von NMAKE
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, exit codes
- exit codes
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
ms.openlocfilehash: 07a104d90d91a027864022d4c82412318eb5fe3d
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413237"
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
