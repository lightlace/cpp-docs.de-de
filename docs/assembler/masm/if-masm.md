---
title: IF (MASM)
ms.date: 12/17/2019
f1_keywords:
- if
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: 38d366a3a41e7b08759594899cdcbb2cb84dfbfa
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317291"
---
# <a name="if"></a>WENN

Erteilt eine Assembly von *if-Anweisungen* , wenn *expression1* den Wert true hat (ungleich 0 (null)) oder *ElseIf-Anweisungen* , wenn *expression1* false (0) und *expression2* true ist.

## <a name="syntax"></a>Syntax

> **Wenn** *expression1*\
> *if-Anweisungen*\
> ⟦**ElseIf** *expression2*\
> *ElseIf-Anweisungen*⟧ \
> ⟦**Else** -\
> *else-Anweisungen*⟧ \
> **EndIf**

## <a name="remarks"></a>Hinweise

Die folgenden Direktiven können für [ElseIf](elseif-masm.md)ersetzt werden: **elseifb**, **ELSEIFDEF**, **elseifdif**, **elseifdifi**, **elseife**, **elseifdn**, **elseimedni**, **elseifnb**und **ELSEIFNDEF**. Optional: assembliert *else--Anweisungen* , wenn der vorherige Ausdruck false ist. Beachten Sie, dass die Ausdrücke zur assemblyzeit ausgewertet werden.

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
