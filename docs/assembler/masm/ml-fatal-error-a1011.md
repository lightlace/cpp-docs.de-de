---
title: ML-Schwerwiegender Fehler A1011 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1011
dev_langs:
- C++
helpviewer_keywords:
- A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32949773b869d189516a381ca7df941760a1e4e4
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43690807"
---
# <a name="ml-fatal-error-a1011"></a>Schwerwiegender ML-Fehler A1011

**Richtlinie muss im Steuerelementblock sein.**

Der Assembler finden Sie eine allgemeine Richtlinie, wo eine nicht erwartet wurde. Eine der folgenden Anweisungen wurde gefunden:

- [. ANDERE](../../assembler/masm/dot-else.md) ohne [. IF](../../assembler/masm/dot-if.md)

- [. ENDIF](../../assembler/masm/dot-endif.md) ohne [. IF](../../assembler/masm/dot-if.md)

- [. ENDW](../../assembler/masm/dot-endw.md) ohne [. WHILE](../../assembler/masm/dot-while.md)

- [. UNTILCXZ](../../assembler/masm/dot-untilcxz.md) ohne [. WIEDERHOLEN SIE DIE](../../assembler/masm/dot-repeat.md)

- [. WEITERHIN](../../assembler/masm/dot-continue.md) ohne [. WÄHREND](../../assembler/masm/dot-while.md) oder [. WIEDERHOLEN SIE DIE](../../assembler/masm/dot-repeat.md)

- [. UNTERBRECHEN](../../assembler/masm/dot-break.md) ohne [. WÄHREND](../../assembler/masm/dot-while.md) oder [. WIEDERHOLEN SIE DIE](../../assembler/masm/dot-repeat.md)

- [. ANDERE](../../assembler/masm/dot-else.md) folgenden `.ELSE`

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>