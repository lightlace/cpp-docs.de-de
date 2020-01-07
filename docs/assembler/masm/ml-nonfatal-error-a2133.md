---
title: Nicht schwerwiegender ML-Fehler A2133
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2133
helpviewer_keywords:
- A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
ms.openlocfilehash: 1ffdf5fb6577dbd4e24312b3c57a4186173ddcf6
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75312637"
---
# <a name="ml-nonfatal-error-a2133"></a>Nicht schwerwiegender ML-Fehler A2133

**Registerwert überschrieben durch Aufrufen**

Ein Register wurde als Argument an eine Prozedur übergeben, aber der vom [Aufruf](invoke.md) zum übergeben anderer Argumente generierte Code hat den Inhalt des Registers zerstört.

Die Register AX, Al, ah, eax, DX, DL, dh und EDX können vom Assembler verwendet werden, um die Datenkonvertierung durchzuführen.

Verwenden Sie ein anderes Register.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](ml-error-messages.md)
