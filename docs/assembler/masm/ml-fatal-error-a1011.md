---
title: Schwerwiegender ML-Fehler A1011
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A1011
helpviewer_keywords:
- A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
ms.openlocfilehash: 591755a1d7066d8251f61d2a22b9601a9ccb9dcb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62178565"
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