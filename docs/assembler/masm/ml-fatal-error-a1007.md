---
title: ML-Schwerwiegender Fehler A1007 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1007
dev_langs:
- C++
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 539ab431510d5dc721e6531c11069a87e27c287a
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693600"
---
# <a name="ml-fatal-error-a1007"></a>Schwerwiegender ML-Fehler A1007

**Die Schachtelungsebene ist zu tief**

Der Assembler erreicht schachteln. Der Grenzwert beträgt 20 Ebenen außer vermerkt.

Eine der folgenden wurde zu tief geschachtelt:

- Eine allgemeine Richtlinie z. B. [. IF](../../assembler/masm/dot-if.md), [. Wiederholen Sie die](../../assembler/masm/dot-repeat.md), oder [. WÄHREND](../../assembler/masm/dot-while.md).

- Die Strukturdefinition einer.

- Eine bedingte-Assembly-Direktive.

- Die Definition einer Prozedur.

- Ein [PUSHCONTEXT](../../assembler/masm/pushcontext.md) Richtlinie (der Grenzwert ist 10).

- Eine Definition des Segments.

- Eine Includedatei.

- Ein Makro.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>