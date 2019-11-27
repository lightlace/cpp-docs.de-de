---
title: .SAVEXMM128
ms.date: 08/30/2018
f1_keywords:
- .SAVEXMM128
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
ms.openlocfilehash: 08bc5ab50e15aa59e0c49992d1810c7de20f364e
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397948"
---
# <a name="savexmm128"></a>.SAVEXMM128

Generiert entweder einen `UWOP_SAVE_XMM128` oder einen `UWOP_SAVE_XMM128_FAR` Entladungs Code Eintrag für das angegebene XMM-Register und den Offset mithilfe des aktuellen prologoffsets. MASM wählt die effizienteste Codierung aus.

## <a name="syntax"></a>Syntax

> **. Savexmm128** *xmmreg* , *Offset*

## <a name="remarks"></a>Hinweise

**. Savexmm128** ermöglicht Benutzern von ml64. exe, anzugeben, wie sich eine Frame Funktion entlädt und nur innerhalb des Prologs zulässig ist, der sich von der [proc](../../assembler/masm/proc.md) Frame-Deklaration zum erstreckt [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) -Direktive. Diese Direktiven generieren keinen Code. Sie generieren nur `.xdata` und `.pdata`. . Savexmm128 sollten Anweisungen vorangestellt sein, die tatsächlich die auszuwickenden Aktionen implementieren. Es wird empfohlen, sowohl die Entlade Direktiven als auch den Code, der in einem Makro entladen werden soll, zu schließen, um eine Vereinbarung zu gewährleisten.

der *Offset* muss ein Vielfaches von 16 sein.

Weitere Informationen finden Sie unter [MASM für x64 (ml64. exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)
