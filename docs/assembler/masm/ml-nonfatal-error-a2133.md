---
title: Nicht schwerwiegender ML-Fehler A2133
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A2133
helpviewer_keywords:
- A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
ms.openlocfilehash: 9e13dd48c77b9574229023e3cfc4cc2f2221d153
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62201209"
---
# <a name="ml-nonfatal-error-a2133"></a>Nicht schwerwiegender ML-Fehler A2133

**Registrieren von INVOKE überschrieben, Wert**

Ein Register als Argument an eine Prozedur übergeben wurde, aber der Code generiert werden, indem [INVOKE](../../assembler/masm/invoke.md) zerstört, den Inhalt des Registers, andere Argumente zu übergeben.

Der AX "," AL "," AH "," EAX "," DX "," DL "," DH, und "EDX-Registern können vom Assembler verwendet werden, zum Ausführen der Datenkonvertierung.

Verwenden Sie einen anderen registrieren.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>