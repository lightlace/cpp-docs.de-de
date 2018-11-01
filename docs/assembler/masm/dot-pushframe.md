---
title: .PUSHFRAME
ms.date: 08/30/2018
f1_keywords:
- .PUSHFRAME
helpviewer_keywords:
- .PUSHFRAME directive
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
ms.openlocfilehash: 9ea506e25435c5d6f1b10eab8c4f25f72bf88791
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468327"
---
# <a name="pushframe"></a>.PUSHFRAME

Generiert eine `UWOP_PUSH_MACHFRAME` Entladen von Codeeintrag. Wenn der optionale `code` angegeben ist, wird der Eintrag der Entladung Code erhält einen Modifizierer von 1. Andernfalls ist der Modifizierer 0.

## <a name="syntax"></a>Syntax

> . PUSHFRAME [Code]

## <a name="remarks"></a>Hinweise

. PUSHFRAME ist nur zulässig, in der Prolog, die von erweitert und ermöglicht ml64.exe angeben, wie eine Funktion des Frames entlädt die [PROC](../../assembler/masm/proc.md) FRAME-Deklaration, um die [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) Richtlinie. Diese Direktiven generieren Sie Code nicht; Generieren sie nur `.xdata` und `.pdata`. . Indem Sie die Anweisungen, die die Aktionen, entladen werden implementieren, sollte PUSHFRAME vorangestellt werden. Es hat sich bewährt, sowohl den Code, den sie auf die Entladung in einem Makro gedacht sind, um sicherzustellen, dass Vereinbarung als auch die Entladung Anweisungen zu umschließen.

Weitere Informationen finden Sie unter [MASM für X64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>