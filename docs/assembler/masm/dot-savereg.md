---
title: .SAVEREG
ms.date: 12/16/2019
f1_keywords:
- .SAVEREG
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
ms.openlocfilehash: 18cb6e563084e8c5357bec2a8052a2b38fcdffee
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317551"
---
# <a name="savereg"></a>.SAVEREG

Generiert entweder einen `UWOP_SAVE_NONVOL` oder einen `UWOP_SAVE_NONVOL_FAR` Entladungs Code Eintrag für das angegebene Register (*reg*) und den Offset (*Offset*) mithilfe des aktuellen prologoffsets. MASM wählt die effizienteste Codierung aus.

## <a name="syntax"></a>Syntax

> **. SAVEREG** *reg* __,__ *Offset*

## <a name="remarks"></a>Hinweise

**. Mit SAVEREG** können Benutzer von ml64. exe angeben, wie sich eine Frame Funktion entlädt und nur innerhalb des Prologs zulässig ist, der von der [proc](proc.md) Frame-Deklaration zum reicht [. ENDPROLOG](dot-endprolog.md) -Direktive. Diese Direktiven generieren keinen Code. Sie generieren nur `.xdata` und `.pdata`. **. SAVEREG** sollten Anweisungen vorangestellt sein, die tatsächlich die auszuwickenden Aktionen implementieren. Es wird empfohlen, sowohl die Entlade Direktiven als auch den Code, der in einem Makro entladen werden soll, zu schließen, um eine Vereinbarung zu gewährleisten.

Weitere Informationen finden Sie unter [MASM für x64 (ml64. exe)](masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
