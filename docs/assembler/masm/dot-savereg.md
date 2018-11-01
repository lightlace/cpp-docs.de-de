---
title: .SAVEREG
ms.date: 08/30/2018
f1_keywords:
- .SAVEREG
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
ms.openlocfilehash: cac7aa7f2bdbf6b60831d2beb062f86559ec0358
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472820"
---
# <a name="savereg"></a>.SAVEREG

Generiert Sie entweder eine `UWOP_SAVE_NONVOL` oder `UWOP_SAVE_NONVOL_FAR` Entladen von Codeeintrag für den angegebenen Register (`reg`) und Offset (`offset`) mit den aktuellen Prologoffset. Die effizienteste Codierung wählen MASM.

## <a name="syntax"></a>Syntax

> . SAVEREG Reg, offset

## <a name="remarks"></a>Hinweise

. SAVEREG ist nur zulässig, in der Prolog, die von erweitert und ermöglicht ml64.exe angeben, wie eine Funktion des Frames entlädt die [PROC](../../assembler/masm/proc.md) FRAME-Deklaration, um die [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) Richtlinie. Diese Direktiven generieren Sie Code nicht; Generieren sie nur `.xdata` und `.pdata`. . Indem Sie die Anweisungen, die die Aktionen, entladen werden implementieren, sollte SAVEREG vorangestellt werden. Es hat sich bewährt, sowohl den Code, den sie auf die Entladung in einem Makro gedacht sind, um sicherzustellen, dass Vereinbarung als auch die Entladung Anweisungen zu umschließen.

Weitere Informationen finden Sie unter [MASM für X64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>