---
title: .SAVEXMM128
ms.date: 08/30/2018
f1_keywords:
- .SAVEXMM128
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
ms.openlocfilehash: c29ec47170c5e0f46f02d53f23ab477a79bbdc32
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62205218"
---
# <a name="savexmm128"></a>.SAVEXMM128

Generiert Sie entweder eine `UWOP_SAVE_XMM128` oder `UWOP_SAVE_XMM128_FAR` Entladen von Codeeintrag für den angegebenen XMM-Register und offset, den aktuelle Prologoffset verwenden. Die effizienteste Codierung wählen MASM.

## <a name="syntax"></a>Syntax

> . savexmm128 Xmmreg, offset

## <a name="remarks"></a>Hinweise

. SAVEXMM128 ermöglicht ml64.exe angeben, wie eine Funktion des Frames entladen ist nur zulässig, in der Prolog, die von erweitert die [PROC](../../assembler/masm/proc.md) FRAME-Deklaration, um die [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) Richtlinie. Diese Direktiven generieren Sie Code nicht; Generieren sie nur `.xdata` und `.pdata`. . Indem Sie die Anweisungen, die die Aktionen, entladen werden implementieren, sollte SAVEXMM128 vorangestellt werden. Es hat sich bewährt, sowohl den Code, den sie auf die Entladung in einem Makro gedacht sind, um sicherzustellen, dass Vereinbarung als auch die Entladung Anweisungen zu umschließen.

*Offset* muss ein Vielfaches von 16 sein.

Weitere Informationen finden Sie unter [MASM für X64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>