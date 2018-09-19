---
title: Schwerwiegender ML--Fehler A2133 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2133
dev_langs:
- C++
helpviewer_keywords:
- A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0df094f5e7135ffb3b9a5f09383e03e411755de3
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678065"
---
# <a name="ml-nonfatal-error-a2133"></a>Nicht schwerwiegender ML-Fehler A2133

**Registrieren von INVOKE überschrieben, Wert**

Ein Register als Argument an eine Prozedur übergeben wurde, aber der Code generiert werden, indem [INVOKE](../../assembler/masm/invoke.md) zerstört, den Inhalt des Registers, andere Argumente zu übergeben.

Der AX "," AL "," AH "," EAX "," DX "," DL "," DH, und "EDX-Registern können vom Assembler verwendet werden, zum Ausführen der Datenkonvertierung.

Verwenden Sie einen anderen registrieren.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>