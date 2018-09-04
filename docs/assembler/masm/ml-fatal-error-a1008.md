---
title: ML-Schwerwiegender Fehler A1008 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1008
dev_langs:
- C++
helpviewer_keywords:
- A1008
ms.assetid: fe592f9d-c37b-4cd8-a51d-e3c15ddcab83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ec709823856e17c90d4af2a06262b30c966f39c
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691937"
---
# <a name="ml-fatal-error-a1008"></a>Schwerwiegender ML-Fehler A1008

**nicht übereinstimmende Makro Schachtelung**

Entweder ein Makro wurde nicht beendet werden, vor dem Ende der Datei oder die abschließende Anweisung [ENDM](../../assembler/masm/endm.md) nicht außerhalb eines Blocks Makro gefunden wurde.

Eine Ursache dieses Fehlers ist Auslassung des Punkts vor [. Wiederholen Sie die](../../assembler/masm/dot-repeat.md) oder [. WÄHREND](../../assembler/masm/dot-while.md).

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>