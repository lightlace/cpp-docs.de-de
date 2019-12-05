---
title: Nicht schwerwiegender ML-Fehler A2096
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2096
helpviewer_keywords:
- A2096
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
ms.openlocfilehash: 14fb30214cf7badf51368672dc52635d50a067f1
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74855473"
---
# <a name="ml-nonfatal-error-a2096"></a>Nicht schwerwiegender ML-Fehler A2096

**Segment-, Gruppen-oder Segment Register erwartet.**

Ein Segment oder eine Gruppe wurde erwartet, aber nicht gefunden.

Eine der folgenden Fehler ist aufgetreten:

- Der linke Operand, der mit dem Segment Überschreibungs Operator ( **:** ) angegeben wird, war kein Segment Register (CS, DS, SS, es, FS oder GS), Gruppenname, Segment Name oder Segment Ausdruck.

- Der [Annahme](../../assembler/masm/assume.md) -Direktive wurde ein Segment Register ohne gültige Segment Adresse, Segment Register, Gruppe oder spezielle **flache** Gruppe zugewiesen.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>