---
title: Nicht schwerwiegender ML-Fehler A2096
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A2096
helpviewer_keywords:
- A2096
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
ms.openlocfilehash: e6b31afeff801e7128b5a76576e9eaa3398f68e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62202489"
---
# <a name="ml-nonfatal-error-a2096"></a>Nicht schwerwiegender ML-Fehler A2096

**Segment, einer Gruppe oder Segmentregister erwartet**

Ein Segment oder eine Gruppe wurde erwartet, jedoch wurde nicht gefunden.

Eine der folgenden aufgetreten ist:

- Der linke Operand, der mit dem Segment angegeben überschreiben Operator (**:**) war nicht Segment (CS, DS, SS, ES, FS oder GS), Gruppe RegisterName, Segmentname oder Segment-Ausdruck.

- Die [VORAUSSETZEN](../../assembler/masm/assume.md) Direktive wurde ein Segmentregister, ohne eine gültige Segmentadresse, Segment registrieren, Gruppe oder die spezielle angegeben **Flatfile** Gruppe.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>