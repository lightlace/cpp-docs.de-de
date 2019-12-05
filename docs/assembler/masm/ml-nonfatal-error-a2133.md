---
title: Nicht schwerwiegender ML-Fehler A2133
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2133
helpviewer_keywords:
- A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
ms.openlocfilehash: c2d13aefe02543129340bcc307771a1026776d61
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74854614"
---
# <a name="ml-nonfatal-error-a2133"></a>Nicht schwerwiegender ML-Fehler A2133

**Registerwert überschrieben durch Aufrufen**

Ein Register wurde als Argument an eine Prozedur übergeben, aber der vom [Aufruf](../../assembler/masm/invoke.md) zum übergeben anderer Argumente generierte Code hat den Inhalt des Registers zerstört.

Die Register AX, Al, ah, eax, DX, DL, dh und EDX können vom Assembler verwendet werden, um die Datenkonvertierung durchzuführen.

Verwenden Sie ein anderes Register.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>