---
title: .SAVEXMM128
ms.date: 12/17/2019
f1_keywords:
- .SAVEXMM128
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
ms.openlocfilehash: 6402b75c10b1400d56923116621f00b4d0908822
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318253"
---
# <a name="savexmm128"></a>.SAVEXMM128

Generiert entweder einen `UWOP_SAVE_XMM128` oder einen `UWOP_SAVE_XMM128_FAR` Entladungs Code Eintrag für das angegebene XMM-Register und den Offset mithilfe des aktuellen prologoffsets. MASM wählt die effizienteste Codierung aus.

## <a name="syntax"></a>Syntax

> **. Savexmm128** *xmmreg* , *Offset*

## <a name="remarks"></a>Hinweise

**. Savexmm128** ermöglicht Benutzern von ml64. exe, anzugeben, wie sich eine Frame Funktion entlädt und nur innerhalb des Prologs zulässig ist, der sich von der [proc](proc.md) Frame-Deklaration zum erstreckt [. ENDPROLOG](dot-endprolog.md) -Direktive. Diese Direktiven generieren keinen Code. Sie generieren nur `.xdata` und `.pdata`. . Savexmm128 sollten Anweisungen vorangestellt sein, die tatsächlich die auszuwickenden Aktionen implementieren. Es wird empfohlen, sowohl die Entlade Direktiven als auch den Code, der in einem Makro entladen werden soll, zu schließen, um eine Vereinbarung zu gewährleisten.

der *Offset* muss ein Vielfaches von 16 sein.

Weitere Informationen finden Sie unter [MASM für x64 (ml64. exe)](masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
