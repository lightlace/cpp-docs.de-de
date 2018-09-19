---
title: Schwerwiegender ML--Fehler A2096 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2096
dev_langs:
- C++
helpviewer_keywords:
- A2096
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82f4ef76dca10b1208a931bc3e1cc09d82a639d2
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679597"
---
# <a name="ml-nonfatal-error-a2096"></a>Nicht schwerwiegender ML-Fehler A2096

**Segment, einer Gruppe oder Segmentregister erwartet**

Ein Segment oder eine Gruppe wurde erwartet, jedoch wurde nicht gefunden.

Eine der folgenden aufgetreten ist:

- Der linke Operand, der mit dem Segment angegeben überschreiben Operator (**:**) war nicht Segment (CS, DS, SS, ES, FS oder GS), Gruppe RegisterName, Segmentname oder Segment-Ausdruck.

- Die [VORAUSSETZEN](../../assembler/masm/assume.md) Direktive wurde ein Segmentregister, ohne eine gültige Segmentadresse, Segment registrieren, Gruppe oder die spezielle angegeben **Flatfile** Gruppe.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>