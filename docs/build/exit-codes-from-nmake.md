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
ms.openlocfilehash: 3b5a593e38efb5230630ed01e65f4bfb1f2ba92a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722617"
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