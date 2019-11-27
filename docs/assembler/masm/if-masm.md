---
title: IF (MASM)
ms.date: 08/30/2018
f1_keywords:
- if
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: ed7b9e63bb19dcc16539dbdaaf1f6a7f16566b3c
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397464"
---
# <a name="if-masm"></a>IF (MASM)

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

Die folgenden Direktiven können für [ElseIf](../../assembler/masm/elseif-masm.md)ersetzt werden: **elseifb**, **ELSEIFDEF**, **elseifdif**, **elseifdifi**, **elseife**, **elseifdn**, **elseimedni**, **elseifnb**und **ELSEIFNDEF**. Optional: assembliert *else--Anweisungen* , wenn der vorherige Ausdruck false ist. Beachten Sie, dass die Ausdrücke zur assemblyzeit ausgewertet werden.

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)
