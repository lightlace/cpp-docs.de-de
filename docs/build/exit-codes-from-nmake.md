---
title: Exitcodes von NMAKE | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, exit codes
- exit codes
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c70c76292b62560b1d9895aca2851b4cf56802b
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861797"
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